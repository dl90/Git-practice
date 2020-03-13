## cloning vs fetching vs pulling

> git cloning creates a copy of the repository with the original repository linked under branch --remotes
  git fetching updates all the remote tracked branches
  git pull merges the git fetch content from the remote master branch to the current master branch

> You and your team are working on a project, its hosted on github and you clone the repository.
  Using git clone you can create a copy of the repo and it will still retain its link to the repository holder.
  If you are a calibrator of the repo you cloned from you can also push to the repository you cloned from.
  If a member of your team made some changes to the repo and pushed it. You can take a look at the updates by using git fetch.
  If the update looks good and you don't need to take a second look at it, you can use git pull to automatically fetch and merge the new material.

> You see another students repo of the same assignment. You use git clone to clone the repository. You delete the .git
  and reinitialize git with git init. This deletes the git history and any links to the repo you cloned from.
  Git assumes you created the code and when you push the history shows you are the sole contributor of the repo.

## Trello vs Asana

| Trello | Asana |
| ------ | ----- |
| Manually prioritize | Prioritize work requests and dependencies |
| Assign team member to tasks | Connect work across teams |
| Task checklist | Manage team member workload |
| Parent child relationship between cards | Feedback and approvals |

## Third Section

_Question 1: What is the .git folder? Where is the object database in this folder?_

> The .git folder is a hidden folder that enables its version control ability.
  It is how git keeps track of files, file structure, commit history and dates.
  The object database in this folder is what holds the the contents of the files.
  These are stored as a blob (binary large object) and the filename of the blobs are hashed values.

_Question 2: Explain in detail how the git hash-object function works._

> git hash-object creates a blob file in the .git/objects folder.
  This is done by passing it a file *git hash-object filepath -w*.
  An example would be git hash-object ../index.html -w
  the -w switch tells git to actually write the object in to the objects folder.
  Calling this returns a hash, which is the filename of the blob.
  This hash is created by passing parameters such as file length and content to SHA-1.
  This means that any changes to the file will produce a different hash and this is how git knows a change occurred to a file.
  
_Question 3: Where does git internally store the file names to our files? How are tree objects related to this?_

> File names are stored in tree objects. Tree objects are like databases linking the path and relationship describing files tracked by git.
  Each row in the tree object is a reference to other blobs and trees. There are four columns of info.
  The first column stores file permissions info(read write).
  The second column stores the file type (blob/tree).
  The third column stores the SHA-1 hash.
  The forth column stores the name of the file/folder in plain text.
  This is how the filenames and folder names are stored in git.
  By doing this git can also track any file path changes such as moving a file from one directory to another and etc.