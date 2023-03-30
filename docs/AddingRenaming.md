## Adding a file

The command line can be used to add a file to a repository. 

Before this can be done, you must have a repository on GitHub that has been cloned locally on your computer.

1. Move the file that you want to add to the directory that is your clone of the repository. 

2. Open Git Bash.

3. Change the current working directory to your clone of the repository. 

4.  Stage the file for commit to your clone using:
```
$ git add . 
```

5. Commit the file that you've staged in your local repository.
```angular2html
$ git commit -m "commit message"
```

6. Push the changes to GitHub.
```angular2html
$ git push origin YOUR_BRANCH
```

## Renaming a file

The command line can be used to rename any file in a repository. 

While many files can be renamed on the GitHub website, some types of files *must* be renamed from the command line.
Images are one example.

1. Open Git Bash

2. Change the current working directory to your repository.

3. Rename the file with the following command. This will stage the change for commit.
```angular2html
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
```angular2html
$ git commit -m "commit message: file renamed"
```

6. Push the changes to GitHub.
```angular2html
$ git push origin YOUR_BRANCH
```

## Conclusion

By the end of this section, you will have successfully learned:

- How to resolve a merge conflict with competing line changes. 
- How to resolve a merge conflict with a file that has been edited *and* deleted. 

