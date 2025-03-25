> [!info]
> The `git clone` command is a fundamental Git operation used to create a copy of an existing repository. This lesson will cover the basics of `git clone`, its usage, and important options that can be configured during the cloning process.

---

## Important Options

| <mark class="hltr-g">Command</mark>                | <mark class="hltr-b">Description</mark>                                            |
| -------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `git clone <repo>`                                 | Clones the repository located at `<repo>` into a new directory.                    |
| `git clone <repo> <directory>`                     | Clones the repository into a specified `<directory>`.                              |
| `git clone --branch <branch> <repo>`               | Clones a specific branch instead of the default branch.                            |
| `git clone --depth 1 <repo>`                       | Creates a shallow clone with only the most recent commit.                          |
| `git clone --bare <repo>`                          | Clones the repository as a bare repository, without a working directory.           |
| `git clone --mirror <repo>`                        | Creates a mirror clone, including all refs and maintaining remote branch tracking. |
| `git clone --template=<template_directory> <repo>` | Clones the repository and applies a template from the specified directory. ❗       |
