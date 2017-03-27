### 配置httpd.conf
0.复制mod_wsgi.so到modules下
1.加载mod_wsgi.so模块
```
LoadModule wsgi_module modules/mod_wsgi.so
```
2.加载wsgi.py文件路径
```
WSGIScriptAlias / /usr/.../msite/msite/wsgi.py
```
3.指定msite项目路径
```
WSGIPythonPath /usr/.../msite
```