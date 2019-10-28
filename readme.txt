一：用IDEdjango_team下新建项目 Django201910以及APP APP01
二：templates下新做index.html登录页面
三：做引入首页
  1.urls.py加入

    from  django.conf.urls import url
from  django.contrib import admin
from  app01 import views

urlpatterns=[
    url(r'^admin/', admin.site.urls),
    url(r'^$', views.index),


]

2 views.py加入
def index(request):
    return render(request,'index.html')

5.初始化sqlite数据库

C:\django_team\Django201910>python manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, sessions
Running migrations:
  Applying contenttypes.0001_initial... OK
  Applying auth.0001_initial... OK
  Applying admin.0001_initial... OK
  Applying admin.0002_logentry_remove_auto_add... OK
  Applying admin.0003_logentry_add_action_flag_choices... OK
  Applying contenttypes.0002_remove_content_type_name... OK
  Applying auth.0002_alter_permission_name_max_length... OK
  Applying auth.0003_alter_user_email_max_length... OK
  Applying auth.0004_alter_user_username_opts... OK
  Applying auth.0005_alter_user_last_login_null... OK
  Applying auth.0006_require_contenttypes_0002... OK
  Applying auth.0007_alter_validators_add_error_messages... OK
  Applying auth.0008_alter_user_username_max_length... OK
  Applying auth.0009_alter_user_last_name_max_length... OK
  Applying auth.0010_alter_group_name_max_length... OK
  Applying auth.0011_update_proxy_permissions... OK
  Applying sessions.0001_initial... OK

C:\django_team\Django201910>python manage.py createsuperuser
Username (leave blank to use 'fin'): edwin
Email address: xujiancslg@sina.com
Password:
Password (again):
Superuser created successfully.

C:\django_team\Django201910>

http://127.0.0.1:8000/admin  --->用上一步创建的用户 edwin/edwin19850725登录