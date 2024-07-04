- - -

![[Pasted image 20240307162924.png|800]]
1. First go inside the working directory, and type ```git commit``` so that Git can track the Working Directory.

![[Pasted image 20240307163258.png|800]]
2. Type ```git add ./``` to add al the files inside the working directory to the staging Area.

![[Pasted image 20240307163415.png|800]]
3. Type ```git commit -m "Type a message here"``` to commit the files inside the Got repository.

4. Then Create a Remote ```git remote add origin <url of github repository>```. Basically we are creating a remote git repo named origin.
5. Then Type ```git branch -M main```  to RENAME the default branch in Github from 'master' to 'main'. 


![[Pasted image 20240307165448.png]]
6. Type ```git push -u <remote name> <branch name>```.  Pushing the local repo to the Remote Repository. OR ```git push -u origin main```



The command `git push -u origin main` is used in Git to push the local branch named `main` to the remote repository called `origin`. Let's break down each part of the command:

- `git`: This indicates that the command is being executed within the Git version control system.
    
- `push`: This is the Git subcommand used to push commits from the local repository to a remote repository.
    
- `-u`: This is an option that stands for "upstream." It is used to set the upstream branch for the current local branch. When you use `-u` followed by `origin main`, you are telling Git to set the remote `main` branch as the upstream branch for the local `main` branch. This means that in the future, when you run `git push` without specifying a branch, Git will automatically push to the remote `main` branch.
    
- `origin`: This is the name of the remote repository. In Git, "origin" is the default name given to the remote repository from which the local repository was cloned. However, you can rename it to something else if needed.
    
- `main`: This is the name of the branch you want to push to the remote repository. In this case, you're pushing the changes from the local `main` branch to the remote `main` branch.
    

When you execute `git push -u origin main`, Git will transfer the commits from your local `main` branch to the `main` branch on the remote repository specified by `origin`. The `-u` flag sets up tracking between the local and remote branches, making it easier to push changes in the future without specifying the branch name and the remote repository.
