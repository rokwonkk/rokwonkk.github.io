---
title: MacOS에 MariaDB server 설치 해보자.
author: cotes
date: 2023-12-03 13:52:10 +0900
categories: [macOS, DB]
tags: [setting]
published: false
---

## 선행 작업
> Hombrew 설치 
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

아 혹시 패스워드를 묻는다면 자기 맥OS의 패스워드를 입력 해줍니다.

## Homebrew로 MariaDB server 설치
>명령어를 터미널에 입력 해 줍시다.
```bash
brew install mariadb
```
그럼 설치가 끝났습니다. 어떻습니까 정말 쉽죠?

## MariaDB 실행
>명령어를 터미널에 입력 해 줍시다.
```bash
mysql.server start
```
![Desktop View](asserts/img/mariadb.png){: width="700" height="400" }