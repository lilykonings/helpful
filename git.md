Git Tips
======
- Staged: files are ready to be committed.
- Unstaged: files with changes that have not been prepared to be committed.
- Untracked: files aren't tracked by Git yet. This usually indicates a newly created file.
- Deleted: file has been deleted and is waiting to be removed from Git.
- Staging area: a place where files can be grouped together before they are "committed" to Git.
- HEAD: a pointer that holds the position within all different commits. By default HEAD points to the most recent commit, so it can be used as a quick way to reference that commit without having to look up the SHA.

- Add All: use `git add -A .` where the dot stands for the current directory, so everything in and beneath it is added. The `-A` ensures even file deletions are included.
- Reset: use `git reset <filename>` to remove a file or files from the staging area.

### clone into directory name of my choice
```
git clone url dir_name
```

### add wildcards
```
git add '*.js'
```

### more detailed git logs
See where new files were added for the first time or where files were deleted.
```
git log --summary
```

### use -u flag in git push to have git remember parameters in the future
```
git push -u origin master
```
after the above initial push, you can then use `git push` without the parameters

### git pull without commiting local changes
```
git stash
git pull
git stash apply
```

### revert files to last commit for <target>
```
git checkout -- <target>
```
> '--' simply promises the command line that there are no more options after it. This way if there happens to be a branch named <target>, it will still revert the file, instead of switching to the branch of the same name.

### create and checkout branch shortcut
```
git checkout -b new_branch
```
is equivalent to
```
git branch new_branch
git checkout new_branch
```

### get remote branch[<sup>ref</sup>](http://stackoverflow.com/questions/9537392/git-fetch-remote-branch)
```
git checkout --track origin/daves_branch
```

### merge specific file from another branch[<sup>ref</sup>](http://stackoverflow.com/questions/18115411/how-to-merge-specific-files-from-git-branches)
```
git checkout --patch branch2 file.py
```

### discard unstaged changes[<sup>ref</sup>](http://stackoverflow.com/questions/52704/how-do-i-discard-unstaged-changes-in-git)
```
git stash save —keep-index
git stash drop
```

### remove files that are not tracked[<sup>ref</sup>](http://stackoverflow.com/questions/22620393/various-ways-to-remove-local-git-changes)
```
git clean [-f]
```
> The -f (force) option will also remove files that are not tracked and are also being ignored by git though ignore-rule.

### remove files from local and remote repos
```
git rm filename.js
git rm '*.txt'
git rm -r dir/folder
```

### untrack files from git[<sup>ref</sup>](http://stackoverflow.com/questions/6919121/why-are-there-2-ways-to-unstage-a-file-in-git)
```
git rm -r --cached path/file
```

## Common Questions
### difference between git pull and fetch[<sup>ref</sup>](http://stackoverflow.com/questions/292357/difference-between-git-pull-and-git-fetch)
> In the simplest terms, git pull does a git fetch followed by a git merge.

> - When you use pull, Git tries to automatically do your work for you. It is context sensitive, so Git will merge any pulled commits into the branch you are currently working in.  pull automatically merges the commits without letting you review them first. If you don’t closely manage your branches, you may run into frequent conflicts.
> - When you fetch, Git gathers any commits from the target branch that do not exist in your current branch and stores them in your local repository. However, it does not merge them with your current branch. This is particularly useful if you need to keep your repository up to date, but are working on something that might break if you update your files. To integrate the commits into your master branch, you use merge.

### difference between ways to discard local changes[<sup>ref</sup>](http://stackoverflow.com/questions/22620393/various-ways-to-remove-local-git-changes)
> Type 1. Staged Tracked files  
> Type 2. Unstaged Tracked files  
> Type 3. Unstaged UnTracked files a.k.a UnTracked files  

> Staged - Those that are moved to staging area/ Added to index  
> Tracked - modified files  
> UnTracked - new files. Always unstaged. If staged, that means they are tracked. 

> What each command does:  
> - `git checkout .` removes Unstaged Tracked files ONLY [Type 2]
> - `git clean -f` removes Unstaged UnTracked files ONLY [Type 3]
> - `git reset --hard` removes Staged Tracked and UnStaged Tracked files ONLY[Type 1, Type 2]
> - `git stash -u` removes all changes [Type 1, Type 2, Type 3]

### difference between `git add -A` and `git add .`[<sup>ref</sup>](http://stackoverflow.com/questions/572549/difference-between-git-add-a-and-git-add)
As of Git Version 2.x, there is no functional difference. But prior to that, `git add .` would not stage deleted files while `git add -A` did.

### difference between `git commit -m <message>` and `git commit -am <message>`?
the `-a` flag 

### when do I use `--force` or `-f` to delete a branch?
`git branch -d bad_branch` doesn't work if it hasn't been merged. So it has to be force deleted if you are certain about it.

## Resources
- [Try Github](https://try.github.io)