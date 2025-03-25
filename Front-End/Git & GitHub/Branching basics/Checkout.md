> [!info]
> **The "checkout" command can switch the currently active branch - but it can also be used to restore files.**
> 
> The most common use case for "checkout" is when you want to _switch to a different branch_, making it the new HEAD branch.
> 
> Another use case for "checkout" is when you want to _restore a historic version_ of a specific file. Thereby, you can reset single files to earlier revisions - while keeping the rest of the project untouched.

---


| <mark class="hltr-g">Command</mark>                  | <mark class="hltr-b">Description</mark>                                                                                                                                                                                                                                                                                |
| ---------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| git checkout `branch-name`                           | **The name of a local branch that you want to switch to.** By specifying the name of a local branch, you will switch to this branch and make it the current "HEAD" branch.                                                                                                                                             |
| git checkout -b `new-branch`                         | **Creates a new local branch and directly switches to it.**                                                                                                                                                                                                                                                            |
| git checkout -b `new-branch` --track `remote-branch` | Creates a new local branch - and sets up an "upstream" configuration. This way, the new local branch has a tracking relationship with its remote counterpart. This allows you to more easily see when the two aren't in sync (i.e. when unpushed commits in the local branch or unpulled commits in the remote exist). |
| git checkout file-path commit-hash                   | Restores a historic revision of a given file. By providing HEAD as the revision, you can restore the last committed version of a file - effectively undoing any local changes that happened since then. If you want to restore a specific earlier revision you can provide that revision's SHA-1 hash.                 |

