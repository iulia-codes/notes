Clone a repository:

git clone repo_name

Show all branches of a repository:

- show all remote and local branches
  git branch -a
- show all local branches
  git branch -r
  
Create a new branch:
 -  git checkout -b new_branch_name
  
Checkout a specific branch (where branch_name is the name of the branch you want to checkout):
  - git fetch --all
  - git checkout branch_name
  
Ignore files without adding them to .gitignore

- edit .gitconfig

[alias]
  ignore = update-index --assume-unchanged
  unignore = update-index --no-assume-unchanged
  
- add the desired file

git ignore myFile.extension

- remove the file from being ignored

git uningnore myFile.extension


  
  
  
