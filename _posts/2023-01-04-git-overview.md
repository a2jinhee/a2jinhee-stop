---
layout: post
cover: false
navigation: false
title: Git Overview
date: 2023-01-04
tags: fiction
subclass: "post tag-fiction"
# author:
# categories:
---

<br/>
### What is Git?

Git is a command line tool that will help us with version control in several different ways:

- Keep track of changes we make to our code by saving snapshots of our code/project.
- Allow us to easily synchronize code between different people working on the same project. → Multiple people pull/push information to repository stored on the web.
- Allow us to test out code on a different branch (i.e. feature) without altering our main code base, and then merge the two together.
- Allow us to revert back to earlier versions of our code if we realize we’ve made a mistake.

![alt text](https://miro.medium.com/max/4800/0*UAZ7JUT2H4CHKEVJ.webp)

A Git repository is a file location where we’ll store all of the files related to a given project. These can either be remote (stored online) or local (stored on your computer).

---

### GitHub

GitHub is a website that allows us to store Git repositories remotely on the web.

Follow along to understand the very basics of Github.

1. Install git in your computer.
2. Create a git repository in Github.
3. In your terminal, run the code below.

```
{git clone <repository url>}
```

`<repository url>` is the HTTPS web URL for your repository.

4. `cd <repository url>` : to change directory into that folder
   `touch <new file name>` : to create a new file in that folder
5. Now, to let Git know that it should be keeping track of the new file you’ve made, run the code below.

```
{
  // to track specific file
git add <new file name>

// to track all files within the directory
git add .

}
```

---

### Commits

1. After making some changes to a file, we can commit those changes, taking a snapshot of the current state of our code. Run the code below,

```
{
  git commit -m "commit message"
}
```

2. `git status` allows us to see how our compares to the code on the remote repository (that is, the repository on the website not your local computer)

3. When we’re ready to publish our local commits to Github, we can run `git push`. Now, when we go to GitHub in our web browser, our changes will be reflected.

4. If you’ve only changed existing files and not created new ones, condense `git add .` + `git commit ...` → `git commit -am "commit message"`

❖ Sometimes, the remote repository on GitHub will be more up to date than the local version. In this case, you want to first commit any changes, and then run git pull to pull any remote changes to your repository.

---

### Merge Conflicts

![alt text](https://miro.medium.com/max/1400/1*Q9JVqoWtG7ekUvjxmUuDhA.webp)

- `git log` : history of all commits on repository
- `git reset --hard <commit hash>` : reverts your code to exactly how it was after the specified commit. To specify the commit, use the commit hash associated with a commit which can be found using `git log` as shown above.
- `git reset --hard origin/master` : reverts your code to the version currently stored online on Github.

---

### Branching

But this could become problematic if we then discover a bug in our original code, and want to revert back without changing the new feature. This is where branching can become really useful.

What is branching? Branching is a method of moving into a new direction when creating a new feature, and only combining this new feature with the main part of your code, or the main branch, once you’re finished.

![alt text](https://miro.medium.com/max/1400/0*WKj_PImQYJhunCos.webp)

The branch you are currently looking at is determined by the HEAD, which points to one of the two branches. By default, the `HEAD` is pointed at the master branch.

Follow along to see how we actually implement branching in our git repositories:

1. Run `git branch` to see which branch you’re currently working on, which will have an asterisk to the left of its name.

![alt text](https://miro.medium.com/max/1400/0*qvZ6JCcDkK7GPkm-.webp)

2. To make a new branch, we’ll run `git checkout -b <new branch name>`

3. Switch between branches using the command `git checkout <branch name>` and commit any changes to each branch.

4. When we’re ready to merge our two branches together, we’ll check out the branch we wish to keep (almost always the master branch) and then run the command `git merge <other branch name>`. This will be treated similarly to a push or pull, and merge conflicts may appear.

---

### More GitHub Features

- Forking
- Pull Requests
- GitHub Pages

_All credit to :_ <https://cs50.harvard.edu/web/2020/notes/1/>
