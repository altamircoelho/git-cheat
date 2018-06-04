# • Add Origin
### - Sync your local repo to a RE-NAMED repo on github
`git remote set-url origin https://github.com/rimatla/repo_name.git`

### - Add a new dir project to an existing (previously created) repo
`git remote add origin https://github.com/username/repo_name.git`

### - Find what remote url owns a given repo
`git remote show origin`


# • README
### - Hyperlinks
`[CakePHP](http://www.cakephp.org) - The rapid development PHP framework`

### - Images
`![alt text](app.png?raw=true "app image")`

### - Write text with "code syntax" on README.md
#### See ex: `myCode.js`.



# • CLONE
### - Clone repo from a specific commit ie: first commit 
`git clone --depth=1 https://github.com/angular/angular-seed.git <your-project-name>`



# • COMMITS
### - Stage and commit 
`git commit -a -m 'message'`

### - Fixes typos on last commit messages 
`$ git commit --amend -m 'new message'`

### - Undo commit
`git reset HEAD~`

### - Rollback a github repository to a specific commit
`git reset --hard 'your_commit_id'`
`git push -f -u origin master `


# • DELETE
### - Delete file from repo
`git rm file_name`

### - Permanently Delete a repo, caution with `rf`
`rm -rf .git`

### - How to remove a dir ex: `.idea or node_modules` from existing github repo.
`git rm -r --cached .idea`

### - Create and/or remove files
```` 
echo '.idea' >> .gitignore,
git rm -r --cached .idea,
git add .gitignore,
git commit -m 'your msg',
git push 
````

### - Undo a git init
#### If you just inited it, you can just delete it:
`rm -rf .git`


# • PUSH
### - Force a push to master branch
`git push -f -u origin master`

# • BRANCHES
### - Create and checkout branch 
`git checkout -b <branch-name>`

### - Delete a branch
`git branch -d <branch-name>`

### - Create a branch 
 `git branch <branch-name>`

### - Checkout a Branch
`git checkout <branch_name>`

### - List Remote Branches
`git branch ls-remote`
`git branch -a`

### - Fetch Newly Created Branches
`git fetch`

### - List Current Branch
`git branch`


# • LOG
### - To see log and commits on a branch graph
`git log --all --decorate --oneline  --graph`

### - One Line Log
`git log --oneline`

### - Log History
````
git log
git log <filename>
````

# • DIFF
### - See changes before commit
`git diff`
#### hit enter
#### q ends it

### - See differance between master and local branch before merging 
`git diff master ..branch-name`


# • VIM
#### - To save: type  `:wq`, then press enter
#### - To quit: type  `:q!`, then press enter


# • Linux Commands
### - print file on cli
`cat file_name`

### - create new dir and file at the same time
`mkdir name && touch name/file.js`

### - remove a file
`rm file_name`

### - remove a dir
`rm -r dir_name`

### - to move files
`mv file_name path`


# • Merge and/or Discard
### - Discard Changes to file
`git checkout -- file_name`

### - Discard Changes to all files
`git checkout -- .`

### - Unstage a added file
`git reset HEAD file_name`

### - Fast Forward Merge
````
git checkout master
git merge branch-name
````

### - Certify what branches were merged 
`git branch --merged`

### - 3-way Merge
`git merge branch-name`

# • Merge Conflicts 
### - Abort a merge during a merge conflict situation
`git merge --abort` 

### - Checkout a commit directly, not through a branch, results in a detached HEAD state
`git checkout (commit-hash)`

## - Merging changes from a remote branch
### - Make sure you have the latest data from upstream
` git fetch upstream`

### - Create and switch to a new branch based on master to explore the conflict
`git checkout -b explore-conflict upstream/master`

### - Now try merging the unmergeable-branch into it
`git merge upstream/unmergeable-branch`

### - Fix Conflits, then:
`git add file-name`,
`git commit -m "fixed conflict"`

ps: Create new branches when resolving conflicts
- Branches are cheap and disposable.
- Rather than risk messing up the branch you’ve been working on, create a new one specially for the purpose of discovering what sort of conflicts arise, and to give you a place to work on resolving them without disturbing your work so far.


