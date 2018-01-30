---
layout: post
title: "Djangogirls_Tutoria(1)"
date: 2018-01-29 09:00:00
img: ./post_img/django.png
category: Django
---
>본 문서는 패스트캠퍼스 'Web-Programming School' 수업 자료를 바탕으로 작성되었습니다.
><Br>**Ubuntu 16.04 환경**

---
## 가상환경 설정
```
$pyenv virtualenv 3.6.4 fc-djangogirls
$pyenv logcal fc-djangogirls
$git init
$vim .gitignore
// gitignore.io 사이트에서 환경설정에 지정해서 복붙
```
pycharm - setting - project interpreter - fc-dajangogirls로 설정<br>
`git status`로 .idea/ 폴더 있는지 확인 후, 연결 된 Git Repository에 commit!

## 장고 설치
```
$pip install django
Collecting django
  Using cached Django-2.0.1-py3-none-any.whl
Collecting pytz (from django)
  Using cached pytz-2017.3-py2.py3-none-any.whl
Installing collected packages: pytz, django
Successfully installed django-2.0.1 pytz-2017.3
```

---
## Django란?
> Django는 파이썬으로 만들어진 무료 오픈소스 웹 애플리케이션 프레임워크<br>

## 서버와 웹페이지 동작 방식
1. 브라우저에서  HTTP 요청 -> DNS -> IP -> request -> 서버컴퓨터에 도착
2. 서버컴퓨터의 웹 서버 프로그램이 해당 요청을 받음
3. 웹 서버 프로그램은 웹 애플리케이션에 요청에 대한 응답의 제작을 요청
4. 웹 애플리케이션은 요청에 대한 응답을 동적으로 생성해서 웹 서버에게 돌려줌
5. 웹 서버는 자신이 요청하고 받은 응답을 다시 사용자에게 전송
6. 브라우저에 전송

---
## 나의 첫 번째 장고 프로젝트!
> Note 이 장의 일부는 Geek Girls Carrots (http://django.carrots.pl/)의 튜토리얼을 기초로 작성되었습니다.<br>
> Note 이 장의 일부는 Creative Commons Attribution-ShareAlike 4.0 International License에 준수하여 django-marcador 튜토리얼를 기초로 작성되었습니다. django-marcador 튜토리얼 저작권은 Markus Zapke-Gründemann et al이 소유하고 있습니다.

### 프로젝트 만들기
Django project 를 구성하는 코드를 자동 생성하며 이 과정에서 데이터베이스 설정, 옵션, 어플리케이션을 위한 설정과 관련된 Django인스턴스를 구성하기 때문에 **초기 설정 주의**

```
$django-admin startproject mysite
```

현재 디렉토리에서 mysite라는 디렉토리 생성

```
└── mysite
    ├── manage.py
    └── mysite
        ├── __init__.py
        ├── settings.py
        ├── urls.py
        └── wsgi.py
```

`tree`로 확인한 디렉토리 구조
mysite - mystie 디렉토리의 경우, setting 관련한 디렉토리이므로 **config** 로 디렉토리명 변경 <br>
mysite 디렉토리 이름도 알기 쉽게 **Django** 로 변경

```
Django
    ├── config
    │   ├── __init__.py
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    └── manage.py
```
Django 디렉토리 **Source root** 로 설정 (Pycharm에서 디렉토리가 파란색으로 변함)
- manage.py : Django 프로젝트와 다양한 방법으로 상호작용 하는 커맨드라인의 유틸리티
- settings.py : project 환경/구성 저장
- urls.py : 현재 Django project의 url선언 저장.

### 설정 변경
**config/seetings.py** 변경
```
# Internationalization
# https://docs.djangoproject.com/en/2.0/topics/i18n/

LANGUAGE_CODE = 'Ko-kr'

TIME_ZONE = 'Asia/Seoul'
```
**TIME_ZONE** 은 국제표준 UTC기준을 따름<BR>
서버에 저장하는 시간과 클라이언트에 따라 보여주는 것을 다르게 하기 위해 설정

### 웹 서버 시작
프로젝트 디렉토리에 **manage.py** 파일이 있어야 하며, 아래 명령어를 통해 웹 서버 실행<br>
사용하는 브라우저에서 `localhost:8000`/`127.0.0.1:8000`으로 확인 <br>
```
$python manage.py runserver
```

<!-- ![장고이미지]({{ site.url }}/assert/img/post_img/djangorunserver.png)
<img src = "./post_img/djangorunserver.png"> -->
