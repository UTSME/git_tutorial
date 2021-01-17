# git_tutorial
tutorial on how to conform to the UTS Motorsports git workflow

## Notes
* ssh vs http
* gitk for visual tool
* this tutorial will teach usage around the git bash api, you will be expected to follow and meet rules if you select to use another method of controlling git.
* On windows you will be required to install git bash seperately but on macos and linux you can check the installation of git through command git -h and you should see the help page for using git. if it does not appear then you can install git with a sudo apt install git

## Usage
### Cloning
To begin, you are required to clone down a version of this repoitory. This can be done with either the http or ssh protocal, see above for help setting up an ssh key for your machine. THe following outline the syntax for each protocal

SSH
```git
git clone git@github.com:<GITHUB_USER>/<REPOSITORY_NAME>
```

HTTP
 ```git
git clone https://github.com/<GITHUB_USER>/<REPOSITORY_NAME>
```
THis will create a new directory in your current working directory containing the main/master branch of the upstream repository. change into the repository directory to begin usign git properly.
### Branches
All work is done on branches. By default, you will have a main or master branch depending on when the repository was created (main is now default since 2020). Work should never be done on your master/main because that is where all finished code will end up and ideally this branch will be not be writeable when you try to push code to upstream.

A new branch can be created and then automatically switched to with the following command:
```git
git checkout -b <NAME_OF_BRANCH>
```
The new branch will begin as a carbon copy of the current working branch, ie the latest commit of your previous working branch.

A slightly more complex use case of branch creation is employed when retrieving a prexisting branch from upstream. the following command will create a local branch and set it to track the remote branch upstream to avoid entering a detatched head state.
```git
git checkout -b <NAME_OF_BRANCH> <UPSTREAM_REMOTE_NAME>/<UPSTREAM_BRANCH_NAME>
```
To switch between existing branches, you can use the checkout command without the addition al -b argument like shown below:
```git
git checkout <NAME_OF_BRANCH>
```
- delete a branch
- deleting an upstream branch

### Making Commits
- changes
- stage
- unstage
- discard
- commiting
### Pushing
- pushing
- ensure there is no conflicts else the push will be rejected
- force pushing
### Rebasing
- rebase
- interactive rebase
### Fetching and Pulling
- fetching
- pulling
- beware merge conflicts
### Merge Requests
## Tutorial
