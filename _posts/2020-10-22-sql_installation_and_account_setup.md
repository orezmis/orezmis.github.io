---
title: "SQL을 배워봅시다_1편"
subtitle: "DB설치 및 계정활성"
author: "orezmis"
date: 2020-10-22
categories: SQL
tags: SQL
toc: true  
toc_sticky: true 
---

## 1. Database  설치
SQL을 사용하기 위해선 우선 컴퓨터에 database가 설치되어야 합니다.
해당 강좌에서는 Oracle의 database를 사용합니다.
Oracle database는 Oracle 공식 홈페이지에서 다운받을 수 있습니다:

>[Oracle DB 다운로드](https://www.oracle.com/database/technologies/xe-prior-releases.html)

본 강좌에서 사용하는 버전은 Oracle 11G Express Edition으로, 줄여서 OracleXE11 이라고 합니다. 위 링크에 접속하여 간단한 회원가입을 하시고 다운을 받으시면 됩니다.

![윈도우 64bit, 32bit, 리눅스 버전등 자신의 컴퓨터 시스템에 맞는 버전을 다운 받으면 된다](/assets/images/OracleSQL/chap1/1.PNG)

설치되는 중간 비밀번호를 입력하라는 화면이 나옵니다. 이것은 오라클 데이터베이스 시스템 관리자 비밀번호를 설정하는것입니다.

본 강습을 따라하면서는 <span style="background-color: #e1e1ea">admin1234</span> 라는 비밀번호를 사용합시다.

![기업에서는 database 최고관리자만 이 비밀번호를 설정 해야한다.](/assets/images/OracleSQL/chap1/7.PNG)


설치가 완료되면 아래의 <span style="background-color: #e1e1ea">scott.sql</span> 파일을 받아 <span style="background-color: #e1e1ea">c: 바로 아래에 저장</span>합니다.

>[scott.sql 다운로드](/assets/scott.sql)
>> 위 파일은 가상의 회사 환경을 구축하여, SCOTT 이라는 인사담당자의 계정으로 회사내의 각종 인사/급여 정보들을 데이터베이스에 저장하여 우리가 쉽고 빠르게 회사 데이터를 갱신, 검색, 수정, 삭제끔 하도록 하는 기초 파일입니다.

![이곳이 C: 아래이다.](/assets/images/OracleSQL/chap1/3.PNG)


sql 확장자가 붙은 파일은 메모장으로 열어 볼 수 있습니다. 한번 열어보시기를 권장합니다. 지금은 알 수 없는 내용들이 나중에 다시보면 이해가 될 것입니다.

## 2. Database 실행
윈도우 10 기준으로, 검색창에서 <span style="background-color: #e1e1ea">CMD 프로그램</span>을 찾아 <span style="background-color: #e1e1ea">"관리자 권한으로 열기"</span> 로 실행합니다.

![관리자 권한 실행](/assets/images/OracleSQL/chap1/4.png)

CMD 창에서 아래와 같이 타이핑을 합시다:

```sql
>sqlplus system/admin1234
```
* sqlplus 키워드는 Oracle Database를 실행시키는 명령어입니다.
* system 은 시스템의 계정이름, admin1234는 DB를 설치할때 설정한 비밀번호 입니다.
* 계정이름과 비밀번호는 / 로 구분이 되며, 아래와 같이 접속할 수도 있습니다:

```sql
>sqlplus

SQL*Plus: Release 11.2.0.2.0 Production on Sun Aug 2 02:35:00 2020

Copyright (c) 1982, 2014, Oracle, All rights reserved.

>Enter user-name: system
>Enter Password:

-- 이 방법은 비밀번호가 보이지 않습니다.
```

성공적으로 system 계정으로 데이터베이스(DB) 에 접속하였다면, 프롬프트 창에  SQL>  라는 문구와 커서가 보일것입니다.

그럼 또 다음과 같은 키워드를 입력해 봅시다:

```sql
-- 입력
SQL> @c:\scott.sql
```
* 위 커맨드는 아까 받은 scott.sql 파일을 읽어옵니다.

```sql
-- 입력
SQL> alter user scott identified by tiger;
```
```sql
-- 결과
User altered.
```
* scott 계정의 비밀번호를 tiger 로 변경합니다.
* 계정과 비밀번호에 관해서는 나중에 배웁니다.

```sql
-- 입력
SQL> conn scott/tiger
```
```sql
-- 결과
Connected.
```
* scott 계정으로 접속하겠다는 커맨드 입니다.

```sql
-- 입력
SQL> show user;
```
```sql
-- 결과
User is "SCOTT"
```
* 현재 DB 에 접속중인 계정을 보여줍니다. 
* 현재 scott 계정에 잘 접속 해 있는것을 볼 수 있습니다.

```sql
-- 입력
SQL> quit
```
* DB 를 종료합니다.

본격적으로 DB 에 저장된 데이터를 SQL 문으로 제어할 준비가 되었습니다.다음강습에 다시 한번 매력적인 SQL의 세계로 빠져봅시다.