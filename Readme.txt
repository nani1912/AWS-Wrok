GIT installation on AWS Instance:

1. Shre this AWS instance key on your git repository.
2. mkdir gitrepo ## Here creating a new directory for git 
3. git init ## change to new directory and hit this command (initilizing the git repository)
4. ls -la ## We can check the hidden files in .git
5. git add . ## Adding all files to git repo staging dir
6. git commit -m "This is my initial commit" ## commit the added folder from staging dir 
7. git remote add origin https://github.com/nani1912/AWS-Wrok.git ## connecting the remote git account 
8. git push -u origin master ## push the created files into git account 

(a. git config --global user.name "[name]" Sets the name you want attached to your commit transactions
b. git config --global user.email "[email address]" Sets the email you want attached to your commit transactions
c. git config --global color.ui auto Enables helpful colorization of command line output)
