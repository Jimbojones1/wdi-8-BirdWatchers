## Git Commands

### Creating a new branch

`git checkout -b <branch-name>`

### Checking out a different branch

`git checkout <branch-name>`

### Pulling changes into your local branch

`git pull origin <branch-name>`

### Pushing changes to a remote branch

`git push origin <branch-name>`

### Merging a branch

From the branch you would like to merge changes in to, run `git merge`

## Typical Workflow

1. Pull down most recent changes from remote master
2. Checkout a new branch for your feature
3. Do work on that branch and commit
4. Checkout the master branch
5. Pull down most recent changes from remote master
6. Merge feature branch
7. Resolve any conflicts and commit (if conflicts exist)
8. Push your updated master branch to the remote
