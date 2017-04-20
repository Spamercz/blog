---
layout: default
comments: true
title: PHPStorm, WSL, remote PHP and debugging
---
<style>
	{% include styles.css %}
</style>

# PHPStorm, WSL, remote PHP and debugging

How to enable debugging PHP on Windows which is running in WSL. In few steps.

1. If not installed, install ssh, php-xdebug on WSL
````
sudo apt-get install openssh-server
````
````
sudo apt-get install php-xdebug
````

2. Change default port from 22 to 9022 (port 22 is usually already occupied), optionally you can 
 enable password login (more bellow).
````
sudo nano /etc/ssh/sshd_config
````
````
sudo service ssh restart
````

3. In PHPStorm configure remote PHP interpreter

Here is remote config button

<img src="/files/images/debug2.PNG">

Here is remote config itself

<img src="/files/images/debug1.PNG">

4. Set up Path mappings. Your project files to WSL files. Keep in mind you have to specify absolute path, 
symlinks are not supported.
<img src="/files/images/debug3.PNG">

5. Configure Xdebug 
````
sudo nano /etc/php/7.1/apache2/php.ini
````
Add these lines to end.
````
[xdebug]
zend_extension="/usr/lib/php/20160303/xdebug.so"

xdebug.remote_enable=1
xdebug.remote_connect_back=On
xdebug.remote_host=127.0.0.1
xdebug.remote_port=9001
xdebug.idekey=PHPSTORM
````
Restart apache
````
sudo service apache2 restart
````

6. Configure debugger in PHPStorm
<img src="/files/images/debug5.PNG">

7. Use it :)
<img src="/files/images/debug4.PNG">

{% include footer.html %}

{% include disqus.md %}