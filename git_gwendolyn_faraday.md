# basic git command
git clone
git add .
git commit 
git push
git pull

# git push -u origin master
- origin -> to set the origin of the repo
- "-u" is the upstream, to default the connection, just type 'git push' next time.

# make a cloud connection
git remote add origin git@github.com:xxx
- remote -> remote connection, not local.

# to check the remote repo that connected to local repo
git remote -v

# git branching
feature branch and hot-fix branch is important. 
git branch 
git checkout -b feature-readme-instruction
git checkout master, to switch back to master branch

# to see the different between branch
git diff xxx
To compare different commits in Git, you have several options. Here are the most common ways:
1. Compare any two commits directly
Using git diff:
bash

# Compare 4th commit to 3rd commit
git diff HEAD~1 HEAD          # Latest vs previous
git diff <commit3-hash> <commit4-hash>

# Compare 4th commit to 2nd commit
git diff HEAD~2 HEAD
git diff <commit2-hash> <commit4-hash>

# Compare 4th commit to 1st commit
git diff HEAD~3 HEAD
git diff <commit1-hash> <commit4-hash>

Get commit hashes first:
bash

git log --oneline
# Example output:
# abc1234 (HEAD) 4th commit message
# def5678 3rd commit message
# ghi9012 2nd commit message
# jkl3456 1st commit message

Then use those hashes:
bash

git diff jkl3456 abc1234  # 1st vs 4th
git diff ghi9012 abc1234  # 2nd vs 4th
git diff def5678 abc1234  # 3rd vs 4th

2. Using relative references
bash

# HEAD is the latest commit (4th)
git diff HEAD~1 HEAD    # 4th vs 3rd
git diff HEAD~2 HEAD    # 4th vs 2nd  
git diff HEAD~3 HEAD    # 4th vs 1st

# You can also use:
git diff HEAD^^^ HEAD   # 4th vs 1st (3 carets = 3 commits back)
git diff HEAD^^ HEAD    # 4th vs 2nd (2 carets = 2 commits back)

3. View changes for specific files only
bash

# Compare specific file between commits
git diff HEAD~2 HEAD -- filename.txt
git diff <commit2-hash> <commit4-hash> -- path/to/file.py

4. See what changed in each commit (statistics)
bash

# Show file changes with stats
git diff HEAD~3 HEAD --stat      # Shows which files changed
git diff HEAD~2 HEAD --name-only # Shows only filenames

# See number of lines added/removed
git diff HEAD~1 HEAD --shortstat

5. Compare using Git GUI tools

If you prefer visual comparison:
bash

git difftool HEAD~1 HEAD    # Opens in configured diff tool
git difftool HEAD~2 HEAD

6. Compare branches with commits

If you want to compare commits across branches:
bash

git diff main~3 HEAD   # Compare 4th commit (current) to 1st commit on main

Practical Example

Let's say you have this commit history:
text

a1b2c3d (HEAD) Add feature C
e4f5g6h Add feature B
i7j8k9l Add feature A
m1n2o3p Initial commit

Compare commits:
bash

# See what changed in the last commit (feature C)
git diff e4f5g6h a1b2c3d

# See all changes from initial to current
git diff m1n2o3p HEAD

# See what changed between feature A and feature C
git diff i7j8k9l HEAD

Pro Tip: Create aliases for frequent comparisons

Add to your ~/.gitconfig:
ini

[alias]
    diff-prev = diff HEAD~1 HEAD
    diff-two = "!f() { git diff $1 $2; }; f"

Then use:
bash

git diff-prev      # Compare with previous commit
git diff-two abc123 def456  # Compare any two commits

Summary

    git diff <older-commit> <newer-commit> - Most flexible

    git diff HEAD~n HEAD - Quick relative comparisons

    Add -- <filename> to limit to specific files

    Use git log --oneline first to see commit hashes

Remember: The order matters! git diff A B shows what you need to change in A to get to B.


xxx -> branch name.

# to combine branch
git merge xxx

xxx -> branch name.

common practice is to go back to the branch that you want to take to the main branch, then 
git status
git push

# pull request (PR)
to pull your code from one branch to another branch. onece we make a PR, anyone can review on it and make a comment. to make changes and update. after making PR, you can still change a code, by making another commit. 
Once the PR is merged, it will delete the branch. If you want to make another changes, you need to create a new branch. 

# to pull code from github
git pull
git pull origin master
git pull -u origin master

# to delete branch
git branch -d feature-instruction

# git conflict
if we update in master, you can to commit the changes before moving to another branch, otherwise, it will be an error for being overwritten by checkout. 

# to undo
to unstage 
git reset 

te uncommit 
git reset HEAD~1

HEAD -> head means the latest commit 
~1   -> step back to one commit further

you can use git log to get the hash number then use git reset to go back to particular commit stage.

# to delete the commit
git reset --hard xxxxx
xxx -> hash number
* hard is not unstaged, but it completely removed.

# to see the commits
git log
git log --oneline

# git fork
you can fork it from github.

git fork is to clone repo to your own repo including branches associated with it.