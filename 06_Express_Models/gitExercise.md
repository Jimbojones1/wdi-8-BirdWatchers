## Git Exercise

### Person 1
1. Create a new github repository named 'git-practice'
2. Open the zip file
3. Navigate to the folder unzipped from the .zip in your terminal
4. Run `git init`
5. Run `git add .`
6. Run `git commit -m "first commit`
7. Go back to your repository in Github.com, and run the two commands underneath ""…or push an existing repository from the command line" (git add origin and git push)
8. Refresh your repository and you should see your code.
9. Click on "Settings" in your repository, then 'Collaborators & teams', then add your partner as a collaborator

### Person 2
1. Clone down the project from Github.
2. Check out a new branch of the project named 'heroes'
3. Create a new heroes.hbs file in your views
4. Add `<h1>Heroes</h1>` to the heroes file.
5. Run `git add .`
6. Run `git commit -m "heroes added"`
7. Check out your master branch, and merge in your 'heroes' branch
8. Run `git push origin master` to push the new master branch up to Github

### Person 1

1. Check out a new branch of the project named 'my-views'
2. Create a new heroes.hbs file in your views
3. Add `<h2>Heroes</h2>` to the heroes file.
4. Create a new villains.hbs file in your views
5. Add `<h2>villains</h2>` to the villains file.
6. Run `git add .`
7. Run `git commit -m "heroes and villains added"`
8. Checkout the master branch
9. Pull down the remote master branch
10. Merge in your my-views branch to the master branch
11. Resolve the conflicts and keep the work with the `<h1>` tag.
12. Push the updated master branch to github.

### Person 2
1. Pull down the new changes to your master branch.

### Person 1 and 2

1. Add a model, view, and controller for 'Civilians'. (Only include a GET request in the controller that returns a view that shows all civilians. No need for POST, PATCH, DELETE)
2. Split up the work and complete each piece independently.
3. Use the git workflow to merge the work together and push the master branch to Github.
