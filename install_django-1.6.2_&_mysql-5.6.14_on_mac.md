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

#### 8. Install Nginx
	➜  ~  brew install nginx
	==> Downloading http://nginx.org/download/nginx-1.4.4.tar.gz
	######################################################################## 100.0%
	==> ./configure --prefix=/usr/local/Cellar/nginx/1.4.4 --with-http_ssl_module --with-
	==> make
	==> make install
	==> Caveats
	Docroot is: /usr/local/var/www

	The default port has been set in /usr/local/etc/nginx/nginx.conf to 8080 so that
	nginx can run without sudo.

	To have launchd start nginx at login:
	    ln -sfv /usr/local/opt/nginx/*.plist ~/Library/LaunchAgents
	Then to load nginx now:
	    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.nginx.plist
	Or, if you don't want/need launchctl, you can just run:
	    nginx
	==> Summary
	🍺  /usr/local/Cellar/nginx/1.4.4: 7 files, 876K, built in 100 seconds
	➜  ~  nginx -V
	nginx version: nginx/1.4.4
	TLS SNI support enabled
	configure arguments: --prefix=/usr/local/Cellar/nginx/1.4.4 --with-http_ssl_module --with-pcre --with-ipv6 --sbin-path=/usr/local/Cellar/nginx/1.4.4/bin/nginx --with-cc-opt=-I/usr/local/include --with-ld-opt=-L/usr/local/lib --conf-path=/usr/local/etc/nginx/nginx.conf --pid-path=/usr/local/var/run/nginx.pid --lock-path=/usr/local/var/run/nginx.lock --http-client-body-temp-path=/usr/local/var/run/nginx/client_body_temp --http-proxy-temp-path=/usr/local/var/run/nginx/proxy_temp --http-fastcgi-temp-path=/usr/local/var/run/nginx/fastcgi_temp --http-uwsgi-temp-path=/usr/local/var/run/nginx/uwsgi_temp --http-scgi-temp-path=/usr/local/var/run/nginx/scgi_temp --http-log-path=/usr/local/var/log/nginx/access.log --error-log-path=/usr/local/var/log/nginx/error.log --with-http_gzip_static_module
	➜  ~  sudo nginx
	Password:
	➜  ~  nginx -s stop
	nginx: [alert] could not open error log file: open() "/usr/local/var/log/nginx/error.log" failed (13: Permission denied)
	2014/03/09 22:34:03 [notice] 35279#0: signal process started
	2014/03/09 22:34:03 [alert] 35279#0: kill(35266, 15) failed (1: Operation not permitted)
	➜  ~  sudo nginx -s stop	

#### 9. Install uWSGI
	➜  ~  sudo pip install uwsgi
	Password:
	Downloading/unpacking uwsgi
	  Downloading uwsgi-2.0.2.tar.gz (754kB): 754kB downloaded
	  Running setup.py (path:/private/tmp/pip_build_root/uwsgi/setup.py) egg_info for package uwsgi
	    
	Installing collected packages: uwsgi
	  Running setup.py install for uwsgi
	......
		################# uWSGI configuration #################
	    
	    pcre = True
	    kernel = Darwin
	    malloc = libc
	    execinfo = False
	    ifaddrs = True
	    ssl = True
	    zlib = True
	    locking = osx_spinlock
	    plugin_dir = .
	    timer = kqueue
	    yaml = embedded
	    json = False
	    filemonitor = kqueue
	    routing = True
	    debug = False
	    capabilities = False
	    xml = libxml2
	    event = kqueue
	    
	    ############## end of uWSGI configuration #############
	    total build time: 26 seconds
	    *** uWSGI is ready, launch it with /usr/local/bin/uwsgi ***
	    
	Successfully installed uwsgi
	Cleaning up...

#### 10. Test uWSGI
	➜  repo  cat test.py
	def application(env, start_response):
		start_response('200 OK', [('Content-Type', 'text/html')])
		return 'Hello World'
	➜  repo  uwsgi --http :8001 --wsgi-file test.py
	*** Starting uWSGI 2.0.2 (64bit) on [Sun Mar  9 23:19:24 2014] ***
	compiled with version: 4.2.1 Compatible Apple LLVM 5.0 (clang-500.2.79) on 09 March 2014 23:07:05
	os: Darwin-13.0.0 Darwin Kernel Version 13.0.0: Thu Sep 19 22:22:27 PDT 2013; root:xnu-2422.1.72~6/RELEASE_X86_64
	nodename: pengleongtekiiMac.local
	machine: x86_64
	clock source: unix
	pcre jit disabled
	detected number of CPU cores: 4
	current working directory: /Users/pengleong/repo
	detected binary path: /usr/local/bin/uwsgi
	*** WARNING: you are running uWSGI without its master process manager ***
	your processes number limit is 709
	your memory page size is 4096 bytes
	detected max file descriptor number: 256
	lock engine: OSX spinlocks
	thunder lock: disabled (you can enable it with --thunder-lock)
	uWSGI http bound on :8001 fd 4
	spawned uWSGI http 1 (pid: 36040)
	uwsgi socket 0 bound to TCP address 127.0.0.1:50568 (port auto-assigned) fd 3
	Python version: 2.7.5 (default, Aug 25 2013, 00:04:04)  [GCC 4.2.1 Compatible Apple LLVM 5.0 (clang-500.0.68)]
	*** Python threads support is disabled. You can enable it with --enable-threads ***
	Python main interpreter initialized at 0x7fabe0c0b300
	your server socket listen backlog is limited to 100 connections
	your mercy for graceful operations on workers is 60 seconds
	mapped 72752 bytes (71 KB) for 1 cores
	*** Operational MODE: single process ***
	WSGI app 0 (mountpoint='') ready in 0 seconds on interpreter 0x7fabe0c0b300 pid: 36039 (default app)
	*** uWSGI is running in multiple interpreter mode ***
	spawned uWSGI worker 1 (and the only) (pid: 36039, cores: 1)
	[pid: 36039|app: 0|req: 1/1] 127.0.0.1 () {34 vars in 602 bytes} [Sun Mar  9 23:19:45 2014] GET / => generated 11 bytes in 0 msecs (HTTP/1.1 200) 1 headers in 44 bytes (1 switches on core 0)
	[pid: 36039|app: 0|req: 2/2] 127.0.0.1 () {34 vars in 553 bytes} [Sun Mar  9 23:19:45 2014] GET /favicon.ico => generated 11 bytes in 0 msecs (HTTP/1.1 200) 1 headers in 44 bytes (1 switches on core 0)
	[pid: 36039|app: 0|req: 3/3] 127.0.0.1 () {34 vars in 553 bytes} [Sun Mar  9 23:19:45 2014] GET /favicon.ico => generated 11 bytes in 0 msecs (HTTP/1.1 200) 1 headers in 44 bytes (0 switches on core 0)


