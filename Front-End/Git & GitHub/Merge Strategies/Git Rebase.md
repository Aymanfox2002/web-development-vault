> [!Info]
> Git rebase is a powerful tool that allows you to integrate changes from one branch into another. Unlike a merge, which creates a new commit to combine histories, rebase moves or "rebases" the feature branch's commits onto the tip of the main branch, resulting in a linear and cleaner project history.

---
## Merge VS. Rebase

- **Rebase:** Moves commits to the tip of the target branch, creating a linear history.
- **Merge:** Creates a merge commit to combine histories, preserving the branch structure.

![[git-rebase.png|841x545]]

---

## How does It work?

```bash
git init -b
echo "Initial content" > file.txt
git add file.txt
git commit -m "Initial commit"
git checkout -b feature-branch
echo "Feature content" >> file.txt
git add file.txt
git commit -m "Add feature content"
git checkout main
echo "Main branch content" >> file.txt
git add file.txt
git commit -m "Add main branch content"
git checkout feature-branch
git rebase main
```

---
## Abort the rebase

*If you want to abort the rebase process and return to the previous state:*

```
git rebase --abort
```
