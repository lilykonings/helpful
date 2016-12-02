Git Tips
======
### get remote branch[<sup>ref</sup>](http://stackoverflow.com/questions/9537392/git-fetch-remote-branch)
```
git checkout --track origin/daves_branch
```

### git merge specific file from another branch[<sup>ref</sup>](http://stackoverflow.com/questions/18115411/how-to-merge-specific-files-from-git-branches)
```
git checkout --patch branch2 file.py
```

### discard unstaged changes[<sup>ref</sup>](http://stackoverflow.com/questions/52704/how-do-i-discard-unstaged-changes-in-git)
```
git stash save —keep-index
git stash drop
```

### untrack files from git[<sup>ref</sup>](http://stackoverflow.com/questions/6919121/why-are-there-2-ways-to-unstage-a-file-in-git)
```
git rm -r --cached [path/file]
```

## Common Questions
### difference between git pull and fetch[<sup>ref</sup>](http://stackoverflow.com/questions/292357/difference-between-git-pull-and-git-fetch)
> In the simplest terms, git pull does a git fetch followed by a git merge.

> - When you use pull, Git tries to automatically do your work for you. It is context sensitive, so Git will merge any pulled commits into the branch you are currently working in.  pull automatically merges the commits without letting you review them first. If you don’t closely manage your branches, you may run into frequent conflicts.
> - When you fetch, Git gathers any commits from the target branch that do not exist in your current branch and stores them in your local repository. However, it does not merge them with your current branch. This is particularly useful if you need to keep your repository up to date, but are working on something that might break if you update your files. To integrate the commits into your master branch, you use merge.
