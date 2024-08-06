Git Commands
------------

1. git init
-----------
The `git init` command initializes a new Git repository in a directory, allowing
you to start tracking changes with Git.

```sh
    git init [<directory>]
```
**Description:**

- Initializes a New Repository:
    * When you run `git init`, it creates a new `.git` subdirectory in the
      current directory (or the specified directory). This `.git` folder
      contains all the metadata and objects required for version control,
      including configuration files, commit history, and other Git-related
      data.
- Sets Up Tracking:
    * The command prepares the directory, for tracking changes and managing
      versions. After initialization, you can start adding files to the
      staging area and committing changes.
- No Arguments:
    * If no `<directory>` is specified, `git init` initializes the
      repository in the current directory.
- With Arguments:
    * If a directory is provided, `git init` will create a new repository in
      that directory, even if the directory does not already exist.
