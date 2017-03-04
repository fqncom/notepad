
  # [hexo](https://hexo.io/)
  centOS7参考（https://www.vultr.com/docs/install-hexo-on-centos-7）

  ## init
  * wget http://nodejs.org/dist/node-latest.tar.gz
  * tar -zxf node-latest.tar.gz
  * cd node-v5.7.1/
  * ./configure
  * make && make install
  * yum install npm


  ## install
  * npm install hexo-cli -g
  * hexo init blog
  * cd blog
  * npm install
  * hexo server



  #
  ```
  yum install -y nodejs

  useradd -d /home/hexo -m -r -U -s /bin/bash
  ```
