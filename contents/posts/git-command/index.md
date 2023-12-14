---
title: "Git 기본 명령어"
description: "Git 기본 명령어에 대해 알아보자"
date: 2023-06-27
update: 2023-06-27
tags:
  - Git
---

![](1.png)

### Git 저장소 생성

```git
$ git init
```

### 기본 브랜치 이름 변경

```git
$ git config --global init.defaultBranch 변경할_브랜치_이름
```

### 현재 상태 확인

```git
$ git status
```

### 전체 로그 확인

```git
$ git log
```

### Staging area로 파일 이동시키기

```git
$ git add .
```

### 저장소 복제 및 다운로드

```git
$ git clone https://github.com/{GITHUB_NAME}/{REPOSITORY_NAME}.git
```

### 파일을 Local repository에 저장하고 버전을 기록(commit)

```git
$ git commit -m "message"
```

### Remote repository로 업로드

```git
$ git push origin master
```

### 원격 저장소의 변경 내용을 현재 디렉토리로 가져오기 (pull)

```git
$ git pull
```

### Remote repository와 Local repository를 연결

```git
$ git remote --v
```

### 브랜치 삭제

```git
$ git branch -d [브랜치명]
```

### 현재 브랜치에 다른 브랜치 수정사항 병합

```git
$ git merge [다른 브랜치명]
```

### 복사할 코드가 있는 Rmote Repository의 코드를 내 Rmote Repository로 복사

```git
$ Fork
```

### 상대의 Rmote Repository 주소를 내 Local Repository와 연결

```git
$ git rmote add pair [상대의 Rmote Repository 주소]
```

### 연결된 주소들의 목록 확인

```git
$ git rmote -v
```

### 파일 수정

```git
$ nano [파일이름]
```

### 수정한 파일을 staging area에 추가 (commit 전)

```git
$ git add [파일이름]
```

### commit이 되지 않은 파일을 폐기

```git
$ git restore [파일이름]
```

### staged된 파일을 이전 상태로 되돌림

```git
$ git restore --staged
```

