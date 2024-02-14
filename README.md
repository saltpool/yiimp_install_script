# Ubuntu 22.04 Yiimp install script v0.3 (February, 2024)

## Install script for yiimp on Ubuntu Server 22.04
USE THIS SCRIPT ON FRESH INSTALL UBUNTU Server 22.04 only.
Will install PHP 8.2 and Yii Framework 1.1.29, with a customised Yiimp!

# What's new in v0.3
- MOTD

## v0.2 details
- New colour themes for Yiimp (24 'themes' to choose from)

## v0.1 details
- Ubuntu 22.04 support
- PHP 8.2
- Yii Framework 1.1.29

Connect on your VPS =>

- apt update
- apt upgrade
- reboot
- adduser pool (pool it's just an example...)
- adduser pool sudo
- su - pool
- exit
- su - pool
- git clone https://github.com/saltpool/yiimp_install_script
- cd yiimp
- bash install.sh (DO NOT RUN THE SCRIPT AS ROOT or SUDO)
- At the end, you MUST REBOOT to finalize installation...

Finish !

- Go http://xxx.xxx.xxx.xxx or https://xxx.xxx.xxx.xxx (if you have chosen LetsEncrypt SSL). Enjoy !
- Go http://xxx.xxx.xxx.xxx/site/adminRights or https://xxx.xxx.xxx.xxx/site/adminRights (or whatever you set this as) to access Panel Admin

###### :bangbang: **YOU MUST UPDATE THE FOLLOWING FILES :**

- **/var/web/serverconfig.php :** Update with public keys from exchanges, if you're going to use exchanges. Update with other information specific to your server.
- **/etc/yiimp/keys.php :** update with secrect keys from the exchanges (mandatory only if you're going to use exchanges)
- **If you want change 'adminRights' to access Panel Admin :** Edit this file "/var/web/yaamp/modules/site/SiteController.php" and Line 11 => change 'adminRights'

###### :bangbang: **IMPORTANT** :

- The configuration of yiimp and coins require a lot of knowledge of linux, along with many beers and hair pulling...
- Your mysql information (login/Password) is saved in **~/.my.cnf**

---

###### :bangbang: **THEMES**
- Once in the admin control panel, click on the Dashboard button. Then down then bottom, click on "Theme Manager".
- Once in the theme manager, select which theme you would like to set the website to use and save.
- There is either a "light" and "dark" symbol next to each theme - these will use different logo files, so make sure you create an approprpriate one. logo.png for light, and logo-dark.png for dark. Place whichever is appropriate (or both) into the /images directory.
- If you need change the CSS of a theme, it can be found in the appropriate /extensions/jquery/themes directory. You may need to clear your browser cache to see any changes.
- Create a pull request if you want any other themes added. You can create them easily at https://jqueryui.com/themeroller/

###### This script has an interactive beginning and will ask for the following information :

- The domain name (no http:// or www !!!!! Example : example.com OR pool.example.com OR 80.41.52.63)
- Whether you are using a subdomain (pool.example.com)
- A generic type name for your pool (used in MOTD)
- Your support email
- Whether you want to set stratum to AutoExchange
- Your Public IP for admin access (Put your PERSONAL IP, NOT the IP of your VPS/Server)
- Whether you want to install Fail2ban
- Whether you want to install UFW and configure ports
- Whether you want to install LetsEncrypt SSL (recommended)

---

**This install script will get you 95% ready to go with yiimp. There are a few things you need to do after the main install is finished.**

Some server security has been added to the script, but it is every server owner's responsibility to fully secure their own servers. After the installation you will still need to customize your serverconfig.php file to your liking, add your API keys, and build/add your coins to the control panel, and potentially create new stratum configurations.
