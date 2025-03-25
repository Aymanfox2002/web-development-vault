> [!Info]
> A **fast-forward merge** occurs when the branch you're merging into (the target branch) is directly ahead of the branch you're merging from (the source branch). In simpler terms, there are no new commits on the target branch since the source branch diverged from it. Git simply moves the target branch's pointer to the latest commit of the source branch

---

### How Does It Work?

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
git merge feature-branch
```

*Since there were no new commits on the `main` branch while you were working on `feature-branch`, Git performs a fast-forward merge.*