Git is popular version control system. It was created by Linus Torvalds in 2005, and has been maintained by Junio Hamano since then.

It is used for:
- Tracking code changes
- Tracking who made changes
- Coding collaboration

It;
- Manages projects with repositories.
- **Clone** a project to work on a local copy.
- Control and track changes with **Staging** and **Committing**.
- **Branch** and **Merge** to allow for work and different parts and version of a project.
- **Pull** the latest version of the project to a local copy.
- **Push** local updates to the main project.
## Configure Git

- Should let know who you are, because each Git commit uses this information.

```bash
git config --global user.name "kabilanma"
git config --global user.email "kabilanen@gmail.com"
```

```global``` set the username and email for every repository and removing the global will set the username and email just for the current repo.

## Initialize Git
First we need a directory or repository to initialize Git on that folder.

```bash
mkdir myproject
cd myproject
```
Or just can direct to the folder where Git has to be initialized.

Initialize the git repository.
```bash
git init 
```
This this initialize the git repository by creating a hidden *.git* folder to keep track of changes.
This will create a default branch name, either master or main, depending on the git version.

To configure the initial branch name to use in all of the future repositories, we configure the settings.
```bash
git config --global init.defaultBranch master
```
This will set the default initial branch name to be **master**.

Right after initializing the git repo (repository) with `git init` we can use the following command to remove the existing branch and create the new branch.

```bash
git branch -m master
```

```bash
git status
```
This command will shows the commits, tracked files and untracked files.

## Adding New Files
We can create some documents that need to be tracked by Git in the initialized directory or we can use the existing files in the directory.

To ask Git to track a file, we use the following command.
```bash
git add <filename>
```

This will start to track the specified filename. Replace `<filename>` with `.` to track everything in the current directory.

This will add the files to the **staging area**.
Staging area is like a middle ground where in where we can selectively choose which changes to include in the next commit. After adding the changes to the staging area, Git recognizes them as *staged* or *to be committed*.

## Git commit


