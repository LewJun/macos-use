
## fully uninstall
* brew uninstall mysql@5.7
* sudo find / -name mysql
  sudo rm -rf /usr/local/bin/mysql /usr/local/var/mysql /usr/local/var/mysql/mysql /usr/local/etc/init.d/mysql /usr/local/etc/init.d/mysql.default /usr/local/etc/logrotate.d/mysql /usr/local/etc/logrotate.d/mysql.default /usr/local/var/mysql /usr/local/var/mysql/mysql /Users/huiye/Library/Logs/Homebrew/mysql /Users/huiye/.dbeaver-drivers/maven/maven-central/mysql /usr/local/etc/my.cnf
* vim ~/.bash_profile 删除 /usr/local/opt/mysql@5.7/bin
## brew install
brew install mysql@5.7

``` info
==> Downloading https://homebrew.bintray.com/bottles/mysql@5.7-5.7.25.mojave.bottle.tar.gz
Already downloaded: /Users/huiye/Library/Caches/Homebrew/downloads/9bea6ff9f2b392ad4d37e94a64969cc32fa3d373f0798c6400eb42e167bd2d4c--mysql@5.7-5.7.25.mojave.bottle.tar.gz
==> Pouring mysql@5.7-5.7.25.mojave.bottle.tar.gz
==> Caveats
We've installed your MySQL database without a root password. To secure it run:
    mysql_secure_installation

MySQL is configured to only allow connections from localhost by default

To connect run:
    mysql -uroot

mysql@5.7 is keg-only, which means it was not symlinked into /usr/local,
because this is an alternate version of another formula.

If you need to have mysql@5.7 first in your PATH run:
  echo 'export PATH="/usr/local/opt/mysql@5.7/bin:$PATH"' >> ~/.bash_profile

For compilers to find mysql@5.7 you may need to set:
  export LDFLAGS="-L/usr/local/opt/mysql@5.7/lib"
  export CPPFLAGS="-I/usr/local/opt/mysql@5.7/include"


To have launchd start mysql@5.7 now and restart at login:
  brew services start mysql@5.7
Or, if you don't want/need a background service you can just run:
  /usr/local/opt/mysql@5.7/bin/mysql.server start
==> Summary
🍺  /usr/local/Cellar/mysql@5.7/5.7.25: 319 files, 234MB

```

## set mysql path
> echo 'export PATH="/usr/local/opt/mysql@5.7/bin:$PATH"' >> ~/.bash_profile

## start
> mysql.server start
Starting MySQL
 SUCCESS! 

.. ERROR! The server quit without updating PID file (/usr/local/var/mysql/HuiYesMBP.local.pid).
如果启动出现如上错误，可以使用ps -ef|grep mysql 来杀掉相应的进程

## init
> mysql_secure_installation
Securing the MySQL server deployment.

Connecting to MySQL using a blank password.

VALIDATE PASSWORD PLUGIN can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD plugin?

Press y|Y for Yes, any other key for No: y

There are three levels of password validation policy:

LOW    Length >= 8
MEDIUM Length >= 8, numeric, mixed case, and special characters
STRONG Length >= 8, numeric, mixed case, special characters and dictionary                  file

Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: 0
Please set the password for root here.

New password: root123456

Re-enter new password: root123456

Estimated strength of the password: 50 
Do you wish to continue with the password provided?(Press y|Y for Yes, any other key for No) : n

New password: root123456

Re-enter new password: root123456

Estimated strength of the password: 50 
Do you wish to continue with the password provided?(Press y|Y for Yes, any other key for No) : y
By default, a MySQL installation has an anonymous user,
allowing anyone to log into MySQL without having to have
a user account created for them. This is intended only for
testing, and to make the installation go a bit smoother.
You should remove them before moving into a production
environment.

Remove anonymous users? (Press y|Y for Yes, any other key for No) : y
Success.


Normally, root should only be allowed to connect from
'localhost'. This ensures that someone cannot guess at
the root password from the network.

Disallow root login remotely? (Press y|Y for Yes, any other key for No) : y
Success.

By default, MySQL comes with a database named 'test' that
anyone can access. This is also intended only for testing,
and should be removed before moving into a production
environment.


Remove test database and access to it? (Press y|Y for Yes, any other key for No) : n

 ... skipping.
Reloading the privilege tables will ensure that all changes
made so far will take effect immediately.

Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y
Success.

All done! 


## 登录
> mysql -u root -proot123456

