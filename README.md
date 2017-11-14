<b>It is tough to work without Git in this world of uncertainities. You never know when you desktop goes down and BOOM you lost all your projects. It is recommended for every developer to be committed to git ;) </b></br>
Git is a software that allows you to keep track of changes made to a project over time. Git works by recording the changes you make to a project, storing those changes, then allowing you to reference them as needed.</br>
To make a (existing) repository into git project: <i>git init</i></br></br>
A git project has three main parts:</br>
1) working directory: this is the place where the user make changes to the file in the project.
2) Staging area: this is the place where all the changes the project are listed.
3) Repository: all latest files/folders are saved as a different version in the project.
</br></br>
In git workflow, changes are made in the working directory, files are added to the staging area and saved in the repository.
</br>
Status of changed files: <i>git status</i></br>
Untracked files mean the files has some changes but git has not started tracking them.</br>
To add a file to staging area: <i>git add filename</i> or <i>git add *</i> to add all files to staging area.</br>
To add multiple files to staging area: <b><i>git add filename_1 filename_2</i></b>.
</br></br>
To unstage a file:  <i>git rm --cache filename</i></br>
To see the changes made to a staged file: <i>git diff filename</i></br>
Commit is the last part of Git workflow. This permanently saves changes in the staging area to repository.</br>
The commit message must be: brief(50 characters or less), in present tense and written under quotation marks.</br>
<i>git commit -m "Initial commit"</i></br>
Git stores commits in a chronologically order in repository. This is helpful when you need to refer to previous versions of your project. The logs can be viewed by <i>git log</i>.</br></br>

<b>Backtracking</b></br></br>
The commit you are currently on is called HEAD commit. To look for changes in it, use <i>git show HEAD</i>. The output is same as <i>git log</i> plus changes made to file.</br>
To revert back to the content before the latest commit: <i>git checkout HEAD filename</i>.</br>
To remove a file from staging area: <b><i>git reset filename</i></b>.</br>
Git log return sha for each commit. The first 7 characters of the sha of last commit can also be used to unstag changes. 
<b><i>git reset 96g12673</i></b></br>