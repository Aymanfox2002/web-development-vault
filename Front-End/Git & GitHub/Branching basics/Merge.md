> [!info]
> **Merging** in Git is a fundamental operation that combines multiple sequences of commits into one unified history. It is often used to integrate changes from different branches, ensuring that all contributions are reflected in the main branch.

---

## Types of merges in Git:

1. **[[Fast-Forward Merge:]]** This occurs when there is a direct, linear path between the current branch and the target branch. Git simply moves the current branch pointer to the target branch.
2. **[[3-Way Merge:]]** This is used when branches have diverged. Git uses three commits: the two branch tips and their common ancestor to create a merge commit that combines the changes.

---

| <mark class="hltr-g">Command</mark> | <mark class="hltr-b">Description</mark>            |
| ----------------------------------- | -------------------------------------------------- |
| git merge `branch name`             | merge the specified branch into the current branch |

