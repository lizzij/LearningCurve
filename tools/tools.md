# Git

- check remote ```git remote -v```
- checkout which branch you are on ```git branch```
- switch branches ```git checkout <branchname> ```
- checkout a remote branch ```git checkout <remotebranch>```
- return a list of remote branch ```git branch -r```
- create branch from another branch ```git checkout -b myFeature dev```
- new branches ```git checkout -b <new-branch>```
- delete a branch ```git branch -d <branch-name>```
- undo staged file ```git reset head```
  - unstage a single file `git reset -- <file-name>`
- stage all except one file `git add -u` then `git reset -- <file>`
- change the date of the last commit
    - change last commit date to current date `GIT_COMMITTER_DATE="$(date)" git commit --amend --no-edit --date "$(date)"
` then `git rebase --continue`
    - to arbitrary date `GIT_COMMITTER_DATE="Mon 20 Aug 2018 20:19:19 BST" git commit --amend --no-edit --date "Mon 20 Aug 2018 20:19:19 BST"`
- change commit message `git commit --amend`
- undo commit
  - undo the act of committing, keep staged `git reset --soft HEAD^`
  - undo the act of committing and everything staged, but keep work tree intact `git reset HEAD^`
  - throw away uncommitted changes, reset everything to previous commit `git reset --hard HEAD^`
- recover a deleted git branch `git branch -D <branch>`
  - `git reflog` find the SHA1 for the commit at the tip of the deleted branch
  - `git checkout [sha]` to get to that commit
  - `git checkout -b [branchname]` to recreate the branch
  - (or all in one step) `git checkout -b <branch> <sha>`
- do not commit a file `git rm <file>`
- go back in time `git checkout <sha>`


# Vim

- shift block of code (like Tab) ```// select lines, then >```


### How to do a PR?
- on dev branch start a new feature-branch ```git checkout -b <feature-branch>``` then ```git pull origin dev```
- build the feature
- add necessary test (client side: add/change end-points)
- client and server test (comment out lines 436-445 in ```seqr/settings.py```)
- pull latest dev branch ```git pull origin dev```
- push feature-branch ```git push --set-upstream origin <feature-branch>```
- go to the feature-branch on github and issue a PR pull request to **dev (not master)**
- fix any failing tests and pull + push again
- click "Merge pull request button"
- don't close out ticket until deployed

### zsh and bash
- changes
  - `vim ~/.zshrc` to update changes
  - then run `source ~/.zshrc` after updating changes
- switch from bash <--> zsh
  - `exec bash`
  - `exec zsh`

### pycharm
- press shift twice to search for file in directory

### Quality Control
- formatter
  - Python - Black, Linter, PyLint
  - JS - Prettier, EsLint
- automated test
  - Python - PyLint
  - JS - Jest
- test coverage
  - happy path testing
- version pinning
  - Python `pip freeze`
  - Docker
- documentation
