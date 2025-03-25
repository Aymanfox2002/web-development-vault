> [!Info]
> Cherry-picking in Git allows you to apply a specific commit from one branch to another, without merging the entire branch. This is useful when you want to bring in a specific feature or fix from one branch to another without incorporating all the changes from the source branch.

![[git-cherry-pick-imagem-1.png|788x414]]


---
## How does it work?

```bash
mkdir git-cherry-pick-demo && cd git-cherry-pick-demo
git init -b main
echo "Initial content" > file.txt
git add file.txt
git commit -m "Initial commit"
git checkout -b feature-branch
echo "Feature content part 1" >> file.txt
git add file.txt
git commit -m "Add feature content part 1"
echo "Feature content part 2" >> file.txt
git add file.txt
git commit -m "Add feature content part 2"
git checkout main
git log feature-branch
"Let`t assume the commit hash you want to cherry-pick is abc123"
git cherry-pick abc123
```

---


| <mark class="hltr-g">Command</mark>          | <mark class="hltr-b">Description</mark>                                                                                                                                                                     |
| -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| git cherry-pick --continue                   | If you encounter conflicts during a cherry-pick, Git will pause and prompt you to resolve the conflicts. After resolving the conflicts, you can continue the cherry-pick process with the `--continue` flag |
| git cherry-pick --abort<br>                  | If you want to abort the cherry-pick process and revert to the previous state                                                                                                                               |
| git cherry-pick `start-commit`..`end-commit` | To cherry-pick a range of commits                                                                                                                                                                           |
| git cherry-pick `abc123` `def456` `ghi789`   | To cherry-pick multiple individual commits                                                                                                                                                                  |
