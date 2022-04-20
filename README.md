# who-to-install-latest-version-compoer-on-ubuntu-
Introduction:  In this quickstart guide, we’ll install Composer on an Ubuntu 20.04 server.

# TO INSTALL THE LATEST VERSION OF COMPOSER RUN THESE COMMMAND:

Step 1 — Install Dependencies
 ```
 sudo apt update
sudo apt install php-cli unzip
```
Step 2 — Download and Install Composer
Make sure you’re in your home directory, then retrieve the Composer installer using curl:
```
cd ~
curl -sS https://getcomposer.org/installer -o /tmp/composer-setup.php
```
Next, we’ll verify that the downloaded installer matches the SHA-384 hash for the latest installer found on the Composer Public Keys / Signatures page.

Using curl, fetch the latest signature and store it in a shell variable:
```
HASH=`curl -sS https://composer.github.io/installer.sig`
```
Now execute the following PHP code to verify that the installation script is safe to run:
```
php -r "if (hash_file('SHA384', '/tmp/composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
```
>Installer verified
>**Note:** If the output says Installer corrupt, you’ll need to repeat the download and verification process until you have a verified installer.

The following command will download and install Composer as a system-wide command named composer, under /usr/local/bin:
```
sudo php /tmp/composer-setup.php --install-dir=/usr/local/bin --filename=composer
```
To test your installation, run:
```
composer
```
# Output
 ```
   ______
  / ____/___  ____ ___  ____  ____  ________  _____
 / /   / __ \/ __ `__ \/ __ \/ __ \/ ___/ _ \/ ___/
/ /___/ /_/ / / / / / / /_/ / /_/ (__  )  __/ /
\____/\____/_/ /_/ /_/ .___/\____/____/\___/_/
                    /_/
Composer version 2.3.4 
```
>This verifies that Composer was successfully installed on your system and is available system-wide.
_________________________________________________________________________________________________

# Uninstall composer
>To remove just composer package itself from Ubuntu 16.04 (Xenial Xerus) execute on terminal:
```
sudo apt-get remove composer
```
**Uninstall composer and it's dependent packages**
To remove the composer package and any other dependant package which are no longer needed from Ubuntu.
```
sudo apt-get remove --auto-remove composer
```
**Purging composer**
If you also want to delete configuration and/or data files of composer from Ubuntu Xenial then this will work:
```
sudo apt-get purge composer
```
To delete configuration and/or data files of composer and it's dependencies from Ubuntu Xenial then execute:
```
sudo apt-get purge --auto-remove composer
```
https://www.howtoinstall.co/en/ubuntu/xenial/composer?action=remove
________________________________________________________________________________________________________________________________________________

# uninstall php version 7.4/8.1 ubuntu 20.04 
>Code Example
```
sudo apt-get purge php7.*
```
sudo apt-get autoclean
```
sudo apt-get autoremove
```


[LINK] https://www.digitalocean.com/community/tutorials/how-to-install-composer-on-ubuntu-20-04-quickstart

[LINK] https://stackoverflow.com/questions/39337127/i-cannot-install-php-composer-in-ubuntu-16-04

