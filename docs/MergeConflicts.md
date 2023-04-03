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

     ```
     BOTH CHANGES
     ```

7. Add or stage your changes.

     ```
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

    ```
    cd REPOSITORY-NAME
    ```

3. Use the `$git status` command to see the files affected by the merge conflict. In the following example, the file 
*DELETED.md* has a merge conflict. 

     ```
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
5. Decide whether to keep the removed file. You may view the edits that were made to the file in the text editor.

    To keep the file:
     ```
     $ git add DELETED.md
     ```
    To remove the file:
    ```
    $ git rm README.md
     > README.md: needs merge
     > rm 'README.md'
    ```

6. Commit the changes made. 

    ```
    $ git commit -m "commit message"
    > [branch-d 6f89e49] Merge branch 'branch-c' into branch-d
    ```

## Conclusion

By the end of this section, you will have successfully learned:

- How to resolve a merge conflict with competing line changes. 
- How to resolve a merge conflict with a file that has been edited *and* deleted. 

