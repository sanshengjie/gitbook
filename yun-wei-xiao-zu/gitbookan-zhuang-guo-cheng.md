# gitbook安装过程

## 1、安装node

### 下载node安装包并解压

wget [https://nodejs.org/dist/v10.16.3/node-v10.16.3-linux-x64.tar.xz](https://nodejs.org/dist/v10.16.3/node-v10.16.3-linux-x64.tar.xz) xz -d node-v10.16.3-linux-x64.tar.xz tar -xvf node-v10.16.3-linux-x64.tar

### 创建软链

ln -s /software/node-v10.16.3-linux-x64/bin/node /usr/local/bin/node ln -s /software/node-v10.16.3-linux-x64/bin/npm /usr/local/bin/npm

### 检查安装后的版本

\[root@localhost software\]\# node -v v10.16.3 \[root@localhost software\]\# npm -v 6.9.0 \[root@localhost software\]\#

### 配置npm国内的镜像并检查是否生效

\[root@localhost software\]\# npm config set registry [https://registry.npm.taobao.org](https://registry.npm.taobao.org) -g \[root@localhost software\]\# npm config get registry [https://registry.npm.taobao.org/](https://registry.npm.taobao.org/) \[root@localhost software\]\#

## 2、安装gitbook

### 使用npm安装gitbook

npm install gitbook-cli -g

### 创建软链

ln -s /software/node-v10.16.3-linux-x64/bin/gitbook /usr/local/bin/gitbook

### 检查gitbook版本（期间将会执行install）

\[root@localhost software\]\# gitbook -V CLI version: 2.3.2 Installing GitBook 3.2.3 可能耗时比较久，可打开另外一个命令窗口，使用命令ps -ef\|grep node\|grep gitbook\|awk '{print $2}'\|xargs strace -ttp观察安装情况，如果实在太慢可中断后再次开始，安装完成后如下

\[root@localhost software\]\# gitbook -V CLI version: 2.3.2 GitBook version: 3.2.3 \[root@localhost software\]\#

## 3、使用gitbook

### 初始化gitbook

mkdir -p /project/gitbook cd /project/gitbook gitbook init

### 初始化完成后，可以看到目录下有文件SUMMARY.md，这个文件即用来配置目录；

\[root@localhost gitbook\]\# more SUMMARY.md

### 配置基本参数（新建book.json文件）可选

\[root@localhost gitbook\]\# more book.json

### 安装对应的插件（配合book.json）

gitbook install

### 启动服务

gitbook serve 服务启动后即可通过[http://192.168.80.130:4000访问](http://192.168.80.130:4000访问)

