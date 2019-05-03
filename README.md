# Git commands
These commands are assuming that you both have Git installed on your 
local machine and a remote repository service account, whether this is 
Github, Gitlab or Bitbucket it doesnt matter. However these commands are 
for Github so for other services these might be slightly different.

## Repo Setup
Once you have a local directory for your project you can run `git init` 
to initialise the local directory as a Git repository. Note that however 
this isnt connected online.
To connect it to a remote repository so you can share it over the 
internet you have to grab the service link for the Repo, i.e for github 
it will be something like 
`https://github.com/<account-name>/<repo-name>.git`

So you would run `git remote add origin 
https://github.com/<account-name>/<repo-name>.git`

If you have files/directories you do not want to add to the repository 
you can create a .gitignore file and add these files to it and git will 
ignore them.

Its also helpful to create a README.md file in your repo so other people 
looking at the repo know what it is for.

At any point if you want to see the status of the repository enter the 
command `git status`

## Adding
Once you have some files to commit (In Git terminology these are 
referred to as 'Dirty' files)
You need to add these files to the staging environment.
You can do this a couple of different ways.
`git add *` will add every unstaged file to the staging area.

Or you can do `git add <file>` if you wanted to do more than 1 file at a 
time you can just add more files to the command separated by spaces.

## Committing

Once you have files in the staging environment you need to commit these.
To do this run `git commit -m '<message>'` 

Try to make your commits have meaningful messages which explain what 
you're doing at each step so the project is easier to manage. Add 
separate commits by functional intent.

To see a log of the most recent commits on the branch do `git log`

## Pushing

Once you have some commits and want to send them to the remote 
repository enter the command
`git push <remote-name> <branch-name>` in most cases this will end up 
being `git push origin <current-branch-name>` as origin is the default 
remote name in Github. Including the branch name is optional as by 
default this will push to your current branch.

## Pulling

Once there are other commits in the repo and you want to see the changes 
other developers have made. Enter the command
`git pull <remote>` this will pull the changes from the remotes master 
branch into whatever local branch is currently checked out.

If you have multiple remote branches and you want to pull a specific one 
just do `git pull <remote> <branch>`

Usually its easier to do pulls in a desktop application in case you run 
into merge conflicts (which happens a bit when lots of people are 
working on the same area of the code).

## Branches

When working on a project it is easier to manage the repo if you work in 
branches instead of only on the master branch. This way you can test out 
different features and approaches.

To create a new branch and start using it run `git checkout -b 
<branch-name>`

Once you are done working with a specific branch/feature and want to 
merge your changes, you can do this by entering the commands

`git checkout <branch-to-merge-into>`

`git merge <branch-name>`

`git branch -d <branch-name>`

This will switch into the receiving branch, merge the specified branch 
and then delete it.
