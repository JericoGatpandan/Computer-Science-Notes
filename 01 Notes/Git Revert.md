1. Sometimes, you may not fully test your changes before committing them, which may have undesirable consequences. You can back out your changes by using a `git revert` command like the following.
    
    You can either specify the ID of your commit that you can see from the previous log output or use the shortcut `HEAD` to rollback the last commit:
	- `git revert HEAD --no-edit`


> NOTE: 1. If you don't specify the `--no-edit` flag, you may be presented with an editor screen showing the message with changes to be reverted. In that case, press the `Control` (or Ctrl) key simultaneously with `X`.  
> 2. `git revert HEAD` **does not delete a file**, it **adds a new commit** that undoes the changes introduced by the previous commit.

2. The output shows the most recent commit with the specified id has been reverted.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-CD0131EN-SkillsNetwork/labs/git-branch-commands/images/git_revert.jpg)

#git #version-control #commits #undo