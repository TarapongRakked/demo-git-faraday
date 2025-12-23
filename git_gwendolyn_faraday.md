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

