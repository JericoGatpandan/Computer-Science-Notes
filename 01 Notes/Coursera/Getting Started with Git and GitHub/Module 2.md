---
tags:
  - literature
  - Git
  - GitHub
source: https://www.coursera.org/learn/getting-started-with-git-and-github/home/module/2
created: 2025-07-23
Type: Video
---
# Git Workflows with Git Commands
## Overview of Git Workflows
This content provides an overview of Git workflows, essential for effective collaboration in software development.

**Understanding Git Workflows**
- Git workflows help manage version control and collaboration, preventing issues like code conflicts.
- The first step is cloning a repository from GitHub to create a local copy of the project.

**Steps in a Git Workflow**
- Create a branch from the main branch to work on new features without affecting the main codebase.
- Move changed files to a staging area, commit them with a descriptive message, and push the changes to the remote repository.

**Collaboration and Merging**
- After pushing changes, create a pull request for a maintainer to review and merge the branch into the main branch.
- For new projects, initialize a local repository, track files, and push them to a newly created remote repository for team collaboration.
## Overview of Git Commands
This content provides an overview of basic Git commands and their applications in version control.

**Understanding Command-Line Interface (CLI) Commands**
- The `mkdir` command is used to create a new directory for your project.
- The `cd` command allows you to navigate into the created directory.

**Basic Git Commands**
- The `git init` command initializes a new Git repository in the directory.
- The `git add` command stages changes, while git commit -m saves those changes with a descriptive message.

**Branching and Merging**
- The `git branch` command creates a new branch for isolated development.
- The `git merge` command combines changes from a feature branch back into the main branch.

## [[Git Commands]]

## Demo: Working with Branches using Git Commands
This video lecture focuses on using Git commands to manage branches effectively in software development.

**Understanding Git Branching**
- Git branches allow developers to work on features, experiments, or fixes independently without affecting the main codebase.
- The branching workflow is essential for collaboration in version control, enabling teams to work in isolation.

**Creating and Managing Branches**
- To create a new branch, use the command `git branch <branch-name>`, which duplicates the current branch.
- Switch to the new branch with `git checkout <branch-name>` to make changes without impacting the main branch.

**Merging Changes and Pushing to Remote**
- After making changes, stage them with `git add <file>` and commit using `git commit -m "<message>"`.
- To merge changes back into the main branch, switch to the main branch and use `git merge <branch-name>`, followed by pushing the updates to the remote repository with `git push -u origin main`.

## Cloning and Forking GitHub Projects
This course item focuses on the essential concepts of cloning and forking GitHub projects, which are fundamental for collaborative software development.

**Cloning Repositories**
- Cloning creates a local copy of a repository, allowing you to work offline and sync changes back to the original repository.
- To clone, use the command `git clone <URL>` after copying the repository's URL from GitHub.

**Forking Projects**
- Forking allows you to create a personal copy of a repository to modify or extend it without affecting the original.
- You can submit changes back to the original repository through a pull request after making your modifications.

**Managing Remote Repositories**
- Use commands like `git push`, `git fetch`, and `git pull` to manage changes between your local and remote repositories.
- Understanding the terms "origin" (your fork) and "upstream" (the original repository) is crucial for effective collaboration.
## Cloning versus Forking
This content focuses on the differences between cloning and forking in Git and GitHub, as well as the workflows associated with each.

**Cloning and Forking Overview**
- Cloning creates a local copy of a repository, allowing developers to work on it independently.
- Forking creates a new repository based on an existing one, enabling the development of derivative projects.

**Forking Workflow**
- To fork a project, select the Fork option on GitHub, creating a copy that becomes the origin for further development.
- Developers can clone the forked repository, create branches, and make changes, which can then be pushed back to the origin via pull requests.

**Cloning Workflow**
- Cloning is used to create an identical copy of a remote repository, allowing new developers to collaborate on the project.
- After cloning, developers can create branches, make changes, and push updates to the origin for review and merging.
## Managing GitHub Projects
This content focuses on the roles and commands associated with managing GitHub projects effectively.

**Roles in Managing GitHub Projects**
- **Developer**: Participates in group projects and uses commands like git clone, git pull, git fetch, git push, and git request pull to communicate and collaborate.
- **Integrator**: Reviews and integrates changes from developers, using commands such as git pull, git revert, and git push to manage contributions.

