# Packages
List of free and personal software packages





## How To Add and Update Git Submodules
Git submodules are most of the time used in order to incorporate another versioned project within an existing project.
Submodules can be used for example in order to store third-party libraries used by your main project in order to compile successfully.
In order to keep up with the changes made for those third-party libraries, you choose to include projects as submodules in your main project.


#### Add a Git Submodule
do this only for the first time
```
git submodule add <remote_url>

git commit -m "Added the ... submodule to the project."

git push

git submodule update --init --remote
```

#### PULL latest of all git submodules  
**be carefull. This command clear local changes**
```
git submodule update --recursive --remote
```


#### PUSH a Git Submodule
```
git submodule update --remote --merge
```


#### Remove Submodule
- Delete the section referring to the submodule from the .gitmodules file
- Stage the changes via git add .gitmodules
- Delete the relevant section of the submodule from .git/config.
- Run git rm --cached path_to_submodule (no trailing slash)
- Run rm -rf .git/modules/path_to_submodule
- Commit the changes with `git commit -m "Removed ... submodule"`
- Delete the now untracked submodule files rm -rf path_to_submodule
