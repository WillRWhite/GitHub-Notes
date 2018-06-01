### General Git Stuff

#### Configure Local Repo

git init  
git add .  
git commit -m "First commit"  

#### Push Local Repo to this Remote Repo

git remote add origin https://github.com/WillRWhite/holidayhomes.git  

\# Verifies the new remote URL  
git remote -v
git push -u origin master  

#### Clone

git clone https://github.com/WillRWhite/holidayhomes.git  

#### Synchronising Local Repo with this Remote Repo

git status  
\# Synchronise changes only  
git fetch origin  
git status  
\# The following two commands are only required if you have made changes to the local repo  
\# git reset --hard origin/master    
\# git clean -f -d  
\# now if required merge the changes  
git merge origin\master  
\# The following commands fetches and merges  
git pull  

### Other Useful Resources

#### Interacting with a remore Repo

https://help.github.com/articles/fetching-a-remote/  
https://stackoverflow.com/questions/17712468/what-is-the-difference-between-git-remote-update-git-fetch-and-git-pull  
