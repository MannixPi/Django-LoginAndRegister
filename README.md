## [刘江的博客教程 - django实战项目一 : 可重用的登录注册系统](http://www.liujiangblog.com)

## 简单的使用方法：

1. 创建虚拟环境
2. 使用pip安装第三方依赖: `pip install -r requirements.txt`
3. 修改`settings.example.py`文件为`settings.py`并配置
4. 运行`migrate`命令，创建数据库和数据表
5. 运行`python manage.py runserver`启动服务器

路由设置：

```python
from django.contrib import admin
from django.urls import path, include
from login import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('index/', views.index),
    path('login/', views.login),
    path('register/', views.register),
    path('logout/', views.logout),
    path('confirm/', views.user_confirm),
    path('captcha/', include('captcha.urls'))   # 增加这一行
]
```
