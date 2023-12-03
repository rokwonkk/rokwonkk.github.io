---
title: MacOS에 MariaDB server 설치 해보자.
author: cotes
date: 2023-12-03 13:52:10 +0900
categories: [macOS, DB]
tags: [setting]
published: true
---

## 선행 작업
 Hombrew 설치 
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

아 혹시 패스워드를 묻는다면 자기 맥OS의 패스워드를 입력 해줍니다.

## Homebrew로 MariaDB server 설치
명령어를 터미널에 입력 해 줍시다.
```bash
brew install mariadb
```
그럼 설치가 끝났습니다. 정말 쉽죠?

## MariaDB 실행
명령어를 터미널에 입력해 줍시다.
```bash
mysql.server start
```

![mariadb](https://github.com/rokwonkk/rokwonkk.github.io/assets/117067171/63ecc38b-303f-4b03-8562-aa10d8e09283)

SUCCESS! 가 보이면 실행이 됐다고 볼 수 있습니다. 정말 쉽죠?

## 자동 실행
자동 실행은 brew를 이용해서 해야합니다.
아래의 명령어를 입력해 줍니다.
```bash
brew services start mariadb
```

## root 계정 접속
root 계정으로 접속 할때는 아래 명령어를 입력해줍니다.
```bash
mysql -u root -p 
```

## 이슈
윈도우 환경이나 리눅스 환경에서는 계정 설정이 쉬웠지만

DB 툴로 붙으려고 하니 비밀번호가 계속 틀렸다고 한다. 원래 기본 비밀번호가 있는데.. 

그래서 마리아DB에 접속을 해서 직접 비밀번호를 셋팅을 해주어야한다.

```sql
set password for 'root'@'localhost' = password('비밀번호');

flush privileges; 
```

>확인

![mariadb](https://github.com/rokwonkk/rokwonkk.github.io/assets/117067171/4c0950ab-d3d1-42b3-b340-31bd133a3eb9)

정상적으로 Password에 암호화가 되서 들어가 있는 것을 볼 수 있다.

![mariadb](https://github.com/rokwonkk/rokwonkk.github.io/assets/117067171/878dc583-f326-4ae8-8f74-6a15dcd09e84)
마지막으로 툴에서 접속 Test까지 하면 끝이 납니다.

첫 포스팅이라서 많이 부족한 부분도 많고, 워터마크도 처음 사용하고해서 다사다난 하지만 

자주 사용해보고 친해져서 갈수록 깔끔하며 정리된 모습을 보이도록 하겠습니다.