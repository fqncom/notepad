
# 腾讯云
  * [帮助文档](https://www.qcloud.com/document/product/213/2936)
  * [新用户见面礼](https://www.qcloud.com/act/newuser)
  * [建立网站，从域名注册开始](https://dnspod.qcloud.com/?from=finishReg)

# [腾讯云入门教程](http://bbs.qcloud.com/forum.php?mod=viewthread&utm_campaign=ZhanNeiXin&tid=2387&extra=page=1)
  * [centOS 配置基础环境](http://bbs.qcloud.com/thread-1316-1-1.html)
    * 安装基础库
      - yum install -y git zsh curl openssh-server cronie autojump svn nginx
    * 安装git
      yum install git -y
    * 安装oh-my-zsh
      yum install curl openssh-server cronie
      sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
    * yum install -y httpd php php-fpm mysql mysql-server php-mysql
    * [centOS7下mysql失败](http://www.cnblogs.com/starof/p/4680083.html)
      * yum install mariadb-server mariadb

  * [部署应用环境](https://www.qcloud.com/document/product/213/2975)
    * 安装及启动nginx
      - chkconfig nginx on

    > 输入yum install nginx命令进行nginx的安装，当需要确认时输入”y“确认。
      输入service nginx start启动nginx服务。
      输入wget http://127.0.0.1测试nginx服务。

    * 安装PHP及相应组件

    > 输入yum install php php-fpm命令进行PHP的安装，当需要确认时输入”y“确认。
      输入service php-fpm start启动php-fpm服务，并使用命令cat /etc/php-fpm.d/www.conf |grep -i 'listen ='查看php-fpm配置。
      使用命令nginx -t查找nginx配置文件，并使用vi命令修改该配置文件：
      vi /etc/nginx/nginx.conf

      ```
        server {
          listen       80;
          root   /usr/share/nginx/html;
          server_name  localhost;

          #charset koi8-r;
          #access_log  /var/log/nginx/log/host.access.log  main;

          location / {
              index  index.html index.htm;
          }

          #error_page  404              /404.html;

          # redirect server error pages to the static page /50x.html
          #
          error_page   500 502 503 504  /50x.html;
          location = /50x.html {
              root   /usr/share/nginx/html;
          }

          # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
          #
          location ~ \.php$ {
              fastcgi_pass   127.0.0.1:9000;
              fastcgi_index   index.php;
              fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
              include        fastcgi_params;
          }

        }

      ```

    > 修改后保存，输入service nginx restart重启nginx服务。
      在web目录下创建index.php：
      vi /usr/share/nginx/html/index.php
      写入如下内容：

      ```
      <?php
      echo "<title>Test Page</title>";
      echo "hello world";
      ?>
      ```

    > 在浏览器中，访问CentOS云服务器公网IP+php网页名称查看环境配置是否成功，如果页面可以显示“hello world”，说明配置成功。
    如果不成功，很有可能是安全组配置问题

    [实例](http://zajitangzhai.me/index.php)

    * python 基本应用
    ```
    yum install python-pip
    pip install web.py

    python main.py 80
    ```

    * [install mysql](https://devops.profitbricks.com/tutorials/install-mysql-on-centos-7/)
      - sudo rpm -Uvh http://dev.mysql.com/get/mysql-community-release-el7-5.noarch.rpm
      - sudo yum -y install mysql-community-server
      - sudo /usr/bin/systemctl enable mysqld
      - sudo /usr/bin/systemctl start mysqld
      - sudo /usr/bin/mysql_secure_installation
      - firewall-cmd --permanent --zone=trusted --add-source=192.0.2.10/32
      - firewall-cmd --permanent --zone=trusted --add-port=3306/tcp
      - firewall-cmd  --reload
      - mysql -u root -p mysql
      - create database appdb;
      - grant all on appdb.* to 'appuser'@'localhost' identified by 'password';
      - quit;
      - mysql -u appuser -p -h localhost appdb






















  * 安装golang
    > yum install go































=============
