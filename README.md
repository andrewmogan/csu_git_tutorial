# CSU Git Tutorial

This repository serves as a simple, safe place to experiment with Git/GitHub commands. The original intended audience was CSU physics graduate students who need to learn version control for their analysis work, but the principles here can apply to anyone trying to learn Git. This tutorial will focus on using Git via a command-line interface, specifically Linux/Mac command line. This interface is commonly used on high-performance computing clusters that don't have a graphical interface. Many modern particle physics experiments run their production code on such compute clusters, so knowing how to work with a command-line interface is essential.  

# Git? Github? Why should I care?

Simply put, Git is free, open-source version control software. Utilized correctly, it allows many people to work from the same code base without stepping on each others' toes or breaking the production code for everyone. Git can create "snapshots" or your repository at a given time, and those snapshots can be retrieved later. It also allows for individuals to branch off the "main" code branch to implement their own changes. Modifications made in these _feature branches_ wont' affect the main branch until the repository maintainer(s) decided to merge the changes into main. A simple visualization of this is shown below.

![Sample Github Flow](images/github_flow.png)

Any repository that uses Git can be stored on GitHub, a cloud-based hosting service for managing git repositories. Many of the commands we'll learn here can be performed in GitHub rather than on the command line, but this isn't always an option when working in a command-line environment such as those found on most high-performance compute clusters. 

As for why you should care, there are several reasons:
- __Branch workflow__: Git allows individuals to modify and experiment with code in a way that doesn't interfere with others. This allows for improvements to be introduced in a staged, parallel manner, ensuring overall stability of the main code base.
- __Reproducibility__: Having snapshots of your code means you can always revert back to an older snapshot if something breaks. Even when nothing is broken, having a common code base for everyone to work from ensures stability and reproducibility.
- __Widely used__: Both in and outside of academia, Git and GitHub are everywhere. Some physics experiments host their experiment-wide production code on GitHub. No matter your future prospects, GitHub will prove an invaluable tool for your career. 

# Getting Started

First, you'll need to install Git. See the instructions [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) for installation instructions on Mac, Linux, and Windows. To check your installation, run
```
git --version
```
from the command line. Your output should say something like
```
git version 2.34.1
```

The next step is to "clone" this repository from the remote (GitHub) to local (your machine). Click the green "Code" button in the upper-right of this page and copy the URL there. Then, from the command line, run
```
git clone <copied_url>
```
where you should replace `<copied_url>` with whatever was in the "Code" box. Wherever you are on your machine, Git will create a new directory with the name of this repository&mdash;`csu_git_tutorial`, in this case. You can then enter that directory by typing
```
cd csu_git_tutorial
```

# Basic Git Commands

So, you've cloned a repository to your local machine. Now what? A good first step is to run `git status`, an essential Git command that summarizes the current state of your code. Assuming you haven't made any changes, the output will look something like this:
```
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

Since we haven't made any changes to the code yet, there isn't much to see. Importantly, the first line tells you which branch you're on. When you first clone a repsoitory, you'll usually be in the `main` branch by default. __Before you start making changes__, it's good practice to create a new branch and make your changes there. First, let's look at what branches are already available using `git branch --list`:
```
* main
```
Naturally, there's only one branch, `main`. The `*` indicates which branch you're currently on. Now, let's create a new branch where we can start making changes. To create a new branch on Git, simply run
```
git switch -c my_new_branch
```
where `my_new_branch` can be any name you want. You should see something like `Switched to a new branch 'my_new_branch'` output to the command line. As the name implies, `git switch` is used for switching between branches. Passing the `-c` flag creates a new branch and then switches to it. (__Note__: `git switch` has replaced the older `git checkout` command. If you see older documentation refer to `git checkout`, just know that the two are functionally the same, but `git switch` has more intuitive syntax and is now the preferred method.) Now, if we run `git status` again:
```
On branch my_new_branch
nothing to commit, working tree clean
```
and `git branch`:
```
  main
* my_new_branch
```

We see that we've successfully created and switched to `my_new_branch`. 

## Modifying the Code



## Summary of Common Git Commands

This list below summarizes some of the most common commands. Note that some of these commands require additional command-line arguments that are not shown here. If you forget some command-line arguments, Git will usually tell you what's missing. 

- `git clone`: copy remote repository to your local machine.
- `git status`: view current edits, branch, etc.
- `git branch`: view available “branches” (other people's’ code state).
- `git fetch`: get the latest changes from remote _without merging_.
- `git merge`: Merge changes from another branch into your current branch.
- `git pull`: get latest changes from remote and merge them into local. This is actually an alias for `git fetch` followed by `git merge`.
- `git switch`: switch between branches. Pass the `-c` flag to create a new branch and switch to it. 
- `git add`: choose files to be “staged” (added to code snapshot).
- `git commit`: create a snapshot of your current code state. Pass the `-m` flag to create a commit message.
- `git push`: “push” your changes from local to remote.
- `git diff`: view difference in your code state relative to some previous commit (most recent commit by default).
- `git log`: display a log of commits. Pass the `-n` flag to limit how many log entries are printed.











