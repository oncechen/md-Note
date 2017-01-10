## 01-Django webapp

####  win下cmd进入的项目路径：

```shell
cd /d D:/git
```
####  创建项目名称chen：
```shel
django-admin startproject chen
```
#### 进入项目chen：

```shell
cd /d D:/git/chen	
```

####  开启项目服务：

```python
python3 manage.py runserver
```
###  可设置项目web开发指定端口，如8989：
```python
python3 manage.py runserver 8989
```

#### app创建once

```powershell
python3 manage.py startapp once
```
### django连接mysql
*使用库前先建立NAME库，并安装好pymysql库
*在项目顶层站点下`__init__.py`添加：
```python
#	__init__.py写入（与setting同目录）
import pymysql
pymysql.install_as_MySQLdb()
```
```python
#	setting配置
==========================================================
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'blog',
        'USER':'root',
        'PASSWORD':'123456',
        'HOST':'127.0.0.1',
        'PORT':'3307',
    }
}
==========================================================
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'polls',
        'USER':'root',
        'PASSWORD':'123456',
        'HOST':'127.0.0.1',
        'PORT':'3309',
    }
}
==========================================================
```
#### 为INSTALLED_APPS里的应用生成相应的数据表，自动管理数据表模型：

```python

#  migrate 命令只会为在 INSTALLED_APPS 里声明了的应用进行数据库迁移
python3 manage.py migrate
```
#### 生成数据迁移文件：
```python
python3 manage.py makemigrations appname
python3 manage.py migrate
```
#### 数据表生成前可对项目进行检查
```python
python manage.py check 
```
#### 改变模型需要这三步：
- 编辑 models.py 文件，改变模型。
- 运行 python manage.py makemigrations 为模型的改变生成迁移文件。
- 运行 python manage.py migrate 来应用数据库迁移。
#### 其它App写入数据表方法：

```python
#创建app:
	python3 manage.py startapp app
#设计models.py
	class table1
	class table2
	......
#添加app到setting:
  INSTALLED_APPS = [
      ......
      'app',
  ]
#生成相应的数据表，自动管理数据表模型：
	python3 manage.py migrate
#生成数据迁移文件：
	python3 manage.py makemigrations
```
