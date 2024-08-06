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

2. git add
----------
The `git add` command is used to add files to the index or staging area,
preparing them for the next commit.

```sh
    git add [<file>]
```
**Description:**

- Staging Changes:
    * When you modify files in your working directory, Git doesn't
      automatically track those changes. You need to explicitly tell Git which changes to include in the next commit.
    * The `git add` command stages changes by adding them to the index
      (also known as the staging area). The index is a temporary storage
      area where you prepare changes for the next commit.
- Usage:
    * To stage specific files, provide their paths as arguments to `git add`. For example:
      ```sh
          git add file1.txt file2.js
      ```
    * You can also stage changes interactively using:
      ```sh
          git add -p
      ```
    * Use `-N` or `--intent-to-add` to stage new files but doesn't actually
      add content changes.
      This is useful when you want to start tracking a new file without
      immediately committing its contents.
      ```sh
          git add -N <filename>
      ```
    * Use `-u` or `--update` to stage modified files and deleted files but not
      new files. This helps avoid accidentally staging new files:
      ```sh
          git add -u
      ```
    * To stage all changes in the current directory and its subdirectories, use:
      ```sh
          git add .
      ```
