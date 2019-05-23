Quick setup -- if you have done this kind of things before

We recoment every repository include a README, LICENCE and .gitignore


... or create a new repository on the command line

echo "# ngApp6" >> README.md

git init

git add README.md

git commit -m "first commit"

git remote add origin  https://github.com/vineet-cyberkan/ngApp6.git

git push -u origin master




What is Git?

Ans). Version control system (VCS) for tracking changes in computer files 
1) Distributed version comntrol
2) Coordinates work between multiple devevlopers
3) Who made what changes and when
4) Revert back changes at any time
5) Local and remote repos ( reposetries )

Concepts of GIT
1) Keeps track of code history
2) Takes "snapshots" of your files
3) You decide when to take a snapshot of files by making a "commit"
4) You can visit any snapshot at any time
5) You can stage files before commiting


$ git init    // initilize Local Git Repository

$ git add 
$ git add .      // add all file(s) to Index
$ git add <file> // add file(s) to Index

$ git status    // Check status of working tree  ( it will show the diffrence between working tree and staging area )

$ git commit    // commit changes in Index 



// work with remote repository  

$ git push      // push to remote Repository
$ git pull      // pull the latest changes from remote Repository
$ git clone     // clone will copy a remote Repository to current folder 



// Let's start now.

$ git init   

for very first time you have to configure git

$ git config --global user.name 'Your Name'    // to add user name in git configration 
$ git config --global user.name 'Vineet Kumar'    // to add user name in git configration 

$ git config --global user.email 'your email'    // to add user name in git configration 
$ git config --global user.email 'vineet1.st@gmail.com'    // to add user name in git configration 


// to add a file into Git

$ git add <filename>  // to add single file
$ git add .  // to add all files in current directory 

$ git add git.md   // git.md file added to git to check you can use $ git status

$ git status

// if you want to remove cashed file use below given command
"git rm --cached <file>..."

$ git rm --cached git.md

//if now you will check for staus "$ git status" it will return untracked files 

// to commit files use below given command

$ git commit -m "initial commit"    // "-m" stands for master branch  "initial commit" stands for the comment what changes are commited 

// Tips before commting changes don't froget to check status "$ git status"
// it is shows changes then use 
//"$ git add ." to add all files or 
//"$ git add <filename>"  // to add single file

// use of git .gitignore

file name or directory name written in .gitignore will not be commited in git



// What are branches 

For this let's suppose a team is working on multiple modules and you are working for a module that is known as login

then you can create a branch "$ git branch login"
above mentioned command created a new branch but not switched the branch 

you can check it by using "$ git status"

to switch the branch you have to commit your changes on new branch

$ git commit -m "working on login module" 

to switch you branch use 

$ git checkout login   /// 'login' is your branch name 

$ git diff master2 login   //check diffrence between 2 branches
