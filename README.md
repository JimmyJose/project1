bash-3.2$ git --version
git version 1.8.3.4 (Apple Git-47)

bash-3.2$# Create a Git repository
bash-3.2$ git init project1
Initialized empty Git repository in /Users/jimmyjose/dev/sandbox/scratch/project1/.git/

bash-3.2$ cd project1/
bash-3.2$ ls -la
total 0
drwxr-xr-x   3 jimmyjose  staff  102 Feb 21 23:55 .
drwxr-xr-x   4 jimmyjose  staff  136 Feb 21 23:55 ..
drwxr-xr-x  10 jimmyjose  staff  340 Feb 21 23:55 .git

bash-3.2$ git status
\# On branch master
\#
\# Initial commit
\#
nothing to commit (create/copy files and use "git add" to track)

bash-3.2$ cp ../git_activity.log .
bash-3.2$ git status
# On branch master
#
# Initial commit
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#	git_activity.log
nothing added to commit but untracked files present (use "git add" to track)

bash-3.2$ git add git_activity.log 
bash-3.2$ git status
# On branch master
#
# Initial commit
#
# Changes to be committed:
#   (use "git rm --cached <file>..." to unstage)
#
#	new file:   git_activity.log
#

bash-3.2$ git commit -m "My first commit"
[master (root-commit) 1e39ab9] My first commit
 1 file changed, 23 insertions(+)
 create mode 100644 git_activity.log

bash-3.2$ git status
# On branch master
nothing to commit, working directory clean

bash-3.2$ git remote add origin git@github.com:JimmyJose/project1.git
bash-3.2$ git push -u origin master
Warning: Permanently added the RSA host key for IP address '192.30.252.129' to the list of known hosts.

Counting objects: 3, done.
Delta compression using up to 8 threads.
Compressing objects:  50% (1/2)   
Compressing objects: 100% (2/2)   
Compressing objects: 100% (2/2), done.
Writing objects:  33% (1/3)   
Writing objects:  66% (2/3)   
Writing objects: 100% (3/3)   
Writing objects: 100% (3/3), 621 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To git@github.com:JimmyJose/project1.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.

bash-3.2$ git status
# On branch master
nothing to commit, working directory clean

bash-3.2$ mv git_activity.log README.md
bash-3.2$ git status
# On branch master
# Changes not staged for commit:
#   (use "git add/rm <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#	deleted:    git_activity.log
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#	README.md
no changes added to commit (use "git add" and/or "git commit -a")

bash-3.2$ git add . -A
bash-3.2$ git status
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#	renamed:    git_activity.log -> README.md
#

bash-3.2$ git commit -m "Renamed the file to be README.md"
[master ca4edf6] Renamed the file to be README.md
 1 file changed, 0 insertions(+), 0 deletions(-)
 rename git_activity.log => README.md (100%)

bash-3.2$ git push
warning: push.default is unset; its implicit value is changing in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the current behavior after the default changes, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

Counting objects: 3, done.
Writing objects:  50% (1/2)   
Writing objects: 100% (2/2)   
Writing objects: 100% (2/2), 252 bytes | 0 bytes/s, done.
Total 2 (delta 0), reused 0 (delta 0)
To git@github.com:JimmyJose/project1.git
   1e39ab9..ca4edf6  master -> master
