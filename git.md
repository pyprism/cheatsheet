#### Username 
git config --global user.name "Your Name Here" 
#### Email 
git config --global user.email "your_email@youremail.com"  

#### Password caching 
git config --global credential.helper cache 
###### git will cache your password for 15 minutes
#### Set the cache to timeout after 1 hour (setting is in seconds)
git config --global credential.helper 'cache --timeout=3600'   
#### Enable color output
color-ui =  git config --global color.ui true
git init
git status
git add <filenames>
git commit -m "Add cute octocat story" #add a decribing mesg what i changed
git add '*.tx­t'  # adding all file
git remote add origin <giturl> 
git push -u origi­n maste­r #The name of our remote is origin and the default local branch name is master. The -u tells Git to remember 
                          #the parameters, so that next time we can simply run git push and Git will know what to do. Go ahead and 
                          #push   it!
                          
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
Colored output = git config --global color.ui true
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
                    
 

