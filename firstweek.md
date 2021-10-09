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



After than copy content of /home/piotukh/forassessment/material-design-template/www to /var/www/material-design-template/www





![image](https://user-images.githubusercontent.com/63563263/136674445-2dde743d-7f61-4aef-b849-1237410749f4.png)


## Setup a cron job for a regular (every 1 minute) checkout from main branch https://github.com/YOURNAME/mdt-fork



### Update index.html from your machine, push changes to Git and confirm updated content on web page

### Configure Github hook instead of cron

### * Configure Nginx to Proxy Websockets and cache static content within 1 hour

* Merge feature branch with main, rebase git merge commit, squash all commits

