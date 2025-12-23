# to setup a config
git config --global user.name "Tarapong Rakked"

git config --global user.email tarapongrakked@hotmail.com

git config --global init.default branch main

git config -h

git help config

git init

git status

git add ., git add --all, git add -A

# to no longer track file
git rm --cached index.html

# create gitignore ".gitignore" to ignore the files.
for example 

# ignore all .txt files
*.txt

git commit -m "explaination for your commit" 

git commit -a -m "explaination for your commit" 
-a including add in one command


git diff

# to restore the stage of the file (working, stage, commit)
git restore --staged index.html

# to remove file
git rm "secret_recipe.html"

# to restore the deleted file
git restore "secret_recipe.html"

# to rename the file
git mv "kcc_logo.png" "kii_logo.png"

# to review all commits that we made
git log

git log --oneline

# to amend the commit
git commit -m "changed file name of an image" --amend

# to show the commit history with the actual code changes.
git log -p

# press q to exit the view

# to jump back to previous commit 
git reset chsadf343ghjhjk (hashtag)

# to opens an interactive rebase starting from the very first commit of the repository
git rebase -i --root

pick a1b2c3d first commit 
pick d4e5f6g add feature A
pick h7i8j9k fix bug

we can change pick to 
- reword -> change commit message
- edit -> modify the commit content
- squash -> merge commits
- fixup -> squash without keeping the message
- drop -> delete a commit

# to create a branch
git branch fix_temp
git switch -c update_temp

# to check branch statusokน
git branch

# to switch to another branch
git switch fix_temp

# to merge branch (you need to stay at the main branch)
git merge -m "merge fix_temp back to main" fix_temp 

# to fix the merge config
- go to the conflicted file, then update the file, then commit it

# to push an existing repository from the command line (to connect existing repo to github that we created)
git remote add origin https://github.com/kkk/kjkl;ajk
git branch -M main
git push -u origin main

# to push all branches to github (you need to connect first)
git push --all

# we can create an issue to raise any ideas to discuss
from github go to Issues tab

# to create a pull request, we need repo owner to approve

# to download code back from cloud to local repo
git fetch 
- then use git merge to merge it to local machine

git pull, combine fetch and merge into one command