# • STASH
### - Save changes for later use
`git stash`

### - See list of stashed changes
`git stash list`

### - See all edits done on previous stashes points
`git stash list -p`

### - Apply stashed changes (applies the most recent one)
`git stash apply`

### - Apply a specific stashed change
````
git stash list
git stash apply <label-name>
````

### - Discard a stash
`git stash pop`

### - Add message w/ stash
`git stash save "message"`

# • PULL
### - Pull all changes
`git pull --all`

### - Incorporate upstream changes
````
git checkout master
git fetch
git merge origin/master
````

# •
PS: Note that here instead of **git fetch** followed by **git merge**, you could have run **git pull**. The pull operation does two things: it fetches updates from your GitHub fork (origin), AND merges them. However, be warned that occasionally git pull won’t always work in the way you expect, and doing things the explicit way helps make what you are doing **clearer**. git fetch followed by git merge is generally the **safer** option.


# • Workflow
`fork > clone > branch > edit > stage > commit > push > pull request > merge`

## ps:
### - When you ready to push, do it from your local branch
 `push origin <local-branch>`

 ### - Send pull request `from` your local branch
 ### - Keeping master ‘clean’

You could of course have **merged** your new **branch** into your **master** branch, and sent me a **pull request from that**. But, once again, it’s a good policy to **keep** __your master branch__, on GitHub too, **clean** of changes you make, and only to pull things into it from **upstream**.

In fact the same thing goes for other branches on my upstream that you want to work with. Keeping them clean isn’t strictly necessary, but it’s nice to know that you’ll always be able to pull changes from upstream without having to tidy up merge conflicts.



# • Obscure Errors
##### - Remote rejected (shallow update not allowed) ERROR
##### - This means that you have to unshallow your repository. To do so you will need to add your old remote again.
`git remote add old <path-to-old-remote>`

#### - After that we use git fetch to fetch the remaining history from the old remote
`git fetch --unshallow old`

# • Alias Examples
``
alias gs='git status '
alias ga='git add '
alias gb='git branch '
alias gc='git commit'
alias gd='git diff'
alias go='git checkout '
alias gk='gitk --all&'
alias gx='gitx --all'
``

# • Work flow
`git branch`
`git checkout master`
#### Once on master and ready to pull updates, use the following:
`git fetch`
`git merge origin/master`
#### Now that I am all up to date with the remote repo, I'll create a branch
`git checkout -b branch-name`
`git branch`
#### Edit and commit 
`git commit -am 'my message in present tense'`
#### Push local branch
`git push origin branch-name`
#### Tracking remote branches
`git branch -r`
#### To keep my local repo 100% in sync with deleted remote branches, I make use of this command:
The -p or --prune flag, after fetching, will remove any remote-tracking branches which no longer exist.
`git fetch -p`

#### Pull request - Once the reviewer has approved the editors updates...
`git checkout my-feature-branch`
`git pull origin branch-name`

#### Make sure that the feature branch is up to date with master, while in the feature branch, execrate the following:
`git pull origin master`

#### Now that I know that the feature branch is up to date with the remote repo and that it has the latest code from master, I can now merge these branches
`git checkout master`
`git pull origin master`
`git merge --no-ff my-feature-branch`

Notice the --no-ff flag in the merge command. This flag keeps the repo branching history from flattening out. If I were to look at the history of this branch, using GitX for example, when using the --no-ff flag, I will see the appropriate bump illustrating the history of the feature branch. This is helpful information. If I didn't use this flag, then Git will move the commit pointer forward.

#### Now that I have merged the code, the feature branch by definition is obsolete. First, delete the branch from the local repo.
`git branch -d branch-name`

### Finally...
#### If the feature branch was pushed to the repo, as it should have been per the workflow we described, you will want to delete this from the remote repo as well...
`git push origin --delete my-feature-branch`

#### PS: My branch was rejected?
This is a special case when working on a team and the branch I am are pushing is out of sync with the remote. To address this, it's simple, pull the latest changes:
`git pull origin branch-name`

✌️✌️