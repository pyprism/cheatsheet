#### Username 
```
git config --global user.name "Your Name Here"
```
#### Email
```
git config --global user.email "hiren@mail.com"  
```
#### Password caching
```
git config --global credential.helper cache 
```
###### git will cache your password for 15 minutes
#### Set the cache to timeout after 1 hour (setting is in seconds)
```
git config --global credential.helper 'cache --timeout=3600'   
```
#### Enable color output
```
color-ui =  git config --global color.ui true
```
####Edit default editor
```
git config --global core.editor "nano"
```
###Shortcut way  :D
```
git init
git status
git add <filenames>
git commit -m "Add cute octocat story"
```
#### Add specific pattern 
```
git add '*.txt'
```
#### Only add previously
```
git commit -a
```
####Add commit message using the editor
```
git commit
```
####Add Commit message without the editor
```
git commit -m 'commit mesg'
```
#### Skip the staging part(y) ;)
```
git commit -am 'hiren'
```
####Show difference
```
git diff filename
```
```
git diff HEAD filename
```
```
git diff --staged filename
```
####Show all commit history
```
git log
```
####Commit history statistics
```
git log --stat
```
####Commit history in one line 
```
git log --oneline
```
####Commit history with graph ! (Useful for branches)
```
git log --graph
```
####Commit history of all braches
```
git log --graph -all
```
####Commit history of all braches with brach name
```
git log --graph --all --decorate
```
####Show working and list of all branch
```
git branch
```
####Create a new branch
```
git branch branchName
```
####Switch to branch 
```
git checkout branchName
```
####Shortcut:Create and switch branch
```
git checkout -b brachName
```
#####Marging branch
```
git marge branchName
```
####Delete a branch
```
git branch -d branchName
```
####Rebase
```
git rebase branchName
```
####Remote URL
```
git remote add <name> <giturl>
``` 
####Git push
```
git push -u origi­n maste­r 
```
#####Then for next time
```
git push
```
                          
git reset <filename>      #unstatge file
git branch <branchname>   #for making bruch of main Master brunch
git checkout <branchname> #swicth branch
git rm 'filename'         #remove file from disk
git merge <branchname>    #before u do this go back to the master branch
git branch -d <branchname> #for delete a branch
git push                  # push to remote repo

   =================================================><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>=====================================================
   
 git system level config = git config --system
 git user level config = git config --glbal
 
 set user level username and email  = git config --global user.name "Ashutosh Das"
                                                        git config --global user.email "Your@email.com"
set up default editor = git config --global core.editor "nano"
****See those configuration = git config --list

git auto-completion = curl -OL https://github.com/git/git/raw/master/contrib/completion/git-completion.bash
                                mv ~/git-completion.bash ~/.git-completion.bash
                                nano .bash_profile
                      [code] if [ -f ~/.git-completion.bash ]; then
                                        source ~/.git-completion.bash
                                 fi [code]


initializing repo = git init
add all files = git add .
add file = git add filename
commit = git commit -m "commit mesg"
see all commit messages = git log 
limits the no of commit = git log -n 2
specify date of commit = git log --since=2012-12-12
                                or   git log --until= 2012-12-15

show commit by specific author = git log --author="name"
search commit messages using regex = git log --grep="init"
check status : git status
show diference between files : git deff
delete any file = git rm filenames
rename files = git mv OldFileName NewFileName

add and commit file at same time = git commit -am "commit mesg"  #only usefull for modified files

undo :>>>>>
        git checkout -- filename [ -- means checkout in current branch ]
  undo staged file = git reset HEAD filename
  
  
ignore files = nano .gitignore
                      filenames [we can use regex ]

push to remote host :>>>>
        check remote = git remote
        add remote = git remote add <alias> <url>
        push to remote = git push -u origin master
                    
 


