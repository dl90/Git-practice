# Rebasing vs Merging Lab

Instructions:

For the 50 minutes that we have with each other in Collaboration Tools today, I want you to understand the difference between rebasing and merging. When you are finished understanding the differences between the two, answers the questions below, and submit them to your instructor as a notion link before the end of class. 

Official Documentation:

[https://git-scm.com/book/en/v2/Git-Branching-Rebasing](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)

Understanding Rebase:

[https://www.youtube.com/watch?v=f1wnYdLEpgI](https://www.youtube.com/watch?v=f1wnYdLEpgI)

Understanding the Implications of a Rebase versus a Merge:

[https://hackernoon.com/git-merge-vs-rebase-whats-the-diff-76413c117333](https://hackernoon.com/git-merge-vs-rebase-whats-the-diff-76413c117333)

Question 1: Under what circumstances **should we consider** using *rebase* instead of merging? What about using merge instead of rebase? Discuss the benefits and disadvantages of both sides.  

    Merging creates one single commit on the master branch.
    All the changes in the feature branch are grouped together and commited as one commit.
    If you look at the history of master, each merge will be represented as a commit along
    with the branchs commit history.
    
    Merge commits may clutter up your git log, making any senior developer reading you git log not have a good time.
    Any significant changes to the code base is a good use case for merging.
    These can be used to identify significant milestones.
    
    Rebasing moves the base of your current branch to another position.
    This is useful when you want to update your version of master with the newest master and work from that.
    It also points out and gives you an opportunity fix any conflicts your branch might have with the newest version of master.
    Rebasing does not create extra commits and this reduces "commit history clutter" on your git history.
    One thing to note is that the feature branches commit history will will be different following a git rebase.
    This may cause conflicts with other branches if they are based on the rebased featuer branch.
    So, dont rebase your branch unless you are the only person working on it or,
    there are no git branches branching away from your feature branch.
    
    git merge should be used when you want to group a set of commit history together.
    git rebase should be used when you want to keep a linear, simple to read commit history.
    git rebase should not be used on a shared feature brach as:
    	it changes all the commit history
    	any braches that branched off prior to the rebase will have different commit history,
    	causing them to have conflicts when they want to update or remerge back in to the main feature branch.
    	

Question 2: Are there any dangers that exist in using either merge or rebase? How can we avoid these dangers?

    Rebasing is difficult to revert becuase it changes all of the commit history.
    One way to avoid any problems is to make another branch to rebase your changes 
    so you will still have the pre-rebased branch if somthing wrong happens.
    
    Merging is easier easier to revert by using:
    	git reset --hard <commit hash>
    		this resets your current branch back to the commit hash version
    	git push origin HEAD --force
    		this sets the origin head to the commit hash version
    This also means you will LOSE YOUR WORK. 
    
    So regardless if you are rebasing or merging, make another branch to store your work
    incase you need to undo the rebase or merge just to be safe.

Question 3: Create a scenario below in which you are working on a project and you need to either rebase or merge. Write out the code for how you would do a rebase. Make sure you include the correct git commands.

    Scenario: You created a branch off dev to work ony your feature. The dev branch is
    updated and you want to update your branch to see what what the update was, and
    most importantly, if there may be conflicts with what you are currently working on,
    giving you an opportunity to update your code and resovle merge conflicts and
    integration problems when you finish your feature.
    
    If you are the only person working on this feature (assuming you are currently on 
    your feature branch) :
    	git rebase dev
    	...
    everything looks good, no conflicts and you are ready to merge your feature to dev
    	git checkout dev
    	git merge feature / git push origin dev
    
    If you are on a team working on this feature and your team members branch are all 
    based off of your feature branch :
    	git fetch dev
    resolve any issues if it occures.
    	git commit origin feature
    Tell your team members to update their branch with git fetch.
    Once your team memerbs are finished...
    	git checkout feature
    	git merge feature-1
    	...
    	git merge featuer-2
    	git checkout dev
    	git rebase dev
    	git merge feature / git push origin dev
    This will merge your team members branches to the feature branch, then merge the
    feature branch to the dev branch.

Question 4:

What is the difference in "commit history" when you do a rebase versus a merge.

    When you use git rebase, you are changing all of your commit history because git 
    takes each of those commits and creates a new commit based on the rebased base.
    This is why rebase should only be done if there are no child branches because merging
    those child branches will generate conflicts due to different commit history.
    Commits after git rebase produces a much cleaner commit history as it essentally shows
    up as commits on the same branch.
    
    When you use git merge, git creates a new commit by combining everything and commits
    it to the branch you call merge from. Git merge adds many nodes and branching flows 
    on the git history because it details merged branch commits as well and may add clutter
    to your git history.