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
####Difference between commits
```
git diff <commit hash> <another commit hash>
git diff WETE6874EWR 54qwertwe6q
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
####Interactive adding
```
git add -i
```
####Removing untracked files from a git repo 
```
git clean -df
```
######You only need to pass -d if you have untracked directories. You only need to pass -f (force) if you have git configured with clean.requireForce set to true, which you likely do.
#####avoid removing files unintentionally, run the following first
```
git clean -n
```
######This is a 'dry run' and it tells you which files git plans on removing before it actually removes them. 
####This will give you options, including removing files that match a pattern.
```
git clean -i
```
####Stash
#####Stash latest changes
```
git stash
```
#####Stash list
```
git stash list
```
#####Stash with message
```
git stash save "Your Boring Message"
``` 
#####Apply latest stash to working directory
```
git stash apply
```
#####Drop stash from list
```
git stash pop stash@{1}
```
#####Drop stash from list
```
git stash drop
```
####Alias
Create alias of git commands
```
git config --global alias.<alias word> <command>
git config --global alias.a add
```

                    
 


