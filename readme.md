GOOSH INSTALLER
===============

*Remember that this is an unoffical installer of goosh. Use at your own risk! But if you find any bugs, please let me know!*

Script to install and configure Goosh, the Google terminal like web
application. Clones the current version of Goosh into ~/goosh, where
it also configures and builds the files needed for running Goosh on
your web server.

Please keep in mind that this script is meant to be run under Debian
based distributions, such as Debian itself, Ubuntu or similar.

注意重点这个shell只是用于 Debian 或者 Ubuntu 系统

DEPENDENCIES
------------

Apache or lighthttpd with a working installation of PHP. Also requires yui-compressor, that should be installed by the installer script if not found.

BUGS
----

No known bugs. But if you find one, please report them. Patches welcome! :)

INSTALLATION(安装说明)
------------
首先需要安装PHP 

    apt-get install php5-common libapache2-mod-php5 php5-cli
    
然后下载shell

    wget https://raw.github.com/tolecnal/goosh-installer/master/goosh.sh
    chmod u+x goosh.sh
    
安装之前需要设定下你的编辑器目录 默认的Vim目录是 /usr/bin/vim 

然后编辑这个shell文件  

    vim googsh.sh
    
添加

    EDITOR="/usr/bin/vim"
    
然后执行shell文件就好了。末尾的时候需要你配置一下文件 

    ./goosh.sh
    
只需要改下面的配置就可以了

    goosh.config.user = "guest";  #这个改成你喜欢的
    goosh.config.host = "goosh.org"; #这个改成你的域名或者其他
    goosh.config.mode = "web"; #这个随意改下或者默认也ok
    
配置完成后保存即可
    
最后需你将生成index.php文件拷贝到 apache目录下

    mkdir /var/www/goosh
    cp /root/goosh/index.php /var/www/goosh
    
最后重启下apache

    service httpd restart
    
这样就完成了~

Then follow the on screen instructions

CREDITS
-------

* Thanks to Stefan Grothkopp <grothkopp@gmail.com> for making goosh in the first place.
* Thanks to Steinar H. Gunderson (Sesse) for invaluable BASH help.

ABOUT THE AUTHOR
----------------

Author: Jostein Elvaker Haande <tolecnal@tolecnal.net>
Webpage: http://tolecnal.net
翻译博客 www.teidihen.com
