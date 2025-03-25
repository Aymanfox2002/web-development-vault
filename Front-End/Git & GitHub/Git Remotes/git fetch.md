
*The best way to explain `git fetch` by compare it with `git pull`*


> [!NOTE] Fetch
> - **Fetches updates:** `git fetch` retrieves all the latest changes from the remote repository, including new branches and commits, but it does not merge them into your local branches.
>     
> - **No changes to working directory:** Your working directory and local branches remain unchanged. You get the latest updates, but you need to merge them manually if you want to integrate them into your local branch.
>     
> - **Safe operation:** It’s a safe way to see what others have been working on without affecting your local work.
> 
> **Usage:**
> 
> git fetch `remote-name`



> [!warning] Pull
> - **Fetches and merges updates:** `git pull` is a combination of `git fetch` followed by `git merge`. It retrieves the latest changes from the remote repository and immediately merges them into your current branch.
>     
> - **Automatic merge:** Your current branch is updated with the changes from the remote repository, which might result in merge conflicts if there are differences between your local changes and the remote changes.
>     
> - **Convenient:** It’s a convenient command to quickly update your local branch with the latest changes from the remote repository.
> 
> **Usage: **
> 
> git pull `remote-name` `local-name`

