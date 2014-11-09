## Common

Create the branch on your local machine

	git branch <branchname>

Push the branch on remote

	git push origin <branchname>

Switch to your new branch

	git checkout <branchname>

You can see all branches created by using

	git branch

Add a new remote for you branch

	git remote add <branchname> <url>

Push changes from your commit into your branch

	git push origin <branchname>

Delete a branch on your local filesytem

	git branch -d <branchname>

Delete the branch on remote

	git push origin :<branchname>

Delete remote branch

	git push origin --delete <branchname>
