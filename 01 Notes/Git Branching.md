#git #version-control #branches #merge #conflicts
### Creating Branches

- Make new branches:
```bash
git branch <branch_name>
```

- Change to your new branch:
```bash
git checkout <branch_name>
```

- Create and change to a new branch in one command:
```bash
git checkout -b <branch_name>
```

---

### Viewing Branches

- See all current branches:
```bash
git branch
```
- The branch you’re currently on is indicated with an **asterisk (*)**

---

### Switching Branches

- To go back to `main` from any branch:
```bash
git checkout main
```

---

### Merging Branches

- Once done with a feature branch, bring its commits to `main` by performing a **merge**:
```bash
git merge <branch_name>
```
- This adds the commits from `<branch_name>` into the branch you’re currently on.

**Example:**  
A `develop` branch is created, committed to, then merged into `main`.

```
main
 develop
  commit1
  commit2
  commit1a
  commit2a
   merge to main
Example of Git Branching
```

---

### Merge Conflicts

- If the same lines in a file were changed in two different branches → **merge conflict** occurs.
- To finish merging, you must **resolve the conflict first** (covered in a future lesson).

---

### Deleting Branches

- Delete a branch from the local repo (if already merged into `main`):
```bash
git branch -d <branch_name>
```
    
- Force delete a branch (even if not merged):
```bash
git branch -D <branch_name>
```
    
- Delete a branch from the remote repo (GitHub):
```bash
git push origin --delete <branch_name>
```