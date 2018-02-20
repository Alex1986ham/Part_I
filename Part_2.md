# Terminal operations

- cd
- cd ..
- pwd
- ls
- ls -l dropbox/*.pdf
- mkdir (creates a new directory somewhere)
- mkdir dropbox/new
- mv (moving documents from one directory to an other) example: mv info.txt new/ (will move the txt file to the folder new
- curl http://google.com (shows the html file in terminal
- curl -o google.html -L http://google.com (creates an html file in current directory)
- cat dictionary.txt (reads all the content of the file diectionary.txt)
- less dictionary.txt (reads all the contet but much better to read)
- inside of less use /goobers (to search for the word goobers
- rm dictionary.txt (removes the file without questioning)
- rm -i dictionary.txt (removes with questioning)
- remdir terribleDirectory (removews directory)

- grep shell dictionary.txt (check if a word is in the file, word search for is shell)
- grep shell dictionary.txt | less (same as before just one page)
- curl -L https://tinyurl.com/zeyq9vc | grep (search inside of the site for a particular wordk without saving it somewhere)
- curl -L https://tinyurl.com/zeyq9vc | grep fish | wc -l (as before, to count how many searches where found)
- curl -L https://tinyurl.com/zeyq9vc | grep -c fish (same as before, just an other way)

- look for .bash_profile how to change it

- Shell resources
- The Bash Academy
- Bash Beginners Guide
- Bash Programming HOWTO
- Regexr — Learn Regular Expressions


# Git 

## Types of different git commands:

- git init (creates space in the directory for the git repo)
- git clone link (gets the repo in the current working directory)
- git status (gives the status of the current repo)
- git log (displays information about the existing commits)
  - git log --oneline (shows shorter information about all commits)
  - git log --stat (shows information about changed files)
  - git log --patch (or) git log -p (shows very detailled information about any changes in the files)
  - git log -p fdf5493 (will start showing at a particular SHA and all the previous commits)
- git show (diesplays the info abou the last commit)
- git show fdf5493 (shows info about a particular commit and nothing lese (by default it shows -p)) 
    git show could be combined with --stat / -p / -w

## Putting all files to staging aread, from where they could be commited

- git add index.html (puts the file to the staging aread)
- git rm --cached index.html (removes the file from the staging area back to nomrmal repo)
- git add . (adds all existing files to the repo)
- git commit (to commit changes through atom, atom will be opend)
- git commit -m "initial commit..." (will make a commit with the text initial commit)

### Writting commit messages

Do

- do keep the message short (less than 60-ish characters)
- do explain what the commit does (not how or why!)

Do not

- do not explain why the changes are made (more on this below)
- do not explain how the changes are made (that's what git log -p is for!)
- do not use the word "and"
  - if you have to use "and", your commit message is probably doing too many changes - break the changes into separate commits
  - e.g. "make the background color pink and increase the size of the sidebar"
Checkout udacity standards of making commits: https://udacity.github.io/git-styleguide/

- git diff (shows the uncommited changes in comparison to the last commit)
- touch test.txt (adding a document to the current directory)
- by adding a file .gitignore all files in this directory will be ingnored by commits to the repo


### Taggin

- git tag -a v1.0 -m "1st version" (creates a tag to the current commit, exmpl. version or something)
- git tag (displays just all tags existing)
- git tag -d v1.0 (for deleting a tag / git tag --delete works also)
- git tag -a v1.0 a87984 (will add a tag to a past commit)

### Branching

- git branch (If we type out just git branch it will list out the branches in a repository)
- git branch sidebar (will add a new branch named sidebar to the repo)
- git checkout sidebar (changing to the branch sidebar)
- git branch beta-version 42a69f (will create a new branch at a specific commit)
- git branch -d sidebar (will delete the branch sidebar, but first need to change to master)
- git branch -D sidebar (this is a hard deleting of a branch, which has commits on it, which aren't available in an other branch)
- git checkout -b footer master (does 2 things in one: creates under master a new branch named footer)
- git log --oneline --decorate --graph --all (seeing all versions on all branches)

### Merging

- git merge <name-of-branch-to-merge-in> (beeing in masters branch a sidebar branch will be merged to master branch)
- git reset --hard HEAD^ (turns a merge back)

### Undoing changes

- git commit --amend -m "..." (to update the most-recent commit instead of creating a new one)
- git revert <SHA-of-commit-to-revert> (When you tell Git to revert a specific commit, Git takes the changes that were made in commit and does the exact opposite of them)
- git reflog (You've got to be careful with Git's resetting capabilities. This is one of the few commands that lets you erase commits from the repository. If a commit is no longer in the repository, then its content is gone.
To alleviate the stress a bit, Git does keep track of everything for about 30 days before it completely erases anything. To access this content, you'll need to use the git reflog command. Check out these links for more info)

- git reset <reference-to-commit> (The git reset command is used to reset (erase) commits)
  it could be used to...:
    - move the HEAD and current branch pointer to the referenced commit
    - erase commits
    - move committed changes to the staging index
    - unstage committed changes
- git reset --mixed HEAD~1 (will move the last commit to working directory)
- git reset --soft HEAD~1 (will move the last commit to staging index)
- git reset --hard HEAD~1 (will move the last commit to trash, where it will be available for 30 days)
- git branch backup (before reset a commit, create a backup)

### Create connection from local repo to a repo on github

- git remote add origin https://github.com/Alex1986ham/my-travel-plans.git (this links comes from creating a new repo on github)
- git push origin master (pushing all commits from local to remote on github)
- git log --oneline --graph --decorate --all (showing all information about repo)
- git pull origin master (gets changed commits from origin to the local repo)
- git fetch origin master (Git fetch is used to retrieve commits from a remote repository's branch but it does not automatically merge the local branch with the remote tracking branch after those commits have been received)
- git merge origin/master (will join the new branch called origin/master to the existing master branch)

### Forking

Forking is an action that's done on a hosting service, like GitHub. Forking a repository creates an identical copy of the original repository and moves this copy to your account. You have total control over this forked repository. Modifying your forked repository does not alter the original repository in any way.

### When many people working on same project

- git shortlog (overview of all commits)
- git shortlog -s -n (with the -s -n flags to show only the number of commits each author has made, sorted numerically.)
- git log --author=Surma (The output displays only the commits that Surma made)
- git show 5966b66 (see an example of extra details in a commit)
- git log --grep=bug
$ git log --grep bug (filter down to just the commits that reference the word "bug")

### Pull request

A pull request is a request for the source repository to pull in your commits and merge them with their project. To create a pull request, a couple of things need to happen:

you must fork the source repository
clone your fork down to your machine
make some commits (ideally on a topic branch!)
push the commits back to your fork
create a new pull request and choose the branch that has your new commits

### Origin vs Upstream Clarification

One thing that can be a tiny bit confusing right now is the difference between the origin and upstream. What might be confusing is that origin does not refer to the source repository (also known as the "original" repository) that we forked from. Instead, it's pointing to our forked repository. So even though it has the word origin is not actually the original repository.

Remember that the names origin and upstream are just the default or de facto names that are used. If it's clearer for you to name your origin remote mine and the upstream remote source-repo, then by all means, go ahead and rename them. What you name your remote repositories in your local repository does not affect the source repository at all.

#### Rename remote names

- git remote rename mine origin
- git remote rename source-repo upstream

### Stay sync with source project

When working with a project that you've forked. The original project's maintainer will continue adding changes to their project. You'll want to keep your fork of their project in sync with theirs so that you can include any changes they make.

To get commits from a source repository into your forked repository on GitHub you need to:

get the cloneable URL of the source repository
create a new remote with the git remote add command
use the shortname upstream to point to the source repository
provide the URL of the source repository
fetch the new upstream remote
merge the upstream's branch into a local branch
push the newly updated local branch to your origin repo

### Rebase commits

- git rebase -i HEAD~3 (Using git rebase creates a new commit with a new SHA. When I tried using git push to send this commit up to GitHub, GitHub knew that accepting the push would erase the three separate commits, so it rejected it. So I had to force push the commits through using git push -f)

#### When to rebase

As you've seen, the git rebase command is incredibly powerful. It can help you edit commit messages, reorder commits, combine commits, etc. So it truly is a powerhouse of a tool. Now the question becomes "When should you rebase?".

Whenever you rebase commits, Git will create a new SHA for each commit! This has drastic implications. To Git, the SHA is the identifier for a commit, so a different identifier means it's a different commit, regardless if the content has changed at all.

So you should not rebase if you have already pushed the commits you want to rebase. If you're collaborating with other developers, then they might already be working with the commits you've pushed. If you then use git rebase to change things around and then force push the commits, then the other developers will now be out of sync with the remote repository. They will have to do some complicated surgery to their Git repository to get their repo back in a working state...and it might not even be possible for them to do that; they might just have to scrap all of their work and start over with your newly-rebased, force-pushed commits.

I recommend that you create a backup branch before rebasing, so that it's easy to return to your previous state. If you're happy with the rebase, then you can just delete the backup branch!
