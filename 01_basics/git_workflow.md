# Git Workflow

> The basics of using Git

## Overview

For any Git repository you'll use a standard workflow to save files and push them to a remote repository (usually on GitHub).

## Adding files

The first step in the Git workflow is having files to track. This means that you've created files that you plan to track changes to over time. Whenever you add a new file or change any number of existing files you'll want to add those files as a group to be committed. To do this you run:

```
git add .
```

The `.` means all files from the current directory and all of its subdirectories. If you have changed multiple files and want to commit them separately then you'll want to add each one individually. You can add individual files just by tell git where they are like this:

```
git add example/file1.txt example/file2.txt
```

This will add `file1.txt` and `file2.txt` to be tracked by git. When you're happy with your changes you can commit your work.

## Committing files

Committing files creates a checkpoint in time for whatever files were tracked using the `git add` command. To commit files you will run:

```
git commit -m "Description of my changes"
```

Once you run this command you will have saved what your project looked like at a certain point in time. When you're ready to share your work with others or send it to a remote repository you'll use the `push` command.

## Pushing files

Pushing will send the files to whichever remote repository you want it to go to. To push your committed files you run:

```
git push origin master
```

The push command takes the remote's name and branch as arguments. So `origin master` means push the changes to the remote named `origin` and branch named `master`.


## Creating a branch and putting yourself in it

`git checkout -b branchname`
example: `git checkout -b BobDylan`
