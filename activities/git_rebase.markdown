---
layout: activity
---

# Git Rebase Exercises

## Introduction

In the slides we saw an example of a rebase in a repository with
two branches. The rebase resulted in a conflict that needed to be resolved manually.

<img src="img/rebase0.png">

Executing


```
git checkout branch1
git rebase master
```

results in a conflict since file3 has been independently created/modified in both branches.

- If we resolve the conflict by skipping the commit `d09942b` (the one that created file3 in branch1), then the resulting branches will look as follows.

  <img src="img/rebase0_skip.png">

  (This means that we decided to not apply the that commit to the resulting flow of commit. It is now gone. )

- If we resolve the conflict by using the content of the file from the commit in branch1, thne the resulting branches will look as follows.

  <img src="img/rebase0_use_commit.png">

  (This means that we decided to apply the that commit that created file3 in branch1 on top of (after) the commit that created that file in the master branch.)

In the following, you are given a few exercises that will give you a bit of experience in working with branches and rebasing.

For each exercise, consult with other students in your group and add the final answer to the shared pad at
https://pad.riseup.net/p/ossd_git_rebase  


## Exercise 1

On your local machine, create a new repository. Try to perform sequence of `git` instructions that will produce a repository for which the commits look as follows

<img src="img/rebase1.png">

<br><br>

Keep in mind:
- `git` does not allow you to easily add empty files or empty commits, so make sure that your files actually contain something in them
- to see the log of commits in different branches (as shown above) you can run
  ```
  git log --graph --oneline --all
  ```
- the actual commit hash codes depend on the file content, so you will not be able to recreate these exactly, but you should be able to recreate the structure of the two branches and the sequence of the commits.

Consult with your group members if you are running into problems.

Compare your steps with those of your group members. Pick one of the sequences of instructions that correctly recreated the above structure and add it to the shared pad with a note "Exercise 1". Make sure that your answer is posted under the correct _room_ heading. If you were not able to do this step correctly, do not enter anything in the shared pad.

## Exercise 2

1. If your group was able to recreate the structure correctly, move on to the next step. If you were not, look at the shared pad and pick a sequence of instructions that was successful and execute it on your own machine (you may need to start from a clean repository).

1. In this step, you will rebase the branch1 onto master.  
    1. Consult with your group before you attempt the rebase to answer the questions below.
There are two commits in branch1 that will be "rebased" onto the master branch,

        - how many conflict might there be?
        - what will the files look like after the rebase is complete?

        Enter your answers/guesses in the pad under the heading "Exercise 2".

    1. Perform the actual rebase:
    ```
    git rebase master
    ```
    If there are conflicts and alternative ways to resolve them, explore different ways and what happens in each. <br>
    Were your answers/guesses correct? If anything strange happened, try to decide if it makes sense and describe your thinking. (This should be answered as a group.)


## Exercise 3

In exercises 3 and 4 you will repeat similar steps to the ones that you did in exercises 1 and 2, but with a slightly different repository.

On your local machine, create a new repository. Try to perform sequence of `git` instructions that will produce a repository for which the commits look as follows

<img src="img/rebase2.png">

Consult with your group members if you are running into problems.

Compare your steps with those of your group members. Pick one of the sequences of instructions that correctly recreated the above structure and add it to the shared pad with a note "Exercise 3". Make sure that your answer is posted under the correct _room_ heading. If you were not able to do this step correctly, do not enter anything in the shared pad.

## Exercise 4

1. If your group was able to recreate the structure of the repository in exercise 3 correctly, move on to the next step. If you were not, look at the shared pad and pick a sequence of instructions that was successful and execute it on your own machine (you may need to start from a clean repository).

1. In this step, you will rebase the branch1 onto master.  
    1. Consult with your group before you attempt the rebase to answer the questions below.
There are two commits in branch1 that will be "rebased" onto the master branch,
        - how many conflict might there be?
        - what will the files look like after the rebase is complete?

        Enter your answers/guesses in the pad under the heading "Exercise 4".

    1. Perform the actual rebase:
    ```
    git rebase master
    ```
    If there are conflicts and alternative ways to resolve them, explore different ways and what happens in each.<br>
    Were your answers/guesses correct? If anything strange happened, try to decide if it makes sense and describe your thinking. (This should be answered as a group.)
