#### 分离开发与生产环境的设置

```python
import socket
	if socket.get_hostname() == "开发服务器的主机名"：
		#setting 开发环境
        DEBUG = TEMPLATE_DEBUG = True
	else:
		#setting 生产环境
        DEBUG = TEMPLATE_DEBUG = False
```

#### 将 Django 应用程序部署到运行 mod_python 的 Apache

*mod_wsgi* 是 Apach的一个.py模块,为了将 mod_wsgi 模块加载到 Apache，需要将以下几行代码添加到您的服务器的 httpd.conf 文件中：

```python
>>httpd.conf ... 格式：LoadModule [模块名称] [模块路径]
# find / -name mod_wsgi.so	 查看mod_wsgi.so路径/usr/lib64/httpd/modules/mod_wsgi.so
LoadModule wsgi_module modules/mod_wsgi.so
```

设置一个 `Location` 指令，告诉 Apache 将Django 应用程序关联到哪个 URL。 Apache 可以通过 /testproject URL 访问到 Django testproject 项目。通过 http://www.xxx.com/testproject/ 就可以访问应用程序。

```python
>>httpd.conf ...
<Location "/testproject">
    SetHandler python-program
    PythonHandler django.core.handlers.modpython
    SetEnv DJANGO_SETTINGS_MODULE testproject.settings
    PythonDebug Off
</Location>
```

#### 让Apache 不对媒体文件使用 mod_python

```python
>>httpd.conf ...
<LocationMatch "\.(png|gif|jpg|mov|mp3|avi|wav)$">
    SetHandler None
</LocationMatch>
```



