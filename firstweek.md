# Report

completed by: Anastasiya Piotukh

## Install Nginx web server and git
worked under root user
* apt update
* apt upgrade -y
* apt install -y nginx git
* systemctl nginx start
  
## Fork GitHub repo https://github.com/joashp/material-design-template
Just clicked Fork on Just clicked Fork on https://github.com/joashp/material-design-template and chose my Github name

![Alt text](https://github.com/Piotukh/weekly-assessments/blob/main/1.png)

#### Configuration local repositories for pull and pull
* cd /home/piotukh
* mkdir develop #for updating index.html and pushing changes to Git
* cd develop
* git clone git@github.com:Piotukh/material-design-template.git
* cd /home/piotukh
* mkdir forassessment
* cd forassessement #for pull
* git clone git@github.com:Piotukh/material-design-template.git

#### Deployment of web-site on nginx web-server 

Edited files /etc/nginx/sites-available/default and /etc/nginx/sites-enabled/default in the same (change the working directory of nginx).

![Alt text](https://github.com/Piotukh/weekly-assessments/blob/main/2.png)

After that copied content of /home/piotukh/forassessment/material-design-template/www to /var/www/material-design-template/www (work directory of nginx)

## Setup a cron job for a regular (every 1 minute) checkout from main branch https://github.com/YOURNAME/mdt-fork
Created cron job

* crontab -e

![Alt text](https://github.com/Piotukh/weekly-assessments/blob/main/3.png)

* pull.sh

<p> #! /usr/bin/env bash
<p> cd /home/piotukh/forassessment/material-design-template
<p> git pull origin master
<p> echo "Pull "`date +"%T"`"" >> /var/log/cron.log
<p> cp -r /home/piotukh/forassessment/material-design-template/www/* /var/www/material-design-template/www/

![Alt text](https://github.com/Piotukh/weekly-assessments/blob/main/5.png)

## Update index.html from your machine, push changes to Git and confirm updated content on web page

* cd /home/piotukh/develop/material-design-template/www/
* vi index.html (Change “I love” to “I really love”)
* git push origin

One minute after push to origin content of site was updated.
  
![Alt text](https://github.com/Piotukh/weekly-assessments/blob/main/4.png)
  
## Configure local git hooks for validation of incoming commits (reject commits if there is a “shit” string in the files)
To configure local git hooks I created script pre-commit (did it executable) in /home/piotukh/develop/material-design-template/.git/hooks/

pre-commit
* #!/usr/bin/env bash
* /usr/bin/git diff HEAD > /var/log/diff.log
* changed_files=$(cat diff.log | grep shit)
* if [[ -z "${changed_files}" ]]
* then
*   echo "No shit detected"
* else
* 	echo "Shit detected"
* 	exit 1
* fi

## * Configure Nginx to Proxy Websockets and cache static content within 1 hour


## * Merge feature branch with main, rebase git merge commit, squash all commits
I did 2 commits in master branch, after that created feature branch. Did 2 commits in feature branch and 1 commit in master branch. After that I merged and resilved the conflict.
  
![Alt text](https://github.com/Piotukh/weekly-assessments/blob/main/6.png)
![Alt text](https://github.com/Piotukh/weekly-assessments/blob/main/7.png)  
  
git merge feature
  
![Alt text](https://github.com/Piotukh/weekly-assessments/blob/main/8.png)
  
git rebase feature
  
![Alt text](https://github.com/Piotukh/weekly-assessments/blob/main/9.png)

  git rebase --interactive --root # squash all commits
  
![Alt text](https://github.com/Piotukh/weekly-assessments/blob/main/11.png)
![Alt text](https://github.com/Piotukh/weekly-assessments/blob/main/10.png)
