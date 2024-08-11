## Version Control
Use [[Command Terminal]]
![[Command Terminal]]

## Git
- `git init` see it with `ls -a`
- `git add file.txt` Staging area 
    - `git status` view the Staging area with 
-  `git commit -m “Complete Chapter 1 (present tense)”` Commit the files in staging area
    - `git log` view all the commits with 
- `git diff chapter3.txt` to see the differences.
- `git checkout chapter3.txt` to rollback to the last version.
## GitHub
### Git to Github
- `git remote add origin url` add a remote location called origin
- `git push -u origin master` push to remote (origin) and the branch (master)
###  .Gitignore
- **you should not upload your KEYs Passwords.**
- create a folder `touch .gitignore`
    - add the secrete files names in it
        - `.DS_store`
        - `secrets.txt`
        - `*.txt` to ignore all text files
        - `#comment things in it`
- [https://github.com/github/gitignore](https://github.com/github/gitignore)

### Cloning
- `git clone url`
	- you can check its `git log`

### Branching and Merging
- `git branch name` to create a new branch
- `git branch` to view all the branches
- `git checkout name` to switch to other branch
- `git merge name`
to exit vim `:q!`
- you can merge in GitHub

### Forking and Pull Requests
- collaborate with others with forking
	- `git fork`
- `git fetch` for your local repository.

