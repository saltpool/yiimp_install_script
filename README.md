# Ubuntu 22.04 Yiimp install script v0.2 (February, 2024)

## Install script for yiimp on Ubuntu Server 22.04
USE THIS SCRIPT ON FRESH INSTALL UBUNTU Server 22.04, with PHP 8.2 and Yii Framework 1.1.29!

# What's new in v0.2
- New colour themes for Yiimp (24 'themes' to choose from)

## v0.1
- Ubuntu 22.04 support
- PHP 8.2
- Yii Framework 1.1.29

## Do not use in a production environment yet, testing only.

Connect on your VPS =>

- apt update
- apt upgrade
- reboot
- adduser pool (pool it's just an example...)
- adduser pool sudo
- su - pool
- exit
- su - pool
- sudo apt -y install git
- git clone https://github.com/craiglyoung/yiimp-cly.git
- cd yiimp-cly
- bash install.sh (DO NOT RUN THE SCRIPT AS ROOT or SUDO)
- At the end, you MUST REBOOT to finalize installation...

Finish !

- Go http://xxx.xxx.xxx.xxx or https://xxx.xxx.xxx.xxx (if you have chosen LetsEncrypt SSL). Enjoy !
- Go http://xxx.xxx.xxx.xxx/site/AdminPortal or https://xxx.xxx.xxx.xxx/site/AdminPortal to access Panel Admin

###### :bangbang: **YOU MUST UPDATE THE FOLLOWING FILES :**

- **/var/web/serverconfig.php :** update this file to include your public ip (line = YAAMP_ADMIN_IP) to access the admin panel (Put your PERSONAL IP, NOT the IP of your VPS/server). Update with public keys from exchanges. Update with other information specific to your server..
- **/etc/yiimp/keys.php :** update with secrect keys from the exchanges (not mandatory)
- **If you want change 'AdminPanel' to access Panel Admin :** Edit this file "/var/web/yaamp/modules/site/SiteController.php" and Line 11 => change 'AdminPanel'

###### :bangbang: **IMPORTANT** :

- The configuration of yiimp and coin require a lot of knowledge of linux & many beers and hair pulling...
- Your mysql information (login/Password) is saved in **~/.my.cnf**

---

###### :bangbang: **THEMES**
- Once in the admin control panel, click on the Dashboard button. Then down then bottom, click on "Theme Manager"
- Once in the theme manager, select which theme you would like to set the website to use and save.
- There is either a "light" and "dark" symbol next to each theme - these will use different logo files, so make sure you create an approprpriate one. logo.png for light, and logo-dark.png for dark. Place whichever is appropriate into the /images directory.
- If you need change the CSS of a theme, it can be found in the appropriate /extensions/jquery/themes directory. You may need to clear your browser cache to see any changes.
- Create a pull request if you want any other themes added. You can create them easily at https://jqueryui.com/themeroller/

###### This script has an interactive beginning and will ask for the following information :

- Server Name (no http:// or www !!!!! Example : example.com OR pool.example.com OR 80.41.52.63)
- Are you using a subdomain (pool.example.com)
- Enter support email
- Set stratum to AutoExchange
- Your Public IP for admin access (Put your PERSONAL IP, NOT IP of your VPS)
- Install Fail2ban
- Install UFW and configure ports
- Install LetsEncrypt SSL

---

**This install script will get you 95% ready to go with yiimp. There are a few things you need to do after the main install is finished.**

Ssome server security has been added to the script, but it is every server owner's responsibility to fully secure their own servers. After the installation you will still need to customize your serverconfig.php file to your liking, add your API keys, and build/add your coins to the control panel.
