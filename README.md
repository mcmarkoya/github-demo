## GitHub Demo Repo
This is a demo of how to work with Github

This is a new line

# About the Project
**Some description**

# Resources
data not available 

# add file to staging
git add REPORT.md
git add . (add all of the changed files)

# restore or reset from staging
git restore --staged REPORT.md
git reset . (reset all changed files)

# check status
git status

# commite changes
all commits need a message, stating what changes you made.
git commit -m "update git notes"
**it will ask you who you are**
git config --global user.email "you@example.com"
git config --global user.name "myname" (this is your Github username)

**when committing without a message**
it will prompt you to type a message, then you will need to press "Esc" and then type :wq to exit the editor.
w means write, q means quit

# view your previous commits
git log
(or concise version)
git log --oneline

when the log shows, usually there is a colon after the log. You will need to type q in the command to quit the log.

# go back to a previous commit
git checkout (hashcode of the commit you want to stay)
e.g. git checkout b02bece

# undoing changes
git reset --soft hashcode 
(soft means you still can keep it if you want to get it back)
git reset --hard hashcode 
(hard measn completly getting rid of it)

# detached head --how to fix
Detached head means you are no longer on a branch, you have checked out a single commit in the history (in this case the commit previous to HEAD, i.e. HEAD^).

If you want to keep your changes associated with the detached HEAD
Run **git branch tmp** - this will save your changes in a new branch called tmp.
Run **git checkout master** - if you are in main branch, run **git checkout main**
If you would like to incorporate the changes you made into master, run **git merge tmp** from the master branch. You should be on the master branch after running git checkout master.
If you want to delete your changes associated with the detached HEAD
You only need to checkout the branch you were on, e.g.

**git checkout master** or **git checkout main**
Next time you have changed a file and want to restore it to the state it is in the index, don't delete the file first, just do

git checkout -- path/to/foo
This will restore the file foo to the state it is in the index.

# .gitignore file
Keeps the records of the files that we do not want Git to track.

1. create the files to be ignored
2. run git status, you will see the files untracked
2. create a .gitignore file
2. type in the files or folders that we want Git to ignore, for example:
    .env
    data/ --if this is a folder to be ignored, alwasys add / after the folder name
    notes.txt
3. run git status again, and you will now only see the modified .gitignore file. The other files are hidden.

# push changes onto Github
git push -u origin main
-u means the upstream

# Github key
username is your Github username
when Git prompts you to enter your passkey, it refers to the **personal access token** that is different from your Github account password.

# Generate a personal access token
In your Github account, go to Settings -> Developer Settings -> personal access token -> tokens (classic)
If you don't have a token already, you can click "generate new token" -> generate token (classic)
In the scope, check all within repo.
copy the key and save it in a secure location

---------
# Collaboration

# Sync Fork
After you push your local commits onto github, always sync forks before you do pull requests. This allows your forked repo to be up-to-date with others before you submit any changes.
1 commit ahead --meaning you made changes 
2 commits behind --others made changes to the original repo

# Pull Request
click "Contribute" button -> open pull request -> add title and description

# Project Lead review pull requests
click "Pull Requests" -> go into the pull request and look at the commits, file changes, etc.

If we see "merge branch xxxxx:main into main", that means we synced the fork.
