biowin.cc-2015
=============

博文机器人自动化科技有限公司官网2015年版


域名绑定、301转向及nginx配置
-----

新建配置文件: ``sudo nano /etc/nginx/sites-available/biowin.cc``

编辑配置文件及保存: 

    server {
        server_name biowin.cc;
        return 301 http://www.biowin.cc$request_uri;
    }
    server {
        server_name www.biowin.cc;
        index index.html;
        root /srv/biowin.cc-2015/_site;
        error_page 404 /Error.html;
    }

建立链接: ``sudo ln -s /etc/nginx/sites-available/biowin.cc /etc/nginx/sites-enabled/``

重启nginx: ``sudo service nginx restart``


下载及生成网站
-----

1. 下载网站源码: ``git clone git://github.com/zackwong/biowin.cc-2015.git``

2. 进入源码根目录: ``cd biowin.cc-2015``

3. 生成网站: ``jekyll build``


开发者
---------

* Zack Wong &lt;hzzzoo@126.com&gt;
