> [!Info]
> A **non-fast-forward merge** occurs when the branch you want to merge into (the target branch) has new commits that diverge from the source branch. In this scenario, Git cannot perform a simple fast-forward; instead, it creates a new merge commit to combine the histories of both branches.

---

## How Does It Work?

```bash
git init -b main
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
git merge feature-branch
```

*In this case, Git will create a merge commit to combine the histories of both branches.*

---

## Commands to Force Non-Fast-Forward Merge

*If you want to ensure a non-fast-forward merge even when a fast-forward merge is possible, you can use the `--no-ff` option:*

```
git merge --no-ff feature-branch
```
