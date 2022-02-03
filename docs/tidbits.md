# January 2022

## Deleting local git repositories only

( When they get too many)

I found an easy way to quickly delete all merged branches incase you need to
tidy up your repository:

```
git branch --merged | grep -v \* | xargs git branch -D
```

I found this to only work on a `Linux` terminal and wouldn't work on PowerShell. Powershell adds a question mark to the end of the branch name and this causes it to not find the branches hence can't delete the branch.

Incase you already have a branch that is protected, or just want to delete all branches locally except master/main (No offence for master, we might have branches that are still using master), you can use this command:

```
git branch | grep -v "master" | xargs git branch -D
```

Hope that solves your problem!

# February 2022

## Storing Git Remote Credentials in Ubuntu Unencrypted
Hi there.
Are you using Ubuntu and keep getting the prompt to enter your Github/Gitlab credentials? 

Well, there is a way to store the credentials but there is a catch. It is unencrypted as it is stored as a plain text file on your file system. 
If you don't mind the caveat, head over to your terminal and type this:

```
git config --global credential.helper store
```
Then type:
```
git pull
```
Enter your credentials and you are good to go, but be careful, some malicious NPM Modules may extract the credentials and use them to do EVIL!!
