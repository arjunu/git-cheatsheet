# Git Cheatsheet

? - indicates optional arguments <br>
Dangerous commands are marked with :warning:

## Configure

- Set username <br>
`$ git config --global user.name "<name>"`

- Set email <br>
`$ git config --global user.email "<email address>"`

:information_source: Drop `--global` option to set local (repo specific) config.

## Create/Clone

- Create new local repo <br>
`$ git init <?project-name>`

- Clone existing  <br>
`$ git clone <url>` <br>

- Create from existing code  <br>
`$ git init` <br>
Add files & commit <br>
`$ git remote add origin <remote>` <br>
`$ git push origin master` <br>

## Local Changes

- Add all changes for next commit <br>
`$ git add .` <br>

- List all new & modified files to be committed <br>
`$ git status` <br>

- Show unstaged changes <br>
`$ git diff` <br>

- Commit <br>
`$ git commit -m "<message>"` <br>

## Update

- Fetch <br>
`$ git fetch` <br>

- Pull (fetch & merge) <br>
`$ git pull` <br>

- Push <br>
`$ git push <remote-name> <branch-name>` <br>

## Branches

- List all existing branches <br>
`$ git branch -av` <br>

- Create new branch <br>
`$ git branch <new-branch-name>` <br>

- Switch to branch <br>
`$ git checkout <branch-name>` <br>

- Carry changes to a new branch <br>
`$ git checkout -b <branch-name>` <br>

- Merge specified branch into current branch <br>
`$ git merge <branch-name>` <br>

- Delete branch <br>
`$ git branch -d <branch-name>` <br>

- Delete unmerged branch <br>
`$ git branch -D <branch-name>` :warning: <br> 

- Rename branch <br>
`$ git branch -m <new-branch-name>` # Rename current branch <br>
`$ git branch -m <old-branch-name> <new-branch-name>` # Rename another branch <br>

- Rename remote branch (after above step) <a href="#sources">[2]</a> <br>
`$ git push origin :old_branch`                 # Delete the old branch <br>
`$ git push --set-upstream origin new_branch`   # Push the new branch, set local branch <br>

## Remotes

- Show all remotes <br>
`$ git remote -v` <br>

- Add remote <br>
`$ git remote add <shortname> <url>` <br>

- Show remote information <br>
`$ git remote show <remote-name>` <br>

- Rename remote shortname <br>
`$ git remote rename <old-shortname> <new-shortname>` <br>

## Removing Files

- Delete file from working directory and stage the deletion <br>
`$ git rm <file>` <br>

- Remove file from version control but preserve it locally <br>
`$ git rm --cached <file>` <br>

## History

- Show all commits in reverse chronological order <br>
`$ git log` <br>

## Undoing

- Remove uncommitted changes <br>
`$ git checkout .` :warning: # use -f for force <br>

- Change last commit <br>
`$ git commit --amend` <br>

- Undo last local commit <a href="#sources">[1]</a> <br>
`$ git reset --soft HEAD~` # soft -- keep your changes<br>
`$ git reset --hard HEAD^` # hard -- discard changes<br>

- Undo last published commit <a href="#sources">[1]</a> <br>
`$ git revert HEAD` <br>

- Unstage a file <br>
`$ git reset HEAD <file>` <br>

- Unmodify a file <br>
`$ git checkout -- <file>` :warning:<br>

- Remove untracked files <br>
`$ git clean -f` :warning:<br>

- Remove untracked directories <br>
`$ git clean -d` :warning:<br>

## Tags

- Create tag <br>
`$ git tag -a <tag> -m "<message>"` 

- Push all tags <br>
`$ git push origin --tags`

## Glossary

#### Files

- **Commited:** data is safely stored in your local database
 
- **Modified:** you have changed the file but have not committed it to your database yet
 
- **Staged:** you have marked a modified file in its current version to go into your next commit snapshot

- **Tracked:** are files that were in the last snapshot; they can be unmodified, modified, or staged 
 
- **Untracked:** files are everything else – any files in your working directory that were not in your last snapshot and are not in your staging area
 
#### Repository

- **Remote:** Remote repositories are versions of your project that are hosted on the Internet or network somewhere
 
- **Origin:** Default name Git gives to the server you cloned from

#### Branches

- **master:** name given to default branch.
 
- **HEAD:** pointer to current branch.

- **fast-forward:** is a type of merge. When you try to merge one commit with a commit that can be reached by following the first commit’s history, Git simplifies things by moving the pointer forward because there is no divergent work to merge together.

- **Remote tracking branches:** are references to the state of remote branches. They act as bookmarks to remind you where the branches in your remote repositories were the last time you connected to them.

- **Rebase:** another type of integrating changes (the other one being `merge`) from one branch into another by taking all the changes that were committed on one branch and replaying them on another.

## Sources
- Github Git cheatsheet https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf
- Git Scm https://git-scm.com
- [1]: Undo a commit and redo http://stackoverflow.com/a/927386/2251156
- [2]: Updating your local branch's tracking reference to the new remote http://stackoverflow.com/a/16220970/2251156
 
# Articles

- fast-forward <br>
  http://ariya.ofilabs.com/2013/09/fast-forward-git-merge.html

