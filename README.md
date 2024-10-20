# git add [target]
- Target is a list of files
- The files specified by target will become staged
- Any changes made to staged files will be part of the next commit

# git commit
- Make a commit
- A commit is a list of changes made to your code since the preceding commit
- Commits all point to the commit that precedes them, called the "parent"
- These parent relationships form a chain of changes, called the "ancestors" of that commit

# Branches
- A branch is a label that you can add to a commit

# HEAD
- HEAD is a branch (label) on whichever commit is currently checked out
- When your HEAD points to a branch, that branch is moved to any new commits you make
- When your HEAD points to a commit instead of a branch, it is "detached" and no branches are moved

# [target]^ and [target]~[n]
- Refer to the parent or nth ancestor of target

# git checkout [target]
- Move HEAD to the version of the code at the target
- Target can be a commit hash or a branch name
- If target is a commit hash, then HEAD will point to the commit instead of a branch
- To load your code, git applies all the changes in the ancestor chain, from the first to HEAD, in order

# git checkout -b [target]
- Create and checkout a new branch named target
- Target will point to the commit you where on when you ran this command

# git merge [target]
- Merging creates a new commit on the branch you are currently on
- This merge commit has two parents: the commit you were on when calling merge and target
- This means that when you load this commit, git will apply all the changes from both ancestor chains
- If target is an ancestor of the current commit, then the merge will just move the branch to the new commit

# git rebase [target]
- Change the parent of the current commit to target
- If the current commit is an ancestor of target, then the merge will just move the branch to the current commit

# git reset [target]
- Move the branch at HEAD to target
- Can be used to "undo" a commit by making target HEAD^

# git revert [target]
- Create a commit that undoes all the changes from target
- If this commit comes after target, the commit undoes all those changes
- You can revert any commit at any point, even if target isn't an ancestor of the current commit

# other materials
- https://wizardzines.com/git-cheat-sheet.pdf
- https://wizardzines.com/images/uploads/inside-git.png
