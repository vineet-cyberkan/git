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






++++++++++++++++++++++++++ please have a look start ++++++++++++++++++++++++++++++++++

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git checkout login
Switched to branch 'login'

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (login)
$ git checkout master
error: Your local changes to the following files would be overwritten by checkout:
        git.md
Please commit your changes or stash them before you switch branches.
Aborting

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (login)
$ git commit -m "working on login module added new branch 'login'"
On branch login
Changes not staged for commit:
        modified:   git.md

no changes added to commit

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (login)
$ git add .

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (login)
$ git commit -m "working on login module added new branch 'login'"
[login 4000c28] working on login module added new branch 'login'
 1 file changed, 23 insertions(+)

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (login)
$ git checkout master
Switched to branch 'master'


++++++++++++++++++++++++++ please have a look end++++++++++++++++++++++++++++++++++


// Git merge

to merge branches use "$ git merge <branchname>"

$ git merge login


$ git branch   // to see all the branches



+++++++++++++++++++++++++++++++ commands examples start +++++++++++++++++++


vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master2)
$ git status
On branch master2
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        git.md

nothing added to commit but untracked files present (use "git add" to

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master2)
$ git add .

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master2)
$ git commit -m "master2 branch created"
[master2 3e08475] master2 branch created
 1 file changed, 148 insertions(+)
 create mode 100644 git.md

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master2)
$ git status
On branch master2
nothing to commit, working tree clean

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master2)
$ git checkout loin
error: pathspec 'loin' did not match any file(s) known to git

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master2)
$ git checkout login
Switched to branch 'login'

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (login)
$ git merge master2
Updating db1c462..3e08475
Fast-forward
 git.md | 148 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 148 insertions(+)
 create mode 100644 git.md

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (login)
$ git branch
* login
  master
  master2

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (login)
$ git status
On branch login
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   git.md

no changes added to commit (use "git add" and/or "git commit -a")

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (login)
$ git add .

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (login)
$ git commit -m "git.md added to login branch"
[login faa0d56] git.md added to login branch
 1 file changed, 6 insertions(+)

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (login)
$ git status
On branch login
nothing to commit, working tree clean

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (login)
$ git checkout master2
Switched to branch 'master2'

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master2)
$ git status
On branch master2
nothing to commit, working tree clean

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master2)
$ git checkout master
Switched to branch 'master'

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git status
On branch master
nothing to commit, working tree clean

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git merge master2
Updating db1c462..3e08475
Fast-forward
 git.md | 148 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 148 insertions(+)
 create mode 100644 git.md

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$



+++++++++++++++++++++++++++++++ commands examples end +++++++++++++++++++









vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git add .

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   README.md


vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git commit -m "updated readme.md file"
[master 78b6e2e] updated readme.md file
 1 file changed, 25 insertions(+)

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git fetch

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git fetch git
warning: no common commits
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), done.
From https://github.com/vineet-cyberkan/git
 * [new branch]      master     -> git/master

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git branch
  login
* master
  master2

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git status
On branch master
nothing to commit, working tree clean

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git push -u git master
To https://github.com/vineet-cyberkan/git.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'https://github.com/vineet-cyberkan/git.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git pull
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=git/<branch> master


vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git pull git master
From https://github.com/vineet-cyberkan/git
 * branch            master     -> FETCH_HEAD
fatal: refusing to merge unrelated histories

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git pull git login
fatal: couldn't find remote ref login

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git pull git master --force
From https://github.com/vineet-cyberkan/git
 * branch            master     -> FETCH_HEAD
fatal: refusing to merge unrelated histories

vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git pull --rebase
There is no tracking information for the current branch.
Please specify which branch you want to rebase against.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=<remote>/<branch> master


vineet.kumar@Nvineetkumar MINGW64 /e/work/Git_for_biggners (master)
$ git pull git master --rebase
From https://github.com/vineet-cyberkan/git
 * branch            master     -> FETCH_HEAD
First, rewinding head to replay your work on top of it...
Applying: creating a doc for git biggners
Applying: initial commit
Applying: initial commit
Applying: discription added to about the commit command
Applying: git ignore file added
Applying: working on login module added new branch 'login'
Applying: working on login module added new branch 'login'
.git/rebase-apply/patch:23: trailing whitespace.
// What are branches
.git/rebase-apply/patch:28: trailing whitespace.
above mentioned command created a new branch but not switched the branch
.git/rebase-apply/patch:34: trailing whitespace.
$ git commit -m "working on login module"
.git/rebase-apply/patch:36: trailing whitespace.
to switch you branch use
.git/rebase-apply/patch:38: trailing whitespace.
$ git checkout login   /// 'login' is your branch name
warning: 5 lines add whitespace errors.
Using index info to reconstruct a base tree...
M       git.md
Falling back to patching base and 3-way merge...
Auto-merging git.md
CONFLICT (content): Merge conflict in git.md
error: Failed to merge in the changes.
hint: Use 'git am --show-current-patch' to see the failed patch
Patch failed at 0007 working on login module added new branch 'login'
Resolve all conflicts manually, mark them as resolved with
"git add/rm <conflicted_files>", then run "git rebase --continue".
You can instead skip this commit: run "git rebase --skip".
To abort and get back to the state before "git rebase", run "git rebase --abort".
