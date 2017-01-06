###README.md

Based on 'Visual Studio Code - Version Control' at https://code.visualstudio.com/Docs/editor/versioncontrol

Based on 'Setting up Github with Visual Studio Code on OSX' at http://michaelcrump.net/using-github-with-visualstudio-code/

#Version Control

Visual Studio Code uses Git for Version Control. Check the version of Git installed as follows, using the integrated terminal (CTRL+'):

```javascript
git version
```

Expected result, similar to:

```javascript
git version 2.8.4.windows.1
```

Make sure you have installed at least version 2.0.0.

##Removing your project from GitHub

Delete the folder '.git' from your project directory.

##Adding your project to GitHub

Switch to your project (e.g. scotch-ng-router) and hit the source control button (i.e. Git Icon). 

The first thing you will see is that your workspace isn’t under git source control.

Press the “Initialize Git Repository” button.

If there are changes listed, include a commit message (i.e. "Initial commit") and finally hit the check mark at the top.

If you navigate back to your project, then you will see a new folder called “.git”. NOTE: Visual Studio Code might hide this folder, therefor look for it in the Windows Explorer instead.

##Your Project is Under Git Source Control, now What?

If you navigate back to your project, then you will see a new folder called “.git”, with inside a config file (config) that contains the following:

```javascript
[core]
	repositoryformatversion = 0
	filemode = false
	bare = false
	logallrefupdates = true
	symlinks = false
	ignorecase = true
```

##Create a Repository on GitHub

Open github.com and create a Repo (e.g. https://github.com/willem-vanheemstrasystems/scotch-ng-router). 

Copy the path to the .git for later use by selecting the "Clone or download" button and use the 'Copy to clipboard' button.

```javascript
https://github.com/willem-vanheemstrasystems/scotch-ng-router.git
```

##Adding the remote repository

Using the (internal) terminal, navigate to the location where your Visual Studio Code project is (e.g. scotch-ng-router) and type the following two commands (replace my .git project with yours):

```javascript
cd scotch-ng-router
git remote add origin https://github.com/willem-vanheemstrasystems/scotch-ng-router.git
```

NOTE: If the remote repository's branch (here: master) is not empty from the start, first do a pull:

```javascript
git pull origin master
```

You can now decide to delete the content that has been pulled, or leave it, by selecting the newly pulled files and folders and deleting them or not. 

Should changes have occured (such as the deletion of previous files), do a commit by typing a message in the textbox of the Git menu followed by clicking the 'V' icon. All changes should disappear from the list.

Now push to the remote branch (here: master).

```javascript
git push -u origin master
```

You should see all files (updated) on the Github for the repository (e.g. https://github.com/willem-vanheemstrasystems/scotch-ng-router). Removed files and folders should no longer show.

##Config file 

If you now examine your .git/config file you will see the following, as the remote repository has been added:

```javascript
[core]
	repositoryformatversion = 0
	filemode = false
	bare = false
	logallrefupdates = true
	symlinks = false
	ignorecase = true
[remote "origin"]
	url = https://github.com/willem-vanheemstrasystems/scotch-ng-router.git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
	remote = origin
	merge = refs/heads/master
```

You can now switch back to Git in Visual Studio Code and perform git operations without using the command line, using the More menu ('...').

##Git Icon

The Git icon on the left will always indicate an overview of how many changes you currently have in your repository. Clicking it will show you the details of your current repository changes: unstaged, staged and unresolved conflicting merge changes.

Clicking each item will show you in detail the textual changes within each file. Note that for unstaged changes, the editor on the right still lets you edit the file: feel free to use it!

##Git Status

You can also find indicators of the status of your repository in the bottom left corner of VS Code: the current branch, dirty indicators and the number of incoming and outgoing commits of the current branch. You can checkout any branch in your repository by clicking that status indicator and selecting the Git reference from the list.

##Git Commands

See for detailed instructions as to how to use Git commands https://code.visualstudio.com/Docs/editor/versioncontrol
