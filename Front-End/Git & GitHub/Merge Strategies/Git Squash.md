> [!Info]
> **Git squash** is a technique used to combine multiple commits into a single commit.

---
## How does it work?

*I have these commits I would like to combine into one:*

![[Screenshot-2023-03-22-at-11.10.52.png|760x194]]

*To do that run this command:*

```bash
git rebase -i HEAD~6
```

*This will open up your editor of choice for Git. The default is Vim, but in my case, it is VS Code. This is what the editor looks like:*

![[Screenshot-2023-03-22-at-11.28.12.png|868x592]]


Now, you need to replace all those `pick` with `squash` (or simply `s`) apart from the first one.

> [!warning] Note
> **Note:** `pick` or `p` will only use those commits, but `squash` or `s` will use them and combine them all together.

The first commit is the one you will combine them into without losing your changes.

After doing that, save the file and close it with press `Esc` and type `:wq` . Git will open up another editor where you can see the new commit message it generates for you:

![[Screenshot-2023-03-22-at-11.36.02.png|928x680]]

You can remove all of them and add your custom message:

![[Screenshot-2023-03-22-at-11.37.45.png|880x440]]


> [!success] 
> After doing that, you should see a success message in the terminal.



