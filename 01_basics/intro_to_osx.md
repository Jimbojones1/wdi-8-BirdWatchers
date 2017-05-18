# Intro to OS X

## Objectives

- Understand what POSIX compliance is
- Get familiar with a UNIX/POSIX folder structure
- Learn how to navigate using the keyboard as much as possible
- Understand why OS X is so popular among web developers and designers

## POSIX Compliance

POSIX stands for Portable Operating System IX. An operating system is POSIX compliant when it maintains compatibility with other operating systems. It does this by:

- Using the same `bash` terminal environment (or similar such as `zsh`)
- Uses predictable, standard path names in its root directory
  - These paths comprise a folder structure that lets you predict where certain kinds of files and programs live
- Maintains a separation between users and the system by separating them on the file system.

POSIX operating systems hold their user's data in `/home` directory where each user gets their own copy of some settings files and programs. This allows for multiple users on a system where each one has different desktop backgrounds for example, different files stored in their Documents folders, etc.

## Keyboard shortcuts

Here are some helpful keyboard shortcuts. Some work across all UNIX-y/POSIX platforms and others are specific to OS X.

- `Cmd + Space` - Spotlight search
- `Cmd  + Shift + 4` - Take a screenshot of a single window (by hovering pressing the space bar) or dragging a square box around the area to be turned into a screenshot
- `Cmd + Alt + Esc` - Pull up a list of programs you can force quit
- `Cmd + C` - Copy text
- `Cmd + X` - Cut text
- `Cmd + V` - Paste text
- `Cmd + Tab` - Switch between open windows or applications

## File Structure

OS X has the root folder structure of a POSIX OS but it's user folder structure live in `/Users/` instead of `/home/users`

## Why do developers prefer OS X?

It's a beautiful operating system that is POSIX compliant. This makes it great for developing and running the same tools on your own computer that you will eventually run on a live web server when you begin hosting your own websites. A bonus is that OS X is great for design with its support for Photoshop, easy to use GUI interface, and other goodies that designers love. OS X is great for "devsigners" - developers who also design the sites they build (similar to full stack developers but not the same).

## Summary

Macs are awesome. As a developer you should get comfortable using the terminal and keyboard and lay off the pointing and clicking with your mouse as much as possible.
