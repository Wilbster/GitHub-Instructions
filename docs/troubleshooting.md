| **Symptoms** | **Probable Cause** | **Action** |
| ------------ | ------------------ | ---------- |
| Unable to commit your changes | File that you were working on had changes made to it | Use `git pull` to pull the changes first and resolve the merge issue before trying to commit your changes. |
|  | You did not add your files before trying to commit them. | use the command `git add <filename>` before trying to commit changes. |
|  | You used the wrong command to commit. | Use the command `git commit -m "<your comment here>"` to commit your changes. |
| Merge failed to resolve | There is a conflict between your local branch and the branch being merged. | Check the file that has a merge conflict using `git status` and decide on whether to discard changes or keep them within the file and use `git commit` afterwards to save changes.