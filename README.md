DWP Deployment Plan With Git Hooks and Production Deployment
===
##Lyte
####Spin Up Server
1.Create new droplet on Digital Ocean

2.SSH into server
  * ssh root@[IPaddress]

3.Change Password and create your admin user in the sudo group
  * sudo adduser [username]
  * sudo adduser [username] sudo
4.Logout as root and login as new sudo user

5.Run commands to update your server

  * sudo apt-get update
  * sudo apt-get upgrade
  * sudo apt-get update

  ####Apache Install and Config
 
1.Install Apache 2
  * sudo apt-get install apache2

####Git

1.Change permissions and remove index file
 * sudo chown [username] ./www/
 * rm index.html

2.Inside /var create repos directory
 * cd /var
 * sudo mkdir repos
 * sudo chown [username] repos
 * cd repos/

3.git folder in repos directory
 * mkdir [reponame].git
 * cd reponame.git/

4.Bare git init
 * git init --bare
 * cd hooks/

5.In hooks directory make executable file
 *pico post-recieve
 *in that file write #!/bin/sh
GIT_WORK_TREE=/var/www git checkout -f
 *chmod +x hooks/post-receive

6.New Terminal Window go to where your files are
 *cd projects/
 *cd lab4/
 *git init
 *git add -A
*git commit -m "some text here"

7.Add Remote
 *git remote add [var name]ssh://[username]@[IPADDRESS]/var/repos/reponame.git/
 *git push [var name] master

