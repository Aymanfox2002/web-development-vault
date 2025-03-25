
> [!NOTE] Title
> `git config` is a Git command used to configure various settings and preferences for your Git environment. These configurations can be set at different levels and affect how Git behaves for a user or a specific repository.

---

### **Key Levels of Configuration**

1. **System Level**: Applies to all users and all repositories on the system. Typically set in the system-wide Git configuration file, often located at `/etc/gitconfig`.

2. **Global Level**: Applies to all repositories for the current user. The configuration file is usually located at `~/.gitconfig` or `~/.config/git/config`.

3. **Local Level**: Specific to the current Git repository. The configuration file is found at `.git/config` within the repository.

---

## **Commonly Used Configurations**


| <mark class="hltr-g">Configuration</mark> | <mark class="hltr-g">Command</mark>             | <mark class="hltr-g">Description</mark>                                |
| ----------------------------------------- | ----------------------------------------------- | ---------------------------------------------------------------------- |
| User Name                                 | `git config --global user.name "Your Name"`     | Sets the name to be used for all commits by the current user.          |
| User Email                                | `git config --global user.email 'your-email'`   | Sets the email address to be used for all commits by the current user. |
| Default Editor                            | `git config --global core.editor "code --wait"` | Specifies the default text editor for Git.                             |
| Color UI                                  | `git config --global color.ui true`             | Enables colored output in Git commands for better readability.         |
| Alias for Checkout                        | `git config --global alias.co checkout`         | Creates a shortcut for the `git checkout` command.                     |
| Alias for Branch                          | `git config --global alias.br branch`           | Creates a shortcut for the `git branch` command.                       |
| Alias for Commit                          | `git config --global alias.ci commit`           | Creates a shortcut for the `git commit` command.                       |

> [!question]
> If you want local level write the command without `--global` flag
>` git config user.name "Project Specific Name"`

