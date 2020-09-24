# Git and GitHub

Here we outline four levels of complexity.

## 1. Solo no branching workflow

The simplest use of GitHub as a repository for your own work only, with local editing.

- In your GitHub account, use the big green **New** button to make a new blank repository.
  - It will ask you to name it, describe it briefly, declare it as public or private
  - Also you should answer the "initialize this repository" by adding README and license files. (The "BSD 3-Clause License" is OK.) These two should be included as a matter of good practice. 
  - a .gitignore file is not needed yet, but may be added later.
- Update the README.md file
  - Click the README.md file
  - Click the edit pencil icon
  - Add a line or two
  - Below the edit box you will see "Commit changes" information. Describe the change in the top one-line box, add optional info if you like, check email, be sure you pick "Commit directly to the master branch" and click the Commit changes button.
- That's all that is necessary.
- Work can be carried out within the GitHub environment. Add new or upload files, edit text files (MarkDown or .md files or code, etc.) 

The next step is to clone to your local computer so you can work on the project on your own computer or laptop.

- Install Git version control system on your own computer.
- There are GUIs for all platforms, but it is "safer" to start using the command line, and move to a graphical user interface once you are able to work from the command line. 

---

## 2. Solo with branch and merge

No collaboration but use of branches to "contain" your own development of features.

- Not yet written.

---

## 3. Sharing but with no branching (not ideal)

- Tutorial at NSF's [National Ecological Observatory Network](https://www.neonscience.org/git-setup-remote). This is part 7 from a succinct 7-part beginner's Git tutorial. See also "Pointers & References" below. 

---

## 4. Fork & Pull Workflow

Collaboration using a Fork from someone else's repository, develop in a branch, maintain synchronicity with the originator's master, and request addition of your work using pull request. 

- Fork to your own repository
- Clone to your local 
  - In your local folder under which the new repo should reside: `Git clone …URL…`
  - Track the original upstream version: `Git remote add upstream`
  - (Verify the new remote with `git remote -v`)
- At start of each editing session:
  - Bring upstream's branches (with edits) into the local repo.: `git fetch upstream`
  - (View all branches, including those from upstream with `git branch -va`)
  - Checkout your master branch and merge with upstream's master: 
  
  ```bash
  git checkout master
  git merge upstream/master
  ```
  
  - To create a new branch and start working on it, first checkout the master branch (the new branch should come from master): `git checkout master`
  - Create a new branch `git branch newfeature`
- Continue editing on this branch.
- Fetch upstream and merge that master with your master

```bash
    git fetch upstream
    git checkout master
    git merge upstream/master
```

- If there were any new commits on upstream's master, rebase your work branch:

```bash
    git checkout newfeature
    git rebase master
```

- This means "rebase the _newfeature_ branch onto the _master_ branch."
  - **Golden rule of git rebase**: never use it on public branches. For example never, never do `git checkout master` then `git rebase newfeature`. From [this reference](https://www.atlassian.com/git/tutorials/merging-vs-rebasing#the-golden-rule-of-rebasing).
- OR, IF desired, clear up by squashing (some) smaller commits down into larger commits using interactive rebase:

```bash
   git checkout newfeature
   git rebase -i master
```

- Push to your GitHub repo and ask to merge with original 
  - Send to your repo: `git push`
  - Ask to contribute your work to owner of upstream.
    - At your GitHub repo select the development branch! 
    - Click "pull request". 
- (NOTE: Subsequent changes to that branch will be tracked until pull request is accepted or rejected. )

---

## Pointers & References

There are a great many open-source and commercial tutorials, how-to's and manuals including written pages, tutorials (with exercises, examples etc.), and videos. Here are some recommendations.

||Description|Type|Comments|
|---|---|---|---|
|1|**[7-part intro. to Git](https://www.neonscience.org/version-control-git-series)** from NEON (National Ecological Observatory Network).|written tutorial website|Succinct, no extra words, includes objectives; very nice. Somewhat derived from Software Carpentry (next item). Includes updating repos via "remote".|
|2|**[Software carpentry's resources](https://swcarpentry.github.io/git-novice/)** for their hands on workshops.|Well organized website|Includes a workshop schedule, pages for each section & exercises. A bit more wordy than NEON's introduction, but well designed and tested.|
|3|**[Git manual](https://git-scm.com/doc)** and others, from Git.|Ref. manual; book; videos|Detailed documentation and the comprehensive Pro Git book. Four short videos are good introductions.|
|4|**["Best practices" & Git cheat sheet](https://www.jrebel.com/system/files/git-cheat-sheet.pdf)**|PDF page|From a nice (although oldish, 2016) summary by _Rebellabs_ called [Git Cheat Sheet: Commands and Best Practices](https://www.jrebel.com/blog/git-cheat-sheet).|
|5|**[GitHub Forking](https://gist.github.com/Chaser324/ce0505fbed06b947d962)**|MD page|"Fairly standard" procedure: Create a fork; Do your work; Issue a pull request; Merge back into the original project.|
|6|**[LinkedIn Learning "courses"](https://linkedinlearning.ubc.ca)** for UBC faculty and staff|Video courses|Log in using your CWL and search for Git, or GitHub, etc. There are many, but at least they are not quite as random as the unfiltered internet.|

---
---
