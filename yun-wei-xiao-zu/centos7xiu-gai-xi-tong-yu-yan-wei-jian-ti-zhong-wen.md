#1.查看系当前语言包
##locale
#2.查看系统拥有语言包
##locale -a
（zh_CN.UTF-8是简体中文，如果没有zh_CN.UTF-8,就安装语言包，如果存在可以直接设置)

#2.安装简体中文语言包
####yum install kde-l10n-Chinese
#3.设置为中文
##(1)临时修改，重启服务器之后就会还原之前的设置
###LANG="zh_CN.UTF-8"    #修改为中文
###LANG="en_US.UTF-8"    #修改为英文
##(2)永久修改就要把配置写入文件里面
###方法（一）
####vi /etc/locale.conf
将下面内容写到第一行，设置中文
####LANG=zh_CN.UTF8
###方法（二）
####localectl  set-locale LANG=zh_CN.UTF8