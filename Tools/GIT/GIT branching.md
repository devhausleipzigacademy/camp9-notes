A branch in Git is simply a lightweight movable pointer to commits. The default branch name in Git is `main`. As you start making commits, you’re given a `main` branch that points to the last commit you made. Every time you commit, the `main` branch pointer moves forward automatically.

<iframe src="https://learngitbranching.js.org/" height="1024" width="800">Git Branching Game</iframe>


Note: When working on a feature branch, always pull/merge the updated main into your branch first, before merging the feature branch into the main. This will help you to avoid merge conflicts.