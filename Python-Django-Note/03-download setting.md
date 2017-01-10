#### 附件下载
```html
<a href = '/media/examples/python.exe' target='__blank'>DOWNLOAD</a>
```

```python
url(r'^media/(?P<path>.*)$/','django.views.static.serve',{'document_root':wenda.setting.MEDIA_ROOT}),

MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR,'media')
```

