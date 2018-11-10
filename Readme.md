# Git Basic Commands
### Stashing
* Stashing takes the dirty state of your working directory — that is, your modified tracked files and staged changes — and saves it on a stack of unfinished changes that you can re-apply at any time.
`git stash`
* pop to apply the stash and then immediately drop it from your stack.
`git stash pop`
* To apply a stash and remove it from the stash list, run
`git stash pop stash@{n}`
* To apply a stash and keep it in the stash cache, run
`git stash apply stash@{n}`
* To see which stashes you’ve stored
`git stash list`
* To remove or drop any specific stash
`git stash drop stash@{n}`
 * To delete all of your stashes
`git stash clear`

----
### Pull
* Incorporates changes from a remote repository into the current branch
	`git pull`
* Rebase pull
`git pull --rebase`

----
### Add files
* Add one or more files to staging
`git add <filename>`
`git add .`

----
### Commit
* Commit changes to head (but not yet to the remote repository)
`git commit -m "Commit message"`

----
### Push
* Send changes to the master branch of your remote repository
`git push`

----
### Status
* List the files you've changed and those you still need to add or commit
`git status`
* Push code the first time after creating branch
`git push --set-upstream origin meta-tag`

----
### Checkout
* Switch from one branch to another
	`git checkout`

----
### Merge
* To merge a different branch into your active branch
	`git merge <branch name>`

----
### Branch
* List all the branches in your repo, and also tell you what branch you're currently in
`git branch`
* To create new branch
`git branch <new branch name>`
* Delete the specified branch. This is a “safe” operation in that Git prevents you from deleting the branch if it has unmerged changes.
`git branch -d <branch name>`
* Force delete the specified branch, even if it has unmerged changes. This is the command to use if you want to permanently throw away all of the commits associated with a particular line of development.
`git branch -D <branch name>`
* Rename the current branch to <branch>
`git branch -m <branch name>`
* Delete specific branch from remote
`git push origin --delete <branch name>`

----
### Reset
* resets all uncommitted changes you’ve made in your working copy
	`git reset --hard`
* resets a single file
`git checkout -- filename`

----
### Log
* To view the commit history of the current directory
Type q to exit this screen.
    `git log`

----
### Sample commit history
```
`commit af42dfac081b71d1790bfd67f5ed2eefb9ac0440`
`Merge: e5bc173 17ce323`
`Author: user <user@email.com>`
`Date:   Thu May 31 19:52:51 2018 +0530`

`added employment verification and summary generate report`

`commit e5bc17300f5e9ae7127b8d5eeca5b88a62995e56`
`Author: user <user@email.com>`
`Date:   Thu May 31 19:41:03 2018 +0530`

`    added employment verification and summary generated report`

The history shows you, for each commit entry, detailed information about the commit, as well as 40-character checksum hash (e.g., 7a518xxxxxx).
```

* The --oneline flag condenses each commit to a single line. By default, it displays only the commit ID and the first line of the commit message.
`git log --oneline`
* Checkout specific checksum_hash or commit
To checkout a specific version of the current directory
`git checkout <checksum_hash>`
* To checkout a specific version of a file
`git checkout <checksum_hash> <file>`

----
### Graph
* The --graph option draws an ASCII graph representing the branch structure of the commit history.
`git log --graph --oneline`

----
### Diffs
* If you want to see the actual changes introduced by each commit, you can pass the -p option to git log. This outputs the entire patch representing that commit
`git log -p`
* The --stat option displays the number of insertions and deletions to each file altered by each commit
`git log --stat`
* Show changes between commits, commit and working tree
`git diff --name-only`

----
### Filtering the Commit History
* By Amount
`git log -3`
* By Date - the following command only shows commits that were created after July 1st, 2014 (inclusive)
`git log --after="2014-7-1"`
* By Author
`git log --author="John"`

----
### Undo
* To discard changes in working directory
a specific file 
`git checkout -- <file>`
* To discard changes in working directory all files
    `git checkout -- .`
* To discard previous commits
a specific file 
`git checkout -- <file>`
* To discard previous commits all files
	`git checkout -- .`

----
### Changing a commit message
* If a commit message contains unclear, incorrect, or sensitive information, you can amend it locally and push a new commit
`git commit --amend`
