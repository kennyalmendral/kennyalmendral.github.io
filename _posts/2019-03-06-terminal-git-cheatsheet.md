---
layout: post
title: Terminal and Git Cheatsheet
---

Just another terminal and git cheatsheet.

## Terminal Commands

**cd** - Change directory, e.g. `cd ~/Desktop` where `~` simply means the current user's home directory followed by a trailing slash `/` and then go to the `Desktop` folder.

+ Both `cd` and `cd ~` goes to the current user's home directory.
+ `cd -` goes back to the previous directory.
+ `cd /` goes to the root directory of the drive.
+ `cd ../` goes to the parent directory of the current directory.

**ls** - List directory, e.g. `ls ~/Desktop` which lists all the files and folders inside the `Desktop` folder.

+ Both `ls` and `ls .` lists the contents of the current directory. The `.` refers to the current directory.
+ `ls -l` lists the contents of a directory in a more readable format.
+ `ls -a` lists the contents of a directory including hidden files and folders.
+ `ls -la` lists the contents of a directory in a more readable format including hidden files and folders.

**clear** - Clears the terminal screen. Another way is by pressing `Ctrl + l`.

**pwd** - Prints the absolute path of the current working directory to the terminal screen.

**open** - Opens a file, e.g. `open index.html` where `index.html` is the name of the file.

**cat** - Outputs the contents of file, e.g. `cat index.html` to the terminal screen.

**touch** - Creates a new file, e.g. `touch index.html` where `index.html` is the name of the file.

**mkdir** - Creates a new folder, e.g. `mkdir assets` where `assets` is the name of the folder.

**rm** - Removes a file, e.g. `rm index.html` where `index.html` is the the name of the file.

**rm -r** - Removes a folder and it's contents, e.g. `rm -r assets` where `assets` is the the name of the folder.

**cp** - Copy file to file, e.g. `cp ~/Downloads/index.html ~/Desktop/index.html` where the `~/Downloads/index.html` is the source file and the `~/Desktop/index.html` is the destination file.

+ To copy a file to a directory, use `cp index.html ~/Desktop` where `index.html` is the source file and the `~/Desktop` is the destination folder.
+ The destination file can be renamed, e.g. `cp ~/Downloads/index.html ~/Desktop/about.html` where the `~/Downloads/index.html` is the source file and the `~/Desktop/about.html` is the destination file but with a different file name.

**cp -R** - Copy folder to folder, e.g. `cp ~/Downloads/assets ~/Desktop/assets` where the `~/Downloads/assets` is the source folder and the `~/Desktop/assets` is the destination folder.

+ The destination folder can be renamed, e.g. `cp ~/Downloads/assets ~/Desktop/images` where the `~/Downloads/assets` is the source folder and the `~/Desktop/images` is the destination folder but with a different folder name.

**mv** - Same with the `cp` command, the only difference is that it moves/cuts a file instead of copying.

**mv -R** - Same with the `cp -R` command, the only difference is that it moves/cuts a folder instead of copying.

**grep** - Searches the contents of a file using a "search string", e.g. `grep 'Hello World' index.html` where `'Hello World'` is the search string and `index.html` is the file being searched.

**grep -r** - Searches the contents of a folder using a "search string", e.g. `grep -r '.heading' assets` where `'.heading'` is the search string and `assets` is the folder being searched.

+ To search the contents of the current directory, use `grep -r 'Hello World' .` where `'Hello World'` is the search string and the `.` _(which points to the current directory)_ is the folder being searched.

## Git Commands

**git clone** - Clones an existing repository to the current directory, e.g. `git clone https://bitbucket.org/user/repo/` where `https://bitbucket.org/user/repo/` is the remote repository source URL.

+ To clone a remote repository to a different directory, use `git clone https://bitbucket.org/user/repo/ ~/Desktop` where `~/Desktop` is the folder name.

**git init** - Creates a local repository inside a folder.

+ This folder will be called as the "working directory".
+ The working directory is basically where the unstaged changes resides.

**git status** - Checks the status of a local repository if there are uncommitted changes or if there aren't.

**git add** - Adds a modified file or folder to the next commit, e.g. `git add index.html` or `git add assets` where `index.html` is the modified file and `assets` is the modified folder.

+ Use `git add .` to add all the changes to the next commit.

+ Every added files/folders are moved to the "staging area".

**git commit** - Commits the added changes with a commit message using the `-m` flag, e.g. `git commit -m "Initial commit"` to the local repository.

+ Every commit creates a "commit hash" which is basically a unique ID for a particular commit.

**git log** - Lists all the commits in a local repository.

+ Use `git log --oneline` to list all the commits in a compact format.

**git remote -v** - Lists the remote repository URL that your local repository is currently pointing to.

+ If there's no remote repository found, use `git remote add "https://bitbucket.org/user/repo/"` where `https://bitbucket.org/user/repo/` is the remote repository URL.

**git push** - Push local repository changes/commits to the remote repository.

+ To push without needing to log in every time, enter the following on the terminal: `git config --global user.name "user"` and `git config --global user.email "user@gmail.com"`. Replace the `"user"` and `"user@gmail.com"` with your username and email of course.

**git pull** - Download changes/commits from the remote repository to the local repository.

+ To pull without needing to log in every time, enter the following on the terminal: `git config --global user.name "user"` and `git config --global user.email "user@gmail.com"`. Replace the `"user"` and `"user@gmail.com"` with your username and email of course.

**git reset** - Discard local changes.

+ Use `git reset --hard HEAD` to discard all local changes in your working directory.
+ Use `git reset --hard` to reset your HEAD pointer to a previous commit and discard all the changes since then, e.g. `git reset --hard d53fea1` where `d53fea1` is the commit hash.
+ To discard local changes in a specific file, use `git checkout HEAD` followed by the file name instead, e.g. `git checkout HEAD index.html` where `index.html` is the name of the file.
+ The _HEAD_ is a pointer that refers to the currently active commit.

#### Notes

+ Press the `Tab` key to auto-complete file and folder names.

+ Try to make every commit message descriptive af. Use present tense if possible, e.g. `git commit -m "Add index.html"`.

---
