
### Working Directory -> Staging Area
Start a git project in an empty folder : ```git init```
Track Staging Area : ```git status```
Add file to Staging Area : ```git add [filename]```
Add all files in the directory to Staging Area : ```git add .```
Delete file from Staging Area + Directory : ```git rm -f [filename]```
Delete file from Staging Area : ```git rm --cached [filename]```

----
### Before Commit
Before Starting commit you need 2 things :
- Email
- Name

```git config --global user.email "email@email.com"```
```git config --global user.name "Name"```

---

### Commit

Commit with an message (only Staging Area file) : ```git commit -m "Your Message Here"```
Commit with all files not only files in Staging : ```git commit -a -m "Your Message Here"```
See list of all commit : ```git log```

---

### Checkout

To go back to a commit : ```git checkout [commit_number]```
To go back to where we were: ```git checkout master```

---

### Go back To a old Commit

2 ways to go back permanently to a commit : 

Git revert (Add a new commit and keep the old one too): ```git revert [commit_number]```
Revert the revert : ```git revert [revert_number]```

Git reset 
- Go back permanently without a commit: ```git reset --hard [commit_number]``` 
- Only reset the commit name and description(not the file): ```git reset --soft [commit]```
- Remove from Staging Area all files and move back (default): ```git reset --mixed [commit]```

---

### How to ignore files 

In the directory create a file name : ```.gitignore```
In the ```.gitignore``` file add the names of the files you want untracked
Add the ```.gitignore``` to the tracked files : ```git add .gitignore``` 
If added after the start of a project do this : ```git rm -r --cached . ```
To ignore a complete directory(In the ```.gitignore```) : ```[DirName]/** ```

----

### Branches


Create a new branch : ```git branch [name]```
Create a new branch and automatically switch to it : ```git checkout -b [name]```
List branch : ```git branch -a```
Change to another branch : ```git checkout [branch_name]```
Delete a branch : ```git branch -d [name]```

2 way to merge a branch :
- Merge to the branch your working on : ```git merge [name_of_branch]```
- Merge A source branch to a target branch : 

---
#### Steps to take before starting Git & GitHub
- Copy your **ssh key** to GitHub Account
- Add origin with **SSH** and not **HTTPS**
- Before pulling change your branch to main

---

### How to works with Git & Gitub
- Create a new repository on GitHub
-  Get the URL for the project
- Initialise the Repo : ```git init```
- Add an origin :```git remote add origin [Url(SSH)]```
- To see if it works : ```git remote -v```

Now the Local Directory and the GitHub ones are connected

#### Pushing and Pulling

Before pushing you need to change your branch name to main: ```git checkout -b main```
And after you could push
##### Pulling
- Pull all of the files from the origin : ```git pull```
- Pull only a certain branch from the origin : ```git pull origin [branch]```

##### Pushing
(To Push you need to use it with ssh keys)
In your local  computer :```ssh-keygen -b 4096```
In GitHub Settings look for Add New SSH Key
Add The Public Key
Try the connection with : ```ssh -T git@github```  if it works you will see it

- Push back to GitHub : ```git push -u origin main```

---

Example of working with a merge :

```bash
git branch error
git checkout error
echo "Erreur regler" > nono.txt 
mv nono.txt toto.txt git add . 
git commit -m "Erreur regler" 
git checkout main git merge error 
git add . 
git commit -m "Error merger sur main" 
git push -u origin main
git branch -d error
```

---

To push another branch you need to push it using :```git push origine [branch_name]```

---

To delete a branch in GitHub from Git : ```git push origin --delete [branch_name]```


----

To change origin : ```git remote set-url origin  [new_url]```
