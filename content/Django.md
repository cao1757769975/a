---
title: "Django 基本操作命令"
date: 2020-04-22T15:29:10+08:00
---

## Django基本操作命令
#### 1、新建一个django项目
```
django-admin.py startproject project-name(项目名)
```
 

#### 2、新建一个app
```
python manage.py startapp app-name(app名)
```
 

#### 3、同步数据库（数据库迁移）
```
python manage.py syncdb

注意：Django 1.7.1及以上的版本需要用以下命令
python manage.py makemigrations
python manage.py migrate
```
这种方法可以创建表，当你在models.py中新增了类时，运行它就可以自动在数据库中创建表了，不用手动创建。
备注：对已有的 models 进行修改，Django 1.7之前的版本的Django都是无法自动更改表结构的，不过有第三方工具south

 

#### 4、运行命令
```
python manage.py runserver 
```
 

#### 5、清空数据库
```
python manage.py flush
```
此命令会询问是 yes 还是 no, 选择 yes 会把数据全部清空掉，只留下空表。

 

#### 6、创建超级管理员
```
python manage.py createsuperuser
```
 

#### 7、导出数据、导入数据
```
python manage.py dumpdata appname > appname.json
python manage.py loaddata appname.json
```
 

#### 8、django项目环境终端
```
python manage.py shell
```
如果你安装了bpython或者ipython，会自动调用他们的界面

 

#### 9、数据库执行命令
```
python manage.py dbshell
```
django会进行到settings中设置的数据库，如果是mysql或者postgresql，会要求输入用户名和密码

在这个终端可以输入sql语句

 

#### 10、更多命令

在终端上输入python manage.py 回车，就可以看到详细的列表
