# Basic Terminal & Navigating the File System

> Let's get comfortable using terminal commands to work with our computers

## Changing Directories

`cd` changes directories. Running it without arguments will bring you to your user's Home folder.

Passing arguments to `cd` will move you to the directory you specify. So running `cd ~/Sites` will change directories to your `Sites` folder. The `~/` at the beginning of that command tells it to start at the Home folder. The `~` (tilde) character has a special meaning. It references the current user's Home folder. Putting the tilde character in front of any path tells the terminal to interpret the path as starting from the Home folder.

### Moving relative to the current path

Suppose you're in your `~/Sites/` folder (the `Sites` folder in your Home directory) and you want to move back out to the parent folder (which would be the Home folder). You can back out of a directory by using `cd ../`. You can use `../` multiple times to move up the directory tree. Running something like `cd ../../../` would move you up three directories.

## Finding the current path

Running `pwd` will show you the absolute path to the current folder you are in. Your terminal will show you the current path by default but the `pwd` command is useful in cases where you either want to double check that you are where you think you are and when you need to copy and paste a file path.

## Listing files and folders

`ls` is the command that lists files and folders. It takes arguments and flags. The argument it takes is a file path and it will output all the visible files and folders at the path your specified. If you do not give `ls` any arguments then it will list the files and folders at the path you are currently at.

### `ls` flags

Two useful features of the `ls` command are viewing the details (permissions, date created, size, and name) of a file/folder and viewing invisible files.

- `ls -a` - Shows invisible files and folders
- `ls -l` - Lists out the details of all the files and folders in a directory

You can combine flags too:

- `ls -la` will show you the details of all the files and folders in a directory __*including*__ hidden files and folders

