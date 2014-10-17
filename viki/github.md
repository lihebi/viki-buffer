#github

github search stars:>100

start a new empty branch
`git checkout --orphan <branchname>`
all file are tracked but not commited yet.
`git rm --cached -r .`
untrack all file
`rm -r *`
remove the files.
Now you get the empty branch.

PUll request

1. fork
2. git clone https://github.com/lihebi/xxx
3. cd xxx
4. git remote add upstream https://github.com/origin/xxx.git
5. git fetch upstream
6. git merge upstream/master
7. git add .
8. git commit -m ‘xxx’
9. git push origin master
10. in my repo, create pull request
