### CentOS 6.5 安装 git & gitosis
##### 1、安装 git
***当前用户 `root`***

在安装前将 yum 升级

	yum update
安装 git

	yum install git

##### 2、安装 python-setuptools
安装 python-setuptools

	yum install python python-setuptools

##### 3、安装 gitosis
将 gitosis 克隆到本地

	cd /tmp
	git clone git://github.com/res0nat0r/gitosis.git
安装 gitosis

	cd gitosis
	python setup.py install
	
##### 4、生成 ssh-keygen 并且初始化 gitosis
在管理机器上面生成 ssh-keygen 并且上传到服务器，在这里笔者是在服务器上生成 ssh-keygen

	ssh-keygen -t rsa -C "user@sample.com"
一路回车

查看 ssh-keygen

	cat ~/.ssh/id_rsa.pub
在服务器添加用户 git

	adduser -m git
切换用户

	su git
***当前用户 `git`***

使用 `git` 用户初始化 gitosis，将之前生成的 ssh-keygen 添加到 gitosis

	gitosis-init < /root/.ssh/id_rsa.pub
	
##### 5、使用 gitosis 管理
切换用户

	su root
***当前用户 `root`***

克隆 gitosis-admin 到当前用户目录下

	cd ~
	mkdir repo && cd repo
	git clone git@127.0.0.2:gitosis-admin.git
查看已上传的 ssh-keygen
	
	cd gitosis-admin/keydir
	ls -al
添加 ssh-keygen，例如：上传用户生成的 ssh-keygen 到 /tmp 目录中名为 user@sample.pub

	mv /tmp/user@sample.pub ~/repo/gitosis-admin/keydir/user@sample.com.pub

gitosis.conf 配置

	vi ~/repo/gitosis-admin/gitosis.conf
在 gitosis.conf 文件末尾增加，将该 ssh-keygen 增加及使用项目 test

	[group test]
	writable = test
	members = user@sample.com
提交修改

	git add .
	git commit -a -m "add user@sample.com"
	git push