**Repository Administration**
- **Repository Administrator**: Organizes the repository structure, manages user access, and configures necessary servers and settings. They also utilize GitHub actions for automating workflows, including continuous integration and delivery (CICD).

# Summary: Git Workflows with Git Commands
In this module, you learned that
- GitHub has over 100 million repositories. You can clone a repository and sync changes back to the original. You can also fork a repository and use it as the base for the new project or work on that project independently.
    
- The steps included in a GitHub workflow are:
    
    - Clone the remote repository or initialize a Git repository.
    - Move files to a staging area.
    - Perform an initial commit.
    - Create a branch and work on it.
    - Add files to the staging area and commit.
    - Push local commits to the remote repository.
    - Create a pull request for review and merging.
    - Use the pull operation to update the local repository.
- Multiple roles are involved in managing a project: Developer, Integrator, and Repository Administrator.
    
    - A Developer working in a group project uses commands like git clone, git pull, git fetch, git push, and git request-pull in addition to the ones needed by a standalone developer.
    - An Integrator in a group project reviews and integrates changes made by others. Integrators use commands like git pull, git revert, and git push in addition to the ones needed by participants.
    - Repository Administrators structure how the repository is organized and how users interact with the repository. They also configure the servers needed for accessing the web services and documentation, define email and index settings, and manage the look and feel of the application.
        
- The following table shows various Git commands:

|   |   |   |   |   |
|---|---|---|---|---|
|git init|git checkout|git revert|git-format-patch|git fetch upstream|
|git status|git merge|git config --global user.email|git-request-pull|git merge upstream/main|
|git add .|git clone|git config --global user.name|git-send-email|git pull upstream|
|git commit|git pull|git remote -v|git-am|git web|
|git log|git push|git remote rename|git-daemon|git-instaweb|
|git reset|git version|git remote add origin|git remote -v|git-pull downstream|
|git branch|git diff|git-remote|git remote add upstream|git-rerere|
# Cheat Sheet: Git Commands and Managing GitHub Projects
![[Git Commands and Managing GitHub Projects_Cheat Sheet.pdf]]

# Glossary: Git Commands and Managing GitHub Projects

|Term|Definition|
|---|---|
|**Cloning**|A process of creating a copy of the project's code and its complete version history from the remote repository on the local machine.|
|**Commit**|A snapshot of the project's current state at a specific point in time, along with a description of the changes made.|
|**Developer**|A computer programmer who is responsible for writing code.|
|**Distributed version control system (DVCS)**|A system that keeps track of changes to code, regardless of where it is stored. Multiple users work on the same codebase or repository, mirroring the codebase on their computers if needed, while the distributed version control software helps manage synchronization amongst the various codebase mirrors.|
|**Fork**|A copy of a repository into your GitHub account.|
|**Forking**|Forking creates a copy of a repository on which one can work without affecting the original repository.|
|**GitHub**|A web-hosted service for the Git repository.|
|**Git**|A free and open-source software distributed under the GNU General Public License. It is a distributed version control system that allows users to have a copy of their own project on their computer anywhere in the world.|
|**Integrator**|A role that is responsible for managing changes made by developers.|
|**Master branch**|A branch that stores the deployable version of your code. The master branch is created by default and is definitive.|
|**Merge**|A process to combine changes from one branch to another, typically merging a feature branch into the main branch.|
|**Origin**|A term that refers to the repository where a copy is cloned from.|
|**Pull request**|A process used to request that someone review and approve your changes before they become final.|
|**Remote repositories**|Repositories that are stored elsewhere. They can exist on the internet, on your network, or on your local computer.|
|**Repository administrator**|A role that is responsible for configuring and maintaining access to the repository.|
|**Repository**|A data structure for storing documents, including application source code. It contains the project folders that are set up for version control.|
|**Staging area**|An area where commits can be formatted and reviewed before completing the commit.|
|**Upstream**|A term used by developers to refer to the original source where the local copy was cloned from.|
|**Version control**|A system that allows you to keep track of changes to your documents. This process allows you to recover older versions of the documents if any mistakes are made.|
