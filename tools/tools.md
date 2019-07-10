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