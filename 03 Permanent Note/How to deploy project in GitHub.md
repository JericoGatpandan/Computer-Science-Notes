---
tags: permanent
created: 2025-07-10
id: 20250710112814
---
# Idea: How to deploy or redeploy project in GitHub

"1. Make a new branch to deploy from by running `git branch gh-pages`. You only need to do this the first time you deploy. The rest of the steps should be done every time you deploy or redeploy your project. **only do if gh-pages branch is not yet created**
### This should be done every time I deploy or redeploy my project
1. Make sure you have all your work committed. You can use `git status` to see if there’s anything that needs committing.
	1. Run `git checkout gh-pages && git merge main --no-edit` to change branch and sync your changes from `main` so that you’re ready to deploy.
2. Now let’s bundle our application into `dist` with your build command. For now, that’s `npx webpack`.
3. Now there are a few more commands. Run each of these in order:
    
    ```bash
    git add dist -f && git commit -m "Deployment commit"
    git subtree push --prefix dist origin gh-pages
    git checkout main
    ```
    
4. Recall that the **source branch** for GitHub Pages is set in your repository’s settings. Get this changed to the `gh-pages` branch. That should be everything!

#Deployment

🔗 Links to:
- [[Git Branching]]
- [[GitHub]]

👀 Related Topics:
- [[Git Syntax]]