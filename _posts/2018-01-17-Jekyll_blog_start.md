---
layout: post
title: "Jekyll Git 블로그 만들기"
date: 2018-01-17 12:00:00
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img:  # Add image post (optional)
---
# Jekyll 블로그 만들기
Web-Programming School 1월 17일 수업 <br>
[Che1's Blog 참고](https://nachwon.github.io/)

--------------
## 루비 설치
### 패키지 목록 업데이트
```
$sudo apt-get update
$sudo apt-get upgrade
```
온라인 저장소에서 최신 버전의 패키지들 업로드 -> 실제 설치 해주는 명령어는 `upgrade`

### Ruby에 필요한 의존성 패키지 설치
```
$sudo apt-get install autoconf bison build-essential libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm3 libgdbm-dev
```

### Ruby 버전관리 프로그램 설치
`git clone https://github.com/rbenv/rbenv.git ~/.rbenv`

*.[파일명] : 숨긴 폴더*


### rbenv 실행 환경변수 설정(zsh 셸)
```
$echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.zshrc
$echo 'eval "$(rbenv init -)"' >> ~/.zshrc
$source ~/.zshrc
```

### Ruby - build 플러그인 설치
```
$git clone https://github.com/rbenv/ruby-build.git~/.rbenv/plugins/ruby-build
```

설치 후 `$rbenv` 명령어 입력, **install** 과 **uninstall** 생기는 것 확인
### Ruby 설치하기
```
$rbenv install -l
$rbenv install 2.5.0
$ruby -v
$rbenv global 2.5.0
```

설치 가능한 Ruby 버전확인 -> Ruby 2.5.0 버전 설치 -> Ruby 버전 확인 -> 시스템 전체 버전을 설정

### Jekyll블로그에 필요한 Gem 설치
### bundler 설치
`$gem install bundler`

### github-pages 설치
`$gem install github-pages`
git하고 연동하는데 필요한 패키지

### jekyll설치
`$gem install jekyll`

----------------

## 로컬에서 Jekyll 블로그 시작하기
### 블로그 생성
```
$mkdir blog
$cd blog
$jekyll new 블로그이름
```

원하는 디렉토리를 만들고 그 곳으로 이동한 다음 `jekyll new 블로그이름` 명령어 실행

### Gemfile 수정 및 적용
```
$ vim Gemfile
```
gem "jekyll", "~> 3.7.0"  -> 커맨드 처리
gem "github-pages", group: :jekyll_plugins -> 커맨드 해제
저장 한 후 밑에 명령어 실행

```
$bundle install
$bundle update
```

### 로컬 테스트 서버 실행하기
블로그가 있는 폴더에서 아래 명령을 실행

`$bundle exec jekyll server`

-------------------
## Github에 블로그 업로드하기
### GIthub 에서 새로운 저장소 생성
**사용자명.github.io** 으로 설정

### 로컬 저장소 생성 및 연결
```
$git init
$git remote add origin [remote저장 주소]
```

### 로컬 저장소 파일 업로드
```
$git diff
$git add -A
$git commit -m 'commit메시지'
$git push origin master
```
`git diff`는  변경 사항이 무엇인지 알려주는 명령어<br>
`commit`하기 전에 확인하기!
그리고 자신의 블로그 주소에 접속하면 **완료!**
*만약 블로그에 들어갔는데, 변경 사항이 적용이 안됬을 경우, 몇 분 기달려보기*

------------
## 기타
config.yml : 블로그 설정파일<br>
서버를 하나 켜놓고, md파일을 수정하면서 확인 할것<br>
hosting.kr : 도메인사서 설정할 수 있는 페이지<br>
