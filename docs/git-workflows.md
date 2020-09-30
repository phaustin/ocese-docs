# Git Workflows

For an introduction to Git and version control, see the page [Git Intro](git-intro.html). This page outlines four levels of workflow complexity:
1. Solo no branching workflow; the simplest use of GitHub as a repository for your own work only.
2. Solo with branch and merge to manage your own development of features.
3. Sharing but with no branching (not ideal).
4. Fork & Pull Workflow.

Details follow. 

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

- Could be derived from the tutorial at NSF's [National Ecological Observatory Network](https://www.neonscience.org/git-setup-remote). This is part 7 from a succinct 7-part beginner's Git tutorial. See also "Pointers & References" below. 

NEED TO CHECK and integrate "[A Pull Request Workflow Tutorial](https://github.com/eoas-ubc/eoas_tlef/blob/master/docs/Git_workflow.md)". 

---

## 4. Fork & Pull Workflow

Collaboration using a Fork from someone else's repository, develop in a branch, maintain synchronicity with the originator's master, and request addition of your work using pull request. 

- Fork to your own repository
- Clone to your local 
  - In your local folder under which the new repo should reside: `Git clone …URL…`
  - Track the original upstream version: `Git remote add upstream`
  - (Verify the new remote with `git remote -v` .)
- At start of each editing session:
  - Bring upstream's branches (with edits) into the local repo.: `git fetch upstream`
  - (View all branches, including those from upstream with `git branch -va` .)
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

See the end of the page [Git Intro](git-intro.html).

