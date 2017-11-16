## GIT BASICS
It is tough to work without Git in this world of uncertainities. You never know when you desktop goes down and BOOM you lost all your projects. It is recommended for every developer to be committed to git ;)
>Git is a software that allows you to keep track of changes made to a project over time. Git works by recording the changes you make to a project, storing those changes, then allowing you to reference them as needed.

To make a (existing) repository into git project: 
```git
git init
```
A git project has three main parts:
1. Working directory: this is the place where the user make changes to the file in the project.
2. Staging area: this is the place where all the changes the project are listed.
3. Repository: all latest files/folders are saved as a different version in the project.

>In git workflow, changes are made in the working directory, files are added to the staging area and saved in the repository.

Status of changed files: 
```git
git status
```
Untracked files mean the files has some changes but git has not started tracking them.
To add a file to staging area: 
```git
git add filename
```
or 
```git
git add *
``` 
or
```git
git add .
``` 
or 
```git
git add filename_1 filename_2
```

To unstage a file:  
```git
git rm --cache filename
```

To see the changes made to a staged file: 
```git
git diff filename
```

Commit is the last part of Git workflow. This permanently saves changes in the staging area to repository. The commit message must be: brief(50 characters or less), in present tense and written under quotation marks.
```git
git commit -m "Initial commit"
```
Git stores commits in a chronologically order in repository. This is helpful when you need to refer to previous versions of your project. The logs can be viewed by:
```git
git log
```

### Backtracking
The commit you are currently on is called __HEAD__ commit. To look for changes in it:
```git
git show HEAD
```
The output is same as _git log_ plus changes made to file.
To revert back to the content before the latest commit:
```git
git checkout HEAD filename
```
There is a shortcut to this command:
```git
git checkout -- filename
```
To remove a file from staging area: 
```git
git reset filename
```
Git log return sha for each commit. The first 7 characters of the sha of last commit can also be used to unstag changes. 
```git
git reset 96g12673
```

### Git Branching
The default branch that we work is _master_. Git provides option to create branches to experiment with versions of the project. The main project will be _MASTER_ branch. The other branches need to merged to MASTER to update the main repository. New branch is a different version of the Git project. It will have all commits from MASTER. To check the current branch:
```git
git branch
```
The output will be the list of all branches with asterisk(*) mark on the current branch. To create a new branch:
```git
git branch new_branch
```
To switch to another branch:
```git
git checkout branch_name
```
After switching, staging and commiting is done in the same way as before. To merge the changes with MASTER branch, first switch to master branch using _git checkout master_, then:
```git
git merge branch_name
```
There will be merge conflicts if the same file is editted in master as well as any other. 
Many branches can be created in a Git project. But, the end requirements reflecting all changes into the _master_ branch. After merging the branches can be deleted:
```git
git branch -d branch_name
```

### Working with collaborates

>A __remote__ is a shared Git repository that allows multiple collaborators to work on the same Git project from different locations. Collaborators work on the project independently, and merge changes together when they are ready to do so. 

To contribute to a remote project, the project first needs to be cloned to local. This is done as:
```git
git clone remote_location clone_name
```
_repo_location_ is address of the place where the repository is. It can be a file path or URL. _clone_name_ is the name of the directory where Git project is cloned.
To clone a repository