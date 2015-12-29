git 使用多个本地ssh key
========
本地配置了两个ssh-key，一个用来连接公司server，一个用来连接github

这里省略生成key的过程。

新增ssh的配置文件，并修改权限

	touch ~/.ssh/config
	chmod 600 ~/.ssh/config

修改config文件的内容

	Host *.workdomain.com  
    	IdentityFile ~/.ssh/elemeid_rsa  
    	User git  
   
	Host github.com  
    	IdentityFile ~/.ssh/githubid_rsa  
    	User git 