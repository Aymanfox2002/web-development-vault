> [!Info]
> Creating a branch in Git is a fundamental part of working with version control, allowing you to work on different features or fixes without affecting the main codebase. You can create branches either through the **terminal** or **github interface**.
> 
> The git branch command lets you create, list, rename, and delete branches. It doesn’t let you switch between branches or put a forked history back together again. For this reason, git branch is tightly integrated with the **git checkout** and **git merge** commands.


---
## **Common options**


| <mark class="hltr-g">Command</mark>                                 | <mark class="hltr-b">Description</mark>                                                                                                                                                                   |
| ------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| git branch `branch name`<br>                                        | Create a new branch called `＜branch＞`. This does _not_ check out the new branch                                                                                                                           |
| git checkout `branch name`                                          | switch to a different branch, you can look to [[Checkout]] lesson                                                                                                                                         |
| git branch -d `branch name`                                         | Delete the specified branch. This is a “safe” operation in that Git prevents you from deleting the branch if it has unmerged changes.                                                                     |
| git branch -D `branch name`                                         | Force delete the specified branch, even if it has unmerged changes. This is the command to use if you want to permanently throw away all of the commits associated with a particular line of development. |
| git branch -m `branch name`                                         | Rename the current branch to `＜branch name＞`.                                                                                                                                                             |
| git push origin --delete main<br>`or`<br>git push origin  **:**main | this command delete main branch remotely, you can use `git fetch -p` after that and this make branches which no longer exist on the remote will be deleted.                                               |
| git branch                                                          | List all of the branches in your repository. This is synonymous with `git branch --list.`                                                                                                                 |
| git branch -r                                                       | List all remote branches.                                                                                                                                                                                 |
| git branch -a                                                       | List all remote branches and local branches.                                                                                                                                                              |
