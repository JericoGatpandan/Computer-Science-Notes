---

kanban-plugin: board

---

## Requirements

- [ ] Todo properties should be stored in a class or constructor
- [ ] Properties should include `title`, `description`, `duedate`, `priority`
- [ ] Optional properties can be `notes` or a `checklist`


## Projects support

- [ ] There should be multiple projects or separate todo lists
- [ ] A default project should exist that displays all todos when the app first opens
- [ ] Users should be able to create new projects
- [ ] Users can assign todos to a specific project


## DOM requirement

- [ ] All core logic (creating todos, updating them, etc.) should be in separate modules
- [ ] DOM/UI code should not mix with the core application logic


## User Interface

- [ ] A way to view all projects
- [ ] A way to view all todos within a selected project
- [ ] Show todo `title` and `duedate`
- [ ] Use different styles or colors to indicate `priority`
- [ ] Ability to expand a todo to view or edit its details
- [ ] Option to delete a todo


## Store data in locat storage

- [ ] Save all todos and projects to local storage
- [ ] Handle missing or empty local storage data without crashing




%% kanban:settings
```
{"kanban-plugin":"board","list-collapse":[false,false,false,false,false]}
```
%%