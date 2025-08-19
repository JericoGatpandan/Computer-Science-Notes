 Thanks Jerico! This `project.js` module (Module 3) looks like it handles:

- Project creation
    
- Todo management inside a project
    
- Global `PROJECTS` registry
    

Let’s now evaluate it thoroughly in terms of:

---

## ✅ What’s Good

- **Encapsulation**: `Project` manages its own todos — good OOP design.
    
- **Separation of concerns**: `Project` uses `createTodo` from another module, avoiding tight coupling with `Todo`.
    
- Good use of helper functions: `createProject` provides a factory pattern.
    

---

## 🧹 Clean Code Suggestions

### 1. ❌ `PROJECTS` as a global mutable array

```js
export const PROJECTS = [];
```

- Having a global array introduces potential side effects and makes testing harder.
    
- Suggestion: Encapsulate it in a `ProjectManager` or `ProjectRepository` class.
    

Example:

```js
export class ProjectRepository {
  constructor() {
    this.projects = [];
  }

  createProject(name) {
    const project = new Project(name);
    this.projects.push(project);
    return project;
  }

  getAllProjects() {
    return this.projects;
  }

  findProjectByName(name) {
    return this.projects.find(p => p.name === name);
  }
}
```

This helps respect **SRP** and **DIP** (see more below).

---

### 2. ⚠️ Method `addTodo(...)` couples creation logic into the project

It:

```js
const todo = createTodo(...);
this.todos.push(todo);
```

This means `Project` **creates** the todo itself — a violation of **Single Responsibility**.

Instead, make `addTodo()` accept a `Todo` object:

```js
addTodo(todo) {
  this.todos.push(todo);
}
```

Let another class handle creation (like a controller or factory). This respects **SRP** and **DIP**.

---

### 3. ❌ No way to rename or delete project from outside

Consider adding:

```js
renameProject(newName) {
  this.name = newName;
}
```

---

## 🧠 SOLID Principle Evaluation (project.js)

|Principle|Status|Comments|
|---|---|---|
|SRP|⚠️ Mixed|`Project` is doing todo creation, todo editing, and project data.|
|OCP|✅ Good|You can extend todo editing without changing Project.|
|LSP|✅ OK|Project can be subclassed if needed.|
|ISP|✅ N/A|No interfaces.|
|DIP|❌ No|`Project` directly depends on `createTodo()` instead of abstraction.|

---

## ✅ Suggested Refactor

```js
// project.js
export class Project {
  constructor(name) {
    this.name = name;
    this.todos = [];
  }

  getName() {
    return this.name;
  }

  getTodos() {
    return this.todos;
  }

  rename(newName) {
    this.name = newName;
  }

  addTodo(todo) {
    this.todos.push(todo);
  }

  deleteTodo(ID) {
    this.todos = this.todos.filter((todo) => todo.ID !== ID);
  }

  editTodo(ID, newData) {
    const todo = this.todos.find((todo) => todo.ID === ID);
    if (todo) {
      todo.edit(newData);
    }
  }
}

// Optional repository class to avoid global state
export class ProjectRepository {
  constructor() {
    this.projects = [];
  }

  createProject(name) {
    const project = new Project(name);
    this.projects.push(project);
    return project;
  }

  getAllProjects() {
    return this.projects;
  }

  findProjectByName(name) {
    return this.projects.find(p => p.getName() === name);
  }
}
```

---

### 🧪 Bonus: Enforce type check (Optional)

```js
addTodo(todo) {
  if (!(todo instanceof Todo)) throw new Error("Must pass a Todo");
  this.todos.push(todo);
}
```

---

✅ You can now send **Module 4 (ui.js)** and I’ll finalize the refactor suggestions with the full picture.