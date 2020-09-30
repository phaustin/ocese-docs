# Some challenges

This is not meant to be an exhaustive troubleshooting guide. The advise is simply based on difficulties we have encountered, or challenges that are common or expected to be common. 

Currently the items are in random order - we might gather them into sections later. 

1. Here is the main **[git reference](https://training.github.com/)**. They also have a succinct git cheat sheet in [online](https://training.github.com/downloads/github-git-cheat-sheet/) and [PDF](https://training.github.com/downloads/github-git-cheat-sheet.pdf) formats.  
2. **The `.gitignore` file not working:** The ability of Git to ignore (when committing) files specified in the `.gitignore` file does not work on files that were already part of the repository when the .gitignore file was created, or the repo was cloned. If some files that should be ignored somehow get into the repo. you can untrack them using the short instructions here: [Untrack-files-already-added-to-git-repository-based-on-gitignore](http://www.codeblocq.com/2016/01/Untrack-files-already-added-to-git-repository-based-on-gitignore/). 
