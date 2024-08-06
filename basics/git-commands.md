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

3. git commit
-------------
The `git commit` command creates a snapshot of the staged changes, recording
them in the repository's history along with a descriptive message.

```sh
    git commit -m "Commit message"
```

**Description:**

- Committing Changes:
    * After staging changes with `git add`, you can commit them using `git
      commit`.
    * The commit creates a snapshot of the staged changes, which becomes
      part of your project's history.
    * Each commit has a unique ID and an associated commit message, which
      describes the changes made.
- Usage:
    * `-a` or `--all`: Automatically stages all modified and deleted files
      before committing, effectively skipping the `git add` step. However, new
      files are not included.
      ```sh
          git commit -a -m "Commit message"
      ```
    * `--amend`: Allows you to amend the last commit by adding changes to it.
      Useful for making small adjustments to the previous commit without
      creating a new one.
      ```sh
          git commit --amend
      ```
    * `-m` or `--message`: Lets you specify the commit message directly on the
      command line without opening an editor.
      ```sh
          git commit -m "Commit message"
      ```
    * `--no-verify`: Skips pre-commit and commit-msg hooks. Use with caution,
      as it can bypass important checks.
      ```sh
          git commit --no-verify -m "Commit message"
      ```

4. git push
-----------
The `git push` command is used to upload local repository changes to a remote
repository. It updates the remote branch with the commits from the local branch
and can also create new branches on the remote.

```sh
    git push <remote> <branch>
```
**Description:**

- Usage:
    * `-f` or `--force`: Forcefully pushes your changes to the remote
      repository, even if it results in non-fast-forward-updates. This can
      overwrite changes on the remote branch, so use with caution.
      ```sh
          git push -f <remote> <branch>
      ```
    * `--set-upstream` or `-u`: Sets the upstream branch for the current local
      branch for the current local branch. After using this option once, you can
      simply use `git push` without specifying the remote branch.
      ```sh
          git push --set-upstream <remote> <branch>
      ```
    * `<remote> <branch>`: Push to a different branch on the remote repository
      by specifying it after the remote name. For example `git push origin mybranch` pushes the local changes to `mybranch` on the remote repository
      named `origin`.
      ```sh
          git push <remote> <branch>
      ```
    * `--dry-run`: Simulates the push operaion without actually pushing any
      changes. Useful for previewing what would be pushed without modifying the
      remote repository.
      ```sh
          git push --dry-run <remote> <branch>
      ```

5. git pull
-----------
The `git pull` command retrieves and integrates changes form a remote
repository into your local branch.

```sh
    git pull [<remote>][<branch>]
```
**Description:**

- Usage:
    * `<remote>`: The name of the remote repository (e.g., `origin`). If omitted,
      Git defaults to the remote configured for the current branch.
    * `<branch>`: The name of the branch you want to pull from. If omitted, Git
      pulls from the branch configured for the current branch.
    * `<remote> <branch>`: Pull changes from a specific remote and branch. For
      example, `git pull origin main` retrieves changes from the `main` branch
      on the `origin` remote.
      ```sh
          git pull <remote> <branch>
      ```
    * `--rebase`: Instead of merging, rebase the changes from the remote branch
      onto your local branch. This rewrites commit history to create a linear
      progression of commits.
      ```sh
          git pull --rebase <remote> <branch>
      ```
    * `--ff-only`: Only perform the pull if it can be fast-forward, meaning the
      local branch be updated without creating a merge commit.
      ```sh
          git pull --ff-only <remote> <branch>
      ```
    * `--no-commit`: Automatically merge the changes but do not commit them.
      This allows you to review changes before committing.
      ```sh
          git pull --no-commit <remote> <branch>
      ```
    * `--verbose`: Show detailed information about the operations being
      performed during the pull.
      ```sh
          git pull --verbose <remote> <branch>
      ```

6. git status
-------------
The `git status` command displays the state of the working directory and the
staging area. It shows which changes have been staged, which haven't, and which
files aren't being tracked by Git.
```sh
    git status [<options>]
```
**Description:**

- Usage:
    * `-s` or `--short`: Provides a simplified output that is more concise than
      the default format. This is useful for a quick overview.
      ```sh
          git status -s
      ```
    * `-b` or `--branch`: Shows the branch information in the output. This is
      useful if you want to see branch information along with the status.
      ```sh
          git status -b
      ```
    * `--porcelain`: Outputs the status in a machine-readable format, which is
      useful for scripts and tools.
      ```sh
          git status --porcelain
      ```
    * `--untracked-files[=<mode>]`: Controls the display of untracked files. The
      `<mode>` can be `no`, `normal`, or `all` to specify whether to show
      untracked files.
      ```sh
          git status --untracked-files=all
      ```
