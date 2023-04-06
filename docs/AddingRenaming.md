## Overview

**Adding**, **renaming**, and **moving** files are all processes that must be synchronized 
between multiple clones of the same repository. 

Changes are [**staged**](glossary.md) and [**committed**](glossary.md) before being pushed 
to a central repository stored online.

## Adding a file

The command line can be used to add a file to a repository. 

Before this can be done, you must have a repository on GitHub that has been cloned locally on your computer.

1. Move the file that you want to add to the directory that is your clone of the repository.
2. Open Git Bash.
3. Change the current working directory to your clone of the repository.
4. Stage the file for commit to your clone using:

    ```
    $ git add . 
    ```
   
5. Commit the file that you've staged in your local repository.

    ```
    $ git commit -m "commit message"
    ```
   
6. Push the changes to GitHub.

    ```
    $ git push origin YOUR_BRANCH
    ```

## Renaming a file

The command line can be used to rename any file in a repository. 

While many files can be renamed on the GitHub website, some types of files *must* be renamed from the command line.
Images are one example.

1. Open Git Bash

2. Change the current working directory to your repository.

3. Rename the file with the following command. This will stage the change for commit.

    ```
    $ git mv OLD-FILENAME NEW-FILENAME
    ```

4. Use the `git status` command to check the original and new file names.

    ```
    $ git status
    > # On branch YOUR-BRANCH
    > # Changes to be committed:
    > #   (use "git reset HEAD ..." to unstage)
    > #
    > #     renamed: OLD-FILENAME -> NEW-FILENAME
    > #
    ```
   
5. Commit the file.

    ```
    $ git commit -m "commit message: file renamed"
    ```

6. Push the changes to GitHub.

    ```
    $ git push origin YOUR_BRANCH
    ```

## Moving a file

The command line can be used to move files within a repository by removing it
from one location and then adding it to a new location.

Some files, such as images, must be moved using the command line and cannot be
on the GitHub site. 

1. Move the file to the new location within the directory using any method.
2. Open Git Bash.
3. With the `git status` command, see that the old file location has been 
"deleted" and that there is "new" file at the new location. In the following
example, *image.png* has been moved from *OLD-FOLDER* to *NEW-FOLDER*.

    ```
    $ git status
    > # On branch YOUR-BRANCH
    > # Changes not staged for commit:
    > #   (use "git add/rm ..." to update what will be committed)
    > #   (use "git checkout -- ..." to discard changes in working directory)
    > #
    > #     deleted:    /OLD-FOLDER/IMAGE.PNG
    > #
    > # Untracked files:
    > #   (use "git add ..." to include in what will be committed)
    > #
    > #     /NEW-FOLDER/IMAGE.PNG
    > #
    > # no changes added to commit (use "git add" and/or "git commit -a")
    ```

4. Stage the file for commit using the `git add` command.
5. Check the staged files using `git status`. In this example, *IMAGE.PNG* has
been moved from *OLD-FOLDER* to *NEW-FOLDER*.

    ```
    $ git status
    > # On branch YOUR-BRANCH
    > # Changes to be committed:
    > #   (use "git reset HEAD ..." to unstage)
    > #
    > #    renamed:    /OLD-FOLDER/IMAGE.PNG -> /NEW-FOLDER/IMAGE.PNG
    # Displays the changes staged for commit
    ```
    
6. Commit the staged file:

    ```
    $ git commit -m "commit message: moved IMAGE.PNG"
    ```

7. Push the changes to GitHub:

    ```
    $ git push origin YOUR_BRANCH
    ```

## Conclusion

By the end of this section, you will have successfully learned:

- How to add a file to a GitHub repository. 
- How to rename a file that is already part of a GitHub repository. 
- How to move a file that is already part of a GitHub repository. 

