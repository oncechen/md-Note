解压
tar zxvf XXX.tgz
./configure
make
make install


删除目录
rm -rf file/

wget https://www.python.org/ftp/python/3.4.6/Python-3.4.6.tgz

yum install zlib-devel bzip2-devel openssl-devel ncurses-devel splite-devel readline-devel tk-devel python-devel mysql-devel gcc make

tar zxvf XXX.tgz
./configure
make
make install

pip install mysqlclient
pip install django==1.8.3

备份python旧版本：
mv python python.bak

根目录/ ： cd /
aquota.group  aquota.user  bin  boot  dev  etc  home  lib  lib64  lost+found  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

创建新python命令:
ln /usr/local/bin/python3.4 python

python安装目录：
/usr/local/lib/python3.4/site-packages

yum install mysql-server
如果不能安装，可以先下载到本地再安装。
如果引用的python版本有语法错误可行去修改引用的python版本。
wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm 
rpm -ivh mysql-community-release-el7-5.noarch.rpm
ls -1 /etc/yum.repos.d/mysql-community* 
yum install mysql-server 

启动
service mysqld start
重启
service mysqld restart

查看磁盘使用
df -hl 

mysql help
?         (\?) Synonym for `help'.
clear     (\c) Clear the current input statement.
connect   (\r) Reconnect to the server. Optional arguments are db and host.
delimiter (\d) Set statement delimiter.
edit      (\e) Edit command with $EDITOR.
ego       (\G) Send command to mysql server, display result vertically.
exit      (\q) Exit mysql. Same as quit.
go        (\g) Send command to mysql server.
help      (\h) Display this help.
nopager   (\n) Disable pager, print to stdout.
notee     (\t) Don't write into outfile.
pager     (\P) Set PAGER [to_pager]. Print the query results via PAGER.
print     (\p) Print current command.
prompt    (\R) Change your mysql prompt.
quit      (\q) Quit mysql.
rehash    (\#) Rebuild completion hash.
source    (\.) Execute an SQL script file. Takes a file name as an argument.
status    (\s) Get status information from the server.
system    (\!) Execute a system shell command.
tee       (\T) Set outfile [to_outfile]. Append everything into given outfile.
use       (\u) Use another database. Takes database name as argument.
charset   (\C) Switch to another charset. Might be needed for processing binlog with multi-byte charsets.
warnings  (\W) Show warnings after every statement.
nowarning (\w) Don't show warnings after every statement.


SET PASSWORD FOR root@localhost=password('123456');
FLUSH PRIVILEGES;

mysql -u root -p
123456

mysql -u admin -p
12345678
```mysql
GRANT ALL PRIVILEGES ON *.* TO 'root'@112.65.46.10 IDENTIFIED BY '1234567';
GRANT ALL PRIVILEGES ON *.* TO 'root'@localhost IDENTIFIED BY '123456';
GRANT ALL PRIVILEGES ON *.* TO 'admin'@localhost IDENTIFIED BY '12345678';
```




