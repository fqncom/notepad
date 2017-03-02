
# [gitlab 安装](https://about.gitlab.com/downloads/#centos7)
    * 以上为官网，部分包需要翻墙，使用替代方案：
      * [CentOS 7 安装 GitLab CE 社区版并修改默认 Nginx](https://laravel-china.org/topics/2829)
      * [Gitlab Community Edition 镜像使用帮助](https://mirror.tuna.tsinghua.edu.cn/help/gitlab-ce/)
    ```
    yum install curl policycoreutils openssh-server openssh-clients
    systemctl enable sshd
    systemctl start sshd
    yum install postfix
    systemctl enable postfix
    systemctl start postfix
        * postfix: fatal: parameter inet_interfaces: no local interface found for ::1
          * vi  /etc/postfix/main.cf
            inet_interfaces = localhost ==> all
            inet_protocols = all

    firewall-cmd --permanent --add-service=http
        * FirewallD is not running
          * [How to Start and Enable Firewalld on CentOS 7](https://www.liquidweb.com/kb/how-to-start-and-enable-firewalld-on-centos-7/)
            * systemctl enable firewalld
            * systemctl start firewalld


    systemctl reload firewalld

    curl -LJO https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/yum/el7/gitlab-ce-8.9.9-ce.0.el7.x86_64.rpm
    rpm -i gitlab-ce-8.9.9-ce.0.el7.x86_64.rpm
    ```
    * config
    ```
    gitlab-ctl reconfigure
    gitlab-ctl status
    gitlab-ctl stop
    gitlab-ctl restart
    ps aux | grep runsvdir
    ```
    * 禁用自带Nignx服务器
    ```
    vi /etc/gitlab/gitlab.rb
    ...
    #设置nginx为false
    nginx['enable'] = false
    ...
    ```
    * 重启 nginx, 重启gitlab
    ```
    gitlab-ctl reconfigure
    service nginx restart
    ```
    * 默认账户密码
    ```
    Username: root
    Password: 5iveL!fe
    ```
