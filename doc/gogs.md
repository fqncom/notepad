
# [安装gogs](https://blog.mynook.info/post/host-your-own-git-server-using-gogs)
    * sudo adduser git
    * su git
    * curl -LJO http://7d9nal.com2.z0.glb.qiniucdn.com/0.10.1/linux_amd64.tar.gz
    * tar -zxvf linux_amd64.tar.gz
    * cd
    *
    * yum install mariadb-server mariadb (http://www.cnblogs.com/starof/)

# [网友安装](https://imjad.cn/archives/lab/using-gogs-to-build-your-own-git-server-on-centos) #
    * https://blog.mynook.info/post/host-your-own-git-server-using-gogs


# [官方版本for centOS7](https://packager.io/gh/pkgr/gogs/install?bid=613#centos-7-gogs)
    ```
    sudo rpm --import https://rpm.packager.io/key
    echo "[gogs]
    name=Repository for pkgr/gogs application.
    baseurl=https://rpm.packager.io/gh/pkgr/gogs/centos7/pkgr
    enabled=1" | sudo tee /etc/yum.repos.d/gogs.repo
    sudo yum install gogs
    ```

    ```
    APP_NAME="gogs"
    MYSQL_PASSWORD="change_me"
    HOSTNAME="example.com"

    # setup mysql
    yum install mysql-server -y
    service mysql-server start
    chkconfig mysql-server

    mysqladmin -u root password "${MYSQL_PASSWORD}"
    mysqladmin -u root --password="${MYSQL_PASSWORD}" password "${MYSQL_PASSWORD}"
    mysql -u root -p${MYSQL_PASSWORD} -e "CREATE DATABASE IF NOT EXISTS ${APP_NAME}; use ${APP_NAME}; set global storage_engine=INNODB;"

    # install nginx
    rpm -Uhv http://nginx.org/packages/centos/6/noarch/RPMS/nginx-release-centos-6-0.el6.ngx.noarch.rpm
     yum install -y nginx

    cat > /etc/nginx/conf.d/default.conf <<EOF
    server {
      listen          80;
      server_name     ${HOSTNAME};
      location / {
        proxy_pass      http://localhost:3000;
      }
    }
    EOF

    service nginx start
    chkconfig nginx on
    ```


git remote add origin http://zajitangzhai.me:3000/MonkeyJoker/notepad.git



https://github.com/gogits/gogs/releases/download/v0.10.1/linux_amd64.tar.gz


mysql -u root -p < scripts/mysql.sql
create user 'gogs'@'localhost' identified by 'pwd_fqn';
grant all privileges on gogs.* to 'gogs'@'localhost';
flush privileges;
quit;



# APP_NAME="gogs"
# MYSQL_PASSWORD="pwd_fqn"
HOSTNAME="zajitangzhai.me"

# # setup mysql
# yum install mysql-server -y
# service mysql-server start
# chkconfig mysql-server

# mysqladmin -u root password "${MYSQL_PASSWORD}"
# mysqladmin -u root --password="${MYSQL_PASSWORD}" password "${MYSQL_PASSWORD}"
# mysql -u root -p${MYSQL_PASSWORD} -e "CREATE DATABASE IF NOT EXISTS ${APP_NAME}; use ${APP_NAME}; set global storage_engine=INNODB;"

# install nginx
rpm -Uhv http://nginx.org/packages/centos/6/noarch/RPMS/nginx-release-centos-6-0.el6.ngx.noarch.rpm
 yum install -y nginx

cat > /etc/nginx/conf.d/default.conf <<EOF
server {
  listen          80;
  server_name     zajitangzhai.me;
  location / {
    proxy_pass      http://localhost:3000;
  }
}
EOF

service nginx start
chkconfig nginx on
