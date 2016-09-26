---
title: Python Django 快速入門教學：打造食譜分享社群網站
date: 2016-06-11 22:00:00
tags: Python, Django, Mvc, Web, MTV, Web Backend, Web Framework, 教學 
author: kdchang
---
# 什麼是 Python？

# 什麼是 Django？

# 環境建置與設定

```
// -m 代表執行模組或函式庫 
$ python3 -m venv opencook_venv
```

```
$ source opencook/bin/activate

(opencook_venv)$~/
```

```
$ deactivate
```

# 開始 Django 專案

1. 初始化專案

	```shell
	$ django-admin.py startproject opencook
	$ cd opencook
	$ python manage.py migrate

	Operations to perform:
	  Apply all migrations: admin, auth, contenttypes, sessions
	Running migrations:
	  Applying contenttypes.0001_initial... OK
	  Applying auth.0001_initial... OK
	  Applying admin.0001_initial... OK
	  Applying admin.0002_logentry_remove_auto_add... OK
	  Applying contenttypes.0002_remove_content_type_name... OK
	  Applying auth.0002_alter_permission_name_max_length... OK
	  Applying auth.0003_alter_user_email_max_length... OK
	  Applying auth.0004_alter_user_username_opts... OK
	  Applying auth.0005_alter_user_last_login_null... OK
	  Applying auth.0006_require_contenttypes_0002... OK
	  Applying auth.0007_alter_validators_add_error_messages... OK
	  Applying auth.0008_alter_user_username_max_length... OK
	  Applying sessions.0001_initial... OK
	```

	資料夾結構：

	```
	opencook/
	├── manage.py
	└── mysite
	    ├── __init__.py
	    ├── settings.py
	    ├── urls.py
	    └── wsgi.py
	```

	```
	$ python manage.py runserver

	Starting development server at http://127.0.0.1:8000/
	Quit the server with CONTROL-C.
	```

	![Python Django 快速入門教學：打造食譜分享社群網站 ](hello-world.png)

2. Django 的 Management commands

	- django-admin.py startproject <project_name>：建立初始化 Django 專案
	- python manage.py -h <command_name>：查看 Django commands 的使用方法
	- python manage.py runserver：啟動開發用伺服器
	- python manage.py startapp <app_name>：新增 Django app

3. 建立 Django application（app）
	
	```
	python manage.py startapp recipes
	```

4. 將新增的 Django app 加入設定檔

	```python
	# mysite/settings.py

	...

	# Application definition

	INSTALLED_APPS = (
	    'django.contrib.admin',
	    'django.contrib.auth',
	    'django.contrib.contenttypes',
	    'django.contrib.sessions',
	    'django.contrib.messages',
	    'django.contrib.staticfiles',
	    'recipes',
	)
	```

# 是 MVC？ 還是 MTV？
MVC 架構

# Views and URLconfs

# Templates

# Models

# Admin

# Django ORM

# 進階 Templates 使用

# 動態 URL

# 成果展示

# 總結

# 延伸閱讀
1. [Django 官網](https://www.djangoproject.com/)
2. [Django Girls Taipei](https://djangogirls.org/taipei/)
3. [Django Girls 學習指南](https://www.gitbook.com/book/djangogirlstaipei/django-girls-taipei-tutorial/details)
4. [良葛葛 Python Gossip](http://openhome.cc/Gossip/Python/)
5. [Django 1.8.x staticfile ，静态文件配置](http://blog.mymusise.com/?p=170)
6. [Django Girls Tutorial](https://www.gitbook.com/book/djangogirls/djangogirls-tutorial/details)
7. [在django項目中加入像bootstrap這样的css，js等靜態文件](http://fanli7.net/a/bianchengyuyan/C__/20140216/470245.html)
8. [What is the naming convention in Python for variable and function names?](http://stackoverflow.com/questions/159720/what-is-the-naming-convention-in-python-for-variable-and-function-names)
9. [how to use the href attribute in django templates](http://stackoverflow.com/questions/17200389/how-to-use-the-href-attribute-in-django-templates)