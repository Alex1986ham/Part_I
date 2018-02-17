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
- gitt add . (adds all existing files to the repo)
