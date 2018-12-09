Small review of git, including

git init: initialize the repo
git add: add a file to staging
git commit: advance repo by one checkpoint
git log: view all checkpoints
git checkout: go to a branch / commit (branch that starts with non-HEAD commit)

History:

1. a8796 -- add app.s
2. c7dc4 -- add cats.js
3. 1a989 -- change cats
4. 94397 -- dogs.js
[5. 2a9bf -- add everything]
[6. ab3a6 -- mistake! (Master's HEAD)] (reverted)
[7. 781f6b -- revert (5) and (6)] (reverted)
8. 2a9bf -- back after revert of revert
[9. ab3a6 -- back after revert of revert] (reverted again!)
10. e813fa -- revert only the mistake


Q. What happens if you check out a commit that isn't the HEAD and then make a commit to that?
A. You get a new branch starting with that commit as the new HEAD (but the branch won't be permanent unless you save it, apparently)

git branch -d <branch name>: delete a branch

Reverting a commit:
(Knowledge from work) One way is to run "git revert <hash>" -- this creates a new commit that gets rid of the offending commit. (The offending commit is still technically part of your repo, so this can create problems down the line if you try to add back that code...)

Our way --

git revert --no-commit <hash>..HEAD

Revert everything from that hash to the HEAD without making individual commits for each reverted commit.