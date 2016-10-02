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

# 表單互動

1. 用 HTML 刻個 form 表單
2. 處理 HTTP POST request
3. 驗證表單欄位內容是否正確
4. 把確認過的資料存進 database 之中

```python
def signup(request):
    if request.user.is_authenticated(): 
        return HttpResponseRedirect('/')

    if request.method == 'POST':
        form = UserCreationForm(request.POST)
        if form.is_valid():
            user = form.save()
            return HttpResponseRedirect('/accounts/login')

        return render(request, 'accounts/signup.html', locals())
    else:
    	form = UserCreationForm()
    	return render(request, 'accounts/signup.html', locals())
```

```html
{% extends 'extends/base.html' %}

{% block content %}
<br>
<br>
<br>
<br>
<div class="container">
	<h1>註冊新帳號</h1>
	<form action="/contact/" method="post">
	    {% for field in form %}
	        <div class="fieldWrapper">
	            {{ field.errors }}
	            {{ field.label_tag }} {{ field }}
	        </div>
	    {% endfor %}
	    {% csrf_token %}
	    <button class="btn btn-primary" type="submit">註冊</button>
	</form>
</div>
{% endblock content %}
```

# 進階 Templates / Template Filters 使用

# 動態 URL

# 成果展示

# Deploy 部屬到 Digital Ocean

1. [How to Deploy a Django Application on DigitalOcean](https://www.codementor.io/python/tutorial/how-to-deploy-a-django-application-on-digitalocean) 
2. [How To Use the Django One-Click Install Image](https://www.digitalocean.com/community/tutorials/how-to-use-the-django-one-click-install-image)
3. [Django Tutorials](https://www.digitalocean.com/community/tags/django?type=tutorials)
4. [How To Set Up Django with Postgres, Nginx, and Gunicorn on Ubuntu 14.04](https://www.digitalocean.com/community/tutorials/how-to-set-up-django-with-postgres-nginx-and-gunicorn-on-ubuntu-14-04)
5. [How To Install the Django Web Framework on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-the-django-web-framework-on-ubuntu-16-04)
6. [How To Deploy a Local Django App to a VPS](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-local-django-app-to-a-vps)

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
10. [django rest framework 小小心得](http://sillygod-blog.logdown.com/posts/663369)
11. [Beginner's Guide to the Django Rest Framework](https://code.tutsplus.com/tutorials/beginners-guide-to-the-django-rest-framework--cms-19786)
12. [How To Use PostgreSQL with your Django Application on Ubuntu 14.04](https://www.digitalocean.com/community/tutorials/how-to-use-postgresql-with-your-django-application-on-ubuntu-14-04)
13. [使用Django內建的帳號管理系統](https://yichen0831.wordpress.com/2013/02/17/%E4%BD%BF%E7%94%A8django%E5%85%A7%E5%BB%BA%E7%9A%84%E5%B8%B3%E8%99%9F%E7%AE%A1%E7%90%86%E7%B3%BB%E7%B5%B1/comment-page-1/)
14. [uranusjr/django-tutorial-for-programmers](https://github.com/uranusjr/django-tutorial-for-programmers)
15. [dokelung/Python-QA](https://github.com/dokelung/Python-QA)
16. [Django筆記(10) - 用戶的登入與登出](http://dokelung-blog.logdown.com/posts/234437-django-notes-10-users-login-and-logout)
17. [Django Tutorial](http://daikeren.github.io/django_tutorial/)
18. [Django Packages](https://djangopackages.org/)
19. [在 Django 中实现用 email 登录](http://guoqiao.me/post/2014/0904-login-by-email-in-django)
20. [Django Tutorial: Making Your Own Template Filters](http://www.pfinn.net/custom-django-filter-tutorial.html)
21. [Django: 'current_tags' is not a valid tag library](http://stackoverflow.com/questions/5493776/django-current-tags-is-not-a-valid-tag-library)
22. [Custom template tags and filters¶](https://docs.djangoproject.com/en/dev/howto/custom-template-tags/#assignment-tags)
23. [how to use custom django templatetag with django template if statement?](http://stackoverflow.com/questions/14767516/how-to-use-custom-django-templatetag-with-django-template-if-statement)
24. [Recommended Django Project Layout](http://www.revsys.com/blog/2014/nov/21/recommended-django-project-layout/)
25. [How to validate Google reCAPTCHA v2 in django](http://stackoverflow.com/questions/29548574/how-to-validate-google-recaptcha-v2-in-django)

