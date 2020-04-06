# Collaboration Tools Lab March 6th

Often times, when I look at the commits many of you are making to your projects, I see cases of some of you forgetting to add commit messages, mistyping commands, etc. 

Git hooks is a solution which allows you to ensure certain conditions are met before commits are done.

For today's 1 hour lab, I want you to show the following:

1) What is a git hook, and where are they stored?

    A git hook is a script (which can be in any language) that is executed whenever a
    git event occurs. Git hooks are stored in the hidden git directory .git/hooks and
    is automatically created when git is initialized. By default git includes several
    sample hooks. These files ends with .sample and are meant to serve as a guid/list
    of all the possible hook events.

    The names of the files are important and must match exactly like the sample files.
    The sample hooks are deactivated and will be ignored when the event occurs, to
    activate, remove the .sample at the end of the file.

2) What benefit do git hooks provide your team?

    Git hooks can be used ensure certain things are met before your collaborators are
    able to push anything to the git repository. This could be setup on the client side
    or the server side. Git hooks coverage is more extensive on the client side when
    compared with the server side.

3) What are the different kinds of git hooks that are available? Provide 3 examples. 

    On the client side:
    	1. pre-commit
    	2. commit-msg
    	3. pre-rebase

    pre-commit: linting and some type of test to ensure any changes to the code is not
    breaking any existing functionality.

    commit-msg: check the comment to ensure it meets required format.

    pre-rebase: check there are no other branches based on the branch to be rebased.

    On the server side:
    	1. pre-receive
    	2. update (all branches)
    	3. post-receive
    
    pre-receive: check and reject rebased pushes. Checks changes to certain files
    matches certain users before accepting.
    
    update: check update is pushing to approprate branch for all branch pushes.
    
    post-receive: updates server after push, send notifications.

4) How is "Husky" related to git hooks. You will need to look into husky here:

[https://github.com/typicode/husky](https://github.com/typicode/husky)

    Husky simplifies setting up client sided git hooks to all your collaborators by
    allowing you to use existing npm packages as part of git hooks. This makes it easier
    for your your collaborators to have the same git hooks without having to manually
    add them to their git repo.
    
    After installing husky, it generates a script for each of the git hooks. You can
    then assign specific checks by modifying package.json:
    
    "husky": {
        "hooks": {
          "pre-commit": "lint-staged"
        }
      },
    
    this adds a pre-commit hook which calls "lint-staged", a npm package allows you to
    run your code through linters to check for typos or bad styling prior to commits.

5) Provide a link to a git repository you created that uses git hooks. I will be able to see them when I clone your repository. Also mention the git hooks you used and what function they provide for you. You only need to use 2 hooks.

    Link to your repository: https://github.com/dl90/Git-practice
    Hooks used:
    1) lint-staged, checks all JavaScript files for bad styling prior to commit.
    2) commitlint, enforces conventional commit messages.

Understanding Git hooks

[https://www.digitalocean.com/community/tutorials/how-to-use-git-hooks-to-automate-development-and-deployment-tasks](https://www.digitalocean.com/community/tutorials/how-to-use-git-hooks-to-automate-development-and-deployment-tasks)

[https://www.vojtechruzicka.com/githooks-husky/](https://www.vojtechruzicka.com/githooks-husky/)