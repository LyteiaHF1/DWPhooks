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
