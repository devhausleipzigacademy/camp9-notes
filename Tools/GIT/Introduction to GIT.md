
It is a distributed version control software. By distributed it means, that a distributed [version control system](https://about.gitlab.com/topics/version-control/) (DVCS) brings a local copy of the complete repository to every team member’s computer, so they can commit, branch, and merge locally. The server doesn’t have to store a physical file for each branch — it just needs the differences between each commit[...](https://about.gitlab.com/topics/version-control/benefits-distributed-version-control-system/)

In simple words, we use GIT to track changes, undo changes,  swap between versions.



# Structure

![](https://miro.medium.com/max/1000/1*zw0bLFWkaAP2QPfhxkoDEA.png)



- Working Directory
	current stage of directory, this is where any modified files live. Modified means that you have changed the file but have not committed it to your database yet.

- Staging Directory
	staged means that you have marked a modified file in its current version to go into your next commit snapshot.

- Repository
	to reach here, you make a commit, which takes the files as they are in the staging area and stores that snapshot permanently to your Git directory.


So in a nutshell, if a particular version of a file is in the Git directory, it’s considered _committed_. If it has been modified and was added to the staging area, it is _staged_. And if it was changed since it was checked out but has not been staged, it is _modified_.


# Basic GIT commands

- `git init`
- `git status`
- `git add .` ( *here `.` specifies that every file in the current folder*)
- `git commit -m "put your message here"`
- `git checkout` *( put the name of the main/branch )*
-  `git checkout -b (put the name of the newBranch and checkout to that branch)`
- `git branch`
- `git branch (name of the new branch)`
- `git log --graph`
- `git push`
- `git fetch`
- `git merge`
- `git pull`  *is technically git fetch + git merge*


Note:  Merge could come with conflicts, when the same file had two different commits at two different part, resulting in differences between the two versions of the same file. In this case, GIT will ask us to fix the conflict manually, line by line.

![](https://blog.mergify.com/content/images/2021/08/image-3.png)


Note: When you commit, and just use `git commit` command, that will open vim. Since we might not want that, we could use `git commit -m "<put your comment here>"`
