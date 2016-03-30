### How to Collaborate with Git
###### A simple, fun, and easy guide made by Patrick Huston
=========================================================

#### Resources

Before we get started, I'll provide you with some good resources to refer to.

- [The Git cheatsheet](https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf)
- [Git Scm - extremly exhaustive documentation on git](https://git-scm.com/doc)
- [Piazza - ask your questions to instructors and ninjas](https://piazza.com/)

On that last note - one of the best ways to learn git if you still find it confusing is to get yourself into git trouble, and with the help of a ninja or an instructor, figure out what happened, and resolve the issues together.

#### Where you are
At this point in your software development career, you probably have some basic skills in your git toolbox. Let's quickly review a basic git flow:

1. `git clone`

  This is the command you use to make a clone. What's a clone, you ask? 
A clone is a copy of a repository that lives on your computer instead of on a website's server somewhere. In you case, this 'somewhere' is 
on github's servers.

2. `git add`

  Add is the command you use to tell git that you've edited a file (or a set of files). Wild! This adds them to the 'staging area'

3. `git commit`
  
  Commit is the command you use to create a 'checkpoint' of sorts that git knows about. An individual commit represents
  A commit, or "revision", is an individual change to a file (or a set of files).

4. `git push`

  Push is the command you use to send the commit you've created to the remote repository. The arguments with this command follow the pattern `git commit __remote__ __branch__`. The default remote that GitHub sets up for you is `origin`, and the default branch is `master`. In this tutorial, we'll talk about adding new branches, but we'll stick with the `origin` remote for the time being. In a lot of cases, it's good practice to always use the command
  
5. `git pull`

  to pull in any changes you don't have before pushing your new commit(s). Pull takes the same arguments as push - it takes the same form of `git pull __remote__ __branch__`. 
  
Before we get to branching, let's go once more over what you're doing with these different commands. Here's a great diagram that might help elucidate what's going on behind the scenes.

![Flow Diagram](http://i.stack.imgur.com/UvZ0M.png)
  
#### Beyond the Basics

Now that we've gone beyond the basics, let's talk about collaborating on a project with git. Hot.

##### Branches

One of the main concepts you'll be leveraging when usingworking on a collaborative git project with teammates is branches. A branch is a parallel version of a repository. It is contained within the repository, but does not affect the primary or master branch allowing you to work freely without disrupting the "live" version. When you've made the changes you want to make, you can merge your branch back into the master branch to publish your changes.

But how do I create a new branch?

`git checkout -b __mybranchname__` 

This command does two things. It both creates a new branch and switches you to that new branch. Double trouble, am I right? Now that you've created your new branch, your workflow will be basically the same. `add`, `commit`, `pull`, `push`. It's the same, you're just not working on the main `master` branch anymore. 

When you're ready to 'merge' the changes you've made back into the master branch, you have two options. One is to use the `pull request` tool provided by github, or the command line `merge` command provided by github. Merging takes the changes from one branch (in the same repository or from a fork), and applies them into another. This often happens as a Pull Request (which can be thought of as a request to merge), or via the command line. A merge can be done automatically via a Pull Request via the GitHub.com web interface if there are no conflicting changes, or can always be done via the command line. [See Merging a pull request](https://help.github.com/articles/merging-a-pull-request/).

A `merge` command works like this. You supply one argument - a branch name - that you want to 'merge' into your current branch. Let's say I'm on my `master` branch, and my partner has been working on a branch called `superdopefeature`. My partner has done some good work and completed the super dope feature, so we're ready to pull the changes from `superdopefeature` into `master`. How do I do this?

`git merge superdopefeature`. Dope indeed.

##### Merge Conflicts

Sometimes, the world will be against you. You and a teammate may conflict - and this commonly happens in one of several scenarios.

1. You both edit the same line in the same file
2. Your teammate deleted a file that you modified
3. You both added a file with the same name

Merge conflicts happen. The number one thing to do is to not freak out. We'll walk through how to solve one of the most common conflicts - when two people edit the same line in a single file.

This is what your command line might look like if you try to merge and get a conflict -- 

![Merge Conflict](http://images.abizern.org/365git/April10/Terminal01.png)

Running `git status` will probably give you something that looks like this -- 

![Merge Conflict Status](http://images.abizern.org/365git/April10/TerminalGst.png)

Now is the time to have a look at the contents of the conflicted file. Literally open it in your code editor. Git is nice enough to mark the problematic area in the file by enclosing it in `<<<<<<< HEAD" and ">>>>>>> [other/branch/name]`.

When you open the files up in your editor, it might look something like this -

![Merge conflict in file](https://github-images.s3.amazonaws.com/enterprise/11.10.340/user/assets/images/mac/changes/merge_conflict_sample.png)

It's your job now to edit the file to the point where it is *exactly* where you want it to be. Remove all of the '>>>>>>>' and '<<<<<<<' and everything you don't want until it looks good. At this point, `add`, `commit`, `push`, and you're golden.

##### Task Management

What people code when **matters a lot**.

Tasks should be very specifically targeting a certain piece of code. Code should modular to accomodate.

Tasks should be single features or bug fixes. Large refactors or clean ups that affect the entire code base should be planned in advance and done as a team when no one else is branched off master.

If you feel comfortable with your git workflow, you should really be making a branch for every feature. This is difficult to keep up for an entire project, but think of it this way - this project is part of your portfolio, and knowing git well is a desireable and employable skill. Showing off your effective git workflow through a real project can be a really great way to demonstrate your abilities to an employer.





