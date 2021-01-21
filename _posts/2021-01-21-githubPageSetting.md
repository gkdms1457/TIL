---
title : github 블로그 시작하기
category :
    - git
tag :
    - jekyll
    - github page
---
# github 블로그 시작하기

## 블로그를 시작하게된 계기

 [진유림님의 TIL블로그](http://milooy.github.io/TIL/)를 보고 GITHUB를 이런식으로 활용하는 방법도 있다는 것을 알았다. 이 전에도 GIT, GITHUB를 써야된다고는 생각을 하다가 어떤걸 해야될지 몰라 미루고 있었다. 그래서 저분처럼 기존에 알고있던 지식, 새롭게 알게된 지식을 정리해서 나만의 위키피디아를 만들어보고자 일단 시작하게되었다. 그 전에 GIT을 써봤던게 아니라서 익숙하지도 않고 잘하지도 않지만, 이런식으로라도 시작해보자는 마음으로 무작정 시작했다.

## 1. 저장소(repository) 만들기

 인터넷에 검색해보니 대부분의 저장소 이름을 **username.github.io** 로 설정하라고 나와있었다. 이런식으로 저장소를 만들고 **username.github.io**의 url로 접속가능한 페이지가 생성된다. 나는 주목적이 공부내용을 정리하는 것이어서 진유림님의 페이지처럼 **github.io/TIL/**의 url로 하고싶었다. 그래서 찾아보니 프로젝트별 페이지를 만들 수 있다고 나왔다. 그래서 저장소 이름을 TIL(prohectname)으로 설정하고 **github.io/projectname**의 url로 접속하도록 하였다.(아직 마크다운이 익숙하지 않아 사진은 나중에 첨부할 예정이다.)


## 2. jekyll 테마 고르기
 http://jekyllthemes.org/ 에 들어가보면 수많은 테마가 공개되어 있다. 이 중 원하는 테마를 선택하면 된다. 나는 minimal-mistakes를 선택하였다. 나중에 커스터마이징에 편리하다고 한다.

## 3. 해당 테마 clone
 터미널에서 해당 테마를 clone해준다.
    git clone https://github.com/mmistakes/minimal-mistakes .
 이때 마지막에 .을 붙이지 않는다면 minimal-mistakes라는 이름의 디렉토리를 만들고 그 아래에 내용을 받아온다. .을 붙이면 현재 디렉토리에 받아오게된다.

## 4. 받아온 파일의 .git삭제 후 내 주소 연결
 clone을 해온 후 **git remote -v 를 실행해보면 테마 파일을 받아온 주소로 설정되어있다. 내 블로그에 remote를 해야하기 때문에 .git파일을 삭제해준다. 그 후 git 저장소를 생성한다. 그 다음 원격저장소를 내 주소로 저장한다.
    git init #git 저장소 생성
    
    git remote add origin https://username.github.io/TIL.git #원격저장소 등록

    git remote -v #원격저장소 목록 확인
 

## 5. 테마 적용하기
 받아온 테마를 내 github에 올려준다.    
    git add . # 모든 파일을 스테이지에 추가

    git commit -m 'change theme' #commit

    git push origin master #push
 위의 내용을 실행한 후 블로그에 접속해보면 테마가 적용된 것을 볼 수 있다.

이 후 jekyll의 파일들을 수정하여 커스터마이징한다.
