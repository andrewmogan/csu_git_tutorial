# CSU Git Tutorial

This repository serves as a simple, safe place to experiment with Git/GitHub commands. The original intended audience was CSU physics graduate students who need to learn version control for their analysis work, but the principles here can apply to anyone trying to learn Git. This tutorial will focus on using Git via a command-line interface, specifically Linux/Mac command line. This interface is commonly used on high-performance computing clusters that don't have a graphical interface. Many modern particle physics experiments run their production code on such compute clusters, so knowing how to work with a command-line interface is essential.  

# Git? Github? Why should I care?

![Sample Github Flow](images/github_flow.pdf)

# Getting Started

First, you'll need to install Git. See the instructions [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) for installation instructions on Mac, Linux, and Windows. To check your installation, run
```
git --version
```
from the command line. Your output should say something like
```
git version 2.34.1
```

The next step is to "pull" this repository from the remote (GitHub) to local (your machine). 
