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
To delete a branch locally after it has been merged into master sucessfully use the following command:
```git
git checkout -D <NAME_OF_BRANCH>
```
After a Branch has been deleted locally it can be deleted upstream as well from the terminal with
```git
git push origin :<NAME_OF_BRANCH>
```
the upstream version of a branch can also be deleted on Github or Gitlab after merging


### Making Commits
After completing work you need to make a commit as a form of formal save point in your development cycle. It is important to commit often so that is easy to revert back to earlier states without losing huge amounts of work. making a commit is done in two stages; the first is to stage the appropriate files and the second is to actually make a commit and leave a brief message describing your changes.

The first step in making a commit is to stage files. staging is done with the git add command and follows standardised file slection protocal, ie using the * character to indicate all files that follow a naming pattern. some examples are shown below.

Adding a single file.
```git
git add path/to/file/file.txt
```
Adding a folder.
```git
git add path/to/folder
```
Adding files that follow a specific convention. The first example will add all the .c files within the current directory. The second example will add all the file types called name.
```git
git add *.c
git add name.*
```
Files can also be unstaged if staged accidentally with the following command. It follows the same naming pattern usage as adding a file.
```git
git reset HEAD file_to_unstage.txt
```
At any time changes to files can be discarded with the checkout command. If instead of checking out a branch name and switching branches, you specify the path to a file then all of the local changes made will be automatically discarded. An example is shown below.
```git
git checkout path/to/file/file.txt
```
Finally, once all the appropriate files have been staged, a commit can be made. this is done with the format shown below.
```git
git commit -m "commit message"
```
the -m tag is shown here for ease and is not required but the terminal will open a nano or vim text editor instance for specifying a commit message which is not an intuitive interface for beginners.
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
