## Overview

A **merge conflict** occurs when there are competing changes to a file from different 
collaborators and the resolution is not obvious. 

If there are two different versions of a file when a repository merge is attempted but the 
differences are edits on different lines, Git will resolve the difference automatically.

Competing changes, however, are not resolved without input from the user. These include 
changes to the same line from different collaborators, and when a file is edited by one 
collaborator and deleted by another. 

Merge conflicts must be resolved before a pull request can be merged.

## Competing line changes

To resolve a competing line change merge conflict, the user has to choose which line change to 
incorporate in a new commit. 

Attempting to merge branches with different edits on the same line results in a merge conflict
error. The merge conflict must be resolved with a new commit before the merge can be completed.

1.  Open Git Bash. 

2.  Navigate to the repository that has the merge conflict(s).
```
cd REPOSITORY-NAME
```

3.  Use the `$ git status` command to see the files affected by the merge conflict. In this example, the file 
*conflicted.md* has a merge conflict.

```
$ git status
> # On branch branch-b
> # You have unmerged paths.
> #   (fix conflicts and run "git commit")
> #
> # Unmerged paths:
> #   (use "git add ..." to mark resolution)
> #
> # both modified:      conflicted.md
> #
> no changes added to commit (use "git add" and/or "git commit -a")
```
   
4. Navigate to the file with merge conflicts with a text editor like Visual Studio Code. 

5. Search the file for the conflict marker `<<<<<<<`. The changes from the base branch are shown right after the line
`<<<<<<< HEAD`. After these changes, `=======` divides them from the changes in the other branch. In the following 
example, "CHANGE ONE" is what was written in the base branch and "CHANGE 2" is what was written in the compare branch.
```
Here is the change:
<<<<<<< HEAD
CHANGE ONE
=======
CHANGE 2
>>>>>>> branch-a
```

6. Decide if you want to keep one of the changes or make a new change. Delete the conflict markers `<<<<<<<`, `=======`,
and `>>>>>>>` and make the final changes that you want. In the following example, "BOTH CHANGES" is made the final edit 
instead:
```angular2html
BOTH CHANGES
```

7. Add or stage your changes.
```angular2html
$ git add . 
```

8. Commit your changes.
```angular2html
$ git commit -m "commit message" 
```

## Removed file
If a file is deleted in one branch and edited in another branch to result in a merge conflict, the user must choose 
whether to delete or to keep the file with a new commit before the branches can be merged. 

1. Open Git Bash

2. Navigate to the Git repository with the merge conflict. 
```angular2html
cd REPOSITORY-NAME
```

3. Use the `$git status` command to see the files affected by the merge conflict. In the following example, the file 
*DELETED.md* has a merge conflict. 
```angular2html
$ git status
> # On branch main
> # Your branch and 'origin/main' have diverged,
> # and have 1 and 2 different commits each, respectively.
> #  (use "git pull" to merge the remote branch into yours)
> # You have unmerged paths.
> #  (fix conflicts and run "git commit")
> #
> # Unmerged paths:
> #  (use "git add/rm ..." as appropriate to mark resolution)
> #
> #	deleted by us:   DELETED.md
> #
> # no changes added to commit (use "git add" and/or "git commit -a")
```

4. Navigate to the file in a text editor like Visual Studio Code. 

5. Decide whether or not to keep the removed file. You may view the edits that were made to the file in the text editor.

To keep the file:
```angular2html
$ git add DELETED.md
```

To remove the file:
```angular2html
$ git rm README.md
 > README.md: needs merge
 > rm 'README.md'
```

6. Commit the changes made. 
```angular2html
$ git commit -m "commit message"
> [branch-d 6f89e49] Merge branch 'branch-c' into branch-d
```


You can add labels by clicking on the small cog icon on the right menu bar. You are able to use either a predefined label or create your own customized label so that it is easier for you to identify issues at a later date. 
![Navigating to issues](/site/assets/images/issues4.png)

Users can then use these labels to filter issues and find all issues that have a specific label.

For more information, please reference the [documentation](https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/managing-labels)

## Adding milestones

You can add milestones by clicking on the small cog icon on the right menu bar. A milestone lets you keep track of the progress through a date-based approach. It will show the progress of the task as the target date approaches.

![Navigating to issues](/site/assets/images/issues5.png)
For more information, please reference the [documentation](https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/about-milestones)

## Adding assignees

You can add assignees to a task by clicking on the small cog icon on the right menu bar. An assignee can be specified so that users are able to track who is responsible for fixing a certain issue.

![Navigating to issues](/site/assets/images/issues6.png)

For more information, please reference the [documentation](https://docs.github.com/en/issues/tracking-your-work-with-issues/assigning-issues-and-pull-requests-to-other-github-users)

## Commenting  on an Issue

If we would like to comment on a Github issue, we can take the following steps:

1. Navigate to the issue you would like to comment on.
2. Scroll down to the comment text field.
3. Type your comment in the text field.

4. Click on the green **Comment** button to post your comment.

![Navigating to issues](/site/assets/images/issues7.png)

## Closing an Issue

If we would like to close a Github issue, we can take the following steps:

1. Navigate to the issue you would like to close.

2. Optionally, you can leave a comment explaining why you are closing the issue.
3. Click on the **Close issue** button with the purple check mark to close the issue.

![Navigating to issues](/site/assets/images/issues8.png)
## Reopening an Issue

If we would like to reopen a Github issue,
we can take the following steps:

1. Navigate to the closed issue you want to reopen.

2. Optionally, you can leave a comment explaining why you are reopening the issue.
3. Click on the **Reopen issue** button with the purple check mark to reopen the issue.

![Navigating to issues](/site/assets/images/issues9.png)

## Conclusion

By the end of this section, you will have successfully learned:

- How to create, comment, close, and reopen an issue.
- How to add labels, milestones, and assignees to an issue.

