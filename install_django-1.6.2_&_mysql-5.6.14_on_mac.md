### Install Django-1.6.2 & MySQL-5.6.14 on Mac
#### 1. Install MySQL
	# brew update
	➜  ~  brew install mysql
	==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/mysql-5.6.1
	######################################################################## 100.0%
	==> Pouring mysql-5.6.14.mavericks.bottle.tar.gz
	==> /usr/local/Cellar/mysql/5.6.14/bin/mysql_install_db --verbose --user=pengleo
	==> Caveats
	A "/etc/my.cnf" from another install may interfere with a Homebrew-built
	server starting up correctly.

	To connect:
    mysql -uroot

	To have launchd start mysql at login:
    ln -sfv /usr/local/opt/mysql/*.plist ~/Library/LaunchAgents
	Then to load mysql now:
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist
	Or, if you don't want/need launchctl, you can just run:
    mysql.server start
	==> Summary
	🍺  /usr/local/Cellar/mysql/5.6.14: 9383 files, 349M
	➜  ~  mysql.server start
	Starting MySQL
	. SUCCESS! 
	➜  ~  mysql -uroot -p
	Enter password: 
	Welcome to the MySQL monitor.  Commands end with ; or \g.
	Your MySQL connection id is 1
	Server version: 5.6.14 Source distribution

	Copyright (c) 2000, 2013, Oracle and/or its affiliates. All rights reserved.

	Oracle is a registered trademark of Oracle Corporation and/or its
	affiliates. Other names may be trademarks of their respective
	owners.

	Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

	mysql>
	
	➜  bin git:(master) ./mysql_secure_installation 



	NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MySQL
	      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

	In order to log into MySQL to secure it, we'll need the current
	password for the root user.  If you've just installed MySQL, and
	you haven't set the root password yet, the password will be blank,
	so you should just press enter here.

	Enter current password for root (enter for none): 
	OK, successfully used password, moving on...

	Setting the root password ensures that nobody can log into the MySQL
	root user without the proper authorisation.

	Set root password? [Y/n] y
	New password: 
	Re-enter new password: 
	Password updated successfully!
	Reloading privilege tables..
	 ... Success!


	By default, a MySQL installation has an anonymous user, allowing anyone
	to log into MySQL without having to have a user account created for
	them.  This is intended only for testing, and to make the installation
	go a bit smoother.  You should remove them before moving into a
	production environment.

	Remove anonymous users? [Y/n] y
	 ... Success!

	Normally, root should only be allowed to connect from 'localhost'.  This
	ensures that someone cannot guess at the root password from the network.

	Disallow root login remotely? [Y/n] y
	 ... Success!

	By default, MySQL comes with a database named 'test' that anyone can
	access.  This is also intended only for testing, and should be removed
	before moving into a production environment.

	Remove test database and access to it? [Y/n] n 
	 ... skipping.

	Reloading the privilege tables will ensure that all changes made so far
	will take effect immediately.

	Reload privilege tables now? [Y/n] y
	 ... Success!




	All done!  If you've completed all of the above steps, your MySQL
	installation should now be secure.

	Thanks for using MySQL!


	Cleaning up...
	➜  bin git:(master) cd
	➜  ~  mysql -uroot -p
	Enter password: 
	Welcome to the MySQL monitor.  Commands end with ; or \g.
	Your MySQL connection id is 12
	Server version: 5.6.14 Source distribution

	Copyright (c) 2000, 2013, Oracle and/or its affiliates. All rights reserved.

	Oracle is a registered trademark of Oracle Corporation and/or its
	affiliates. Other names may be trademarks of their respective
	owners.

	Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

	mysql>	
#### 2. Install pip
	➜  github  git clone https://github.com/pypa/pip.git
	Cloning into 'pip'...
	remote: Reusing existing pack: 12871, done.
	remote: Counting objects: 72, done.
	remote: Compressing objects: 100% (71/71), done.
	remote: Total 12943 (delta 31), reused 10 (delta 0)
	Receiving objects: 100% (12943/12943), 18.23 MiB | 36.00 KiB/s, done.
	Resolving deltas: 100% (7872/7872), done.
	Checking connectivity... done
	➜  github  l
	total 0
	drwxr-xr-x   4 pengleong  staff   136  3  9 00:35 .
	drwxr-xr-x+ 43 pengleong  staff  1462  3  9 00:49 ..
	drwxr-xr-x   4 pengleong  staff   136  3  5 21:21 docs
	drwxr-xr-x  20 pengleong  staff   680  3  9 00:49 pip
	➜  github  cd pip
	➜  pip git:(develop) l
	total 152
	drwxr-xr-x  20 pengleong  staff    680  3  9 00:49 .
	drwxr-xr-x   4 pengleong  staff    136  3  9 00:35 ..
	drwxr-xr-x  13 pengleong  staff    442  3  9 00:49 .git
	-rw-r--r--   1 pengleong  staff    119  3  9 00:49 .gitignore
	-rw-r--r--   1 pengleong  staff   2650  3  9 00:49 .mailmap
	drwxr-xr-x   3 pengleong  staff    102  3  9 00:49 .travis
	-rw-r--r--   1 pengleong  staff   1144  3  9 00:49 .travis.yml
	-rw-r--r--   1 pengleong  staff   4940  3  9 00:49 AUTHORS.txt
	-rw-r--r--   1 pengleong  staff  32012  3  9 00:49 CHANGES.txt
	-rw-r--r--   1 pengleong  staff   1090  3  9 00:49 LICENSE.txt
	-rw-r--r--   1 pengleong  staff    236  3  9 00:49 MANIFEST.in
	-rw-r--r--   1 pengleong  staff    794  3  9 00:49 README.rst
	drwxr-xr-x   3 pengleong  staff    102  3  9 00:49 contrib
	drwxr-xr-x  20 pengleong  staff    680  3  9 00:49 docs
	drwxr-xr-x  21 pengleong  staff    714  3  9 00:49 pip
	-rw-r--r--   1 pengleong  staff     88  3  9 00:49 setup.cfg
	-rw-r--r--   1 pengleong  staff   2810  3  9 00:49 setup.py
	drwxr-xr-x   5 pengleong  staff    170  3  9 00:49 tasks
	drwxr-xr-x   9 pengleong  staff    306  3  9 00:49 tests
	-rw-r--r--   1 pengleong  staff    566  3  9 00:49 tox.ini
	➜  pip git:(develop) sudo python setup.py install
	Password:
	running install
	running bdist_egg
	running egg_info
	creating pip.egg-info
	......
	
	creating dist
	creating 'dist/pip-1.6.dev1-py2.7.egg' and adding 'build/bdist.macosx-10.9-intel/egg' to it
	removing 'build/bdist.macosx-10.9-intel/egg' (and everything under it)
	Processing pip-1.6.dev1-py2.7.egg
	creating /Library/Python/2.7/site-packages/pip-1.6.dev1-py2.7.egg
	Extracting pip-1.6.dev1-py2.7.egg to /Library/Python/2.7/site-packages
	Adding pip 1.6.dev1 to easy-install.pth file
	Installing pip script to /usr/local/bin
	Installing pip2.7 script to /usr/local/bin
	Installing pip2 script to /usr/local/bin

	Installed /Library/Python/2.7/site-packages/pip-1.6.dev1-py2.7.egg
	Processing dependencies for pip==1.6.dev1
	Finished processing dependencies for pip==1.6.dev1
	➜  pip git:(develop) pip -V
	pip 1.6.dev1 from /Library/Python/2.7/site-packages/pip-1.6.dev1-py2.7.egg (python 2.7)
#### 3. Install setuptools
	➜  ~  sudo pip install setuptools --upgrade
	Requirement already up-to-date: setuptools in /Library/Python/2.7/site-packages/setuptools-3.1-py2.7.egg
	Cleaning up...
#### 4. Install Distribute
	➜  ~  sudo pip install Distribute
	Password:
	Downloading/unpacking Distribute
	  Downloading distribute-0.7.3.zip (145kB): 145kB downloaded
	  Running setup.py (path:/private/tmp/pip_build_root/Distribute/setup.py) egg_info for package Distribute
	    
	Requirement already satisfied (use --upgrade to upgrade): setuptools>=0.7 in /Library/Python/2.7/site-packages/setuptools-3.1-py2.7.egg (from Distribute)
	Installing collected packages: Distribute
	  Running setup.py install for Distribute
	    
	Successfully installed Distribute
	Cleaning up...
#### 5. Install Django
	➜  ~  sudo pip install Django==1.6.2
	Downloading/unpacking Django==1.6.2
	  Downloading Django-1.6.2-py2.py3-none-any.whl (6.7MB): 6.7MB downloaded
	Installing collected packages: Django
	Successfully installed Django
	Cleaning up...
	➜  ~  python           
	Python 2.7.5 (default, Aug 25 2013, 00:04:04) 
	[GCC 4.2.1 Compatible Apple LLVM 5.0 (clang-500.0.68)] on darwin
	Type "help", "copyright", "credits" or "license" for more information.
	>>> import django
	>>> django.VERSION
	(1, 6, 2, 'final', 0)
	>>> quit()
#### 6. Install MySQL-python
	➜  ~  sudo pip install mysql-python
	Password:
	Downloading/unpacking mysql-python
	  Downloading MySQL-python-1.2.5.zip (108kB): 108kB downloaded
	  Running setup.py (path:/private/tmp/pip_build_root/mysql-python/setup.py) egg_info for package mysql-python
	    
	Installing collected packages: mysql-python
	  Running setup.py install for mysql-python
	  ......
	  
	  Successfully installed mysql-python
	Cleaning up...
#### 7. Test
	➜  repo  django-admin.py startproject mysite
	➜  repo  cd mysite
	➜  mysite  python manage.py runserver
	Validating models...

	0 errors found
	March 09, 2014 - 03:52:54
	Django version 1.6.2, using settings 'mysite.settings'
	Starting development server at http://127.0.0.1:8000/
	Quit the server with CONTROL-C.
	[09/Mar/2014 03:53:14] "GET / HTTP/1.1" 200 1757

	