---
title: "SQL을 배워봅시다_2편"
subtitle: "sql 맛보기 및 sqldeveloper 설치"
date: 2020-11-08
categories: SQL
tags: SQL
author_profile: true
toc: true
toc_sticky: true
---

## 1. CLI를 이용한 DB 접근

>[1편](https://orezmis.github.io/sql/sql_installation_and_account_setup/)

지난 강습에선 CMD 를 통해 Oracle DB에 접속하여 SQL 실습에 필요한 scott 계정의 활성화를 마쳤습니다.
그럼 본격적으로 SQL 문을 사용하여 SQL의 강력한 능력을 살짝만 맛 보도록 합시다!

지금부터는 1편에서 활성화시킨 scott 계정을 이용하여 데이터베이스에 접근 해보도록 하겠습니다.
CMD 창에서 DB에 접속을 위해 아래와 같이 타이핑을 해 주세요:

```sql
sqlplus scott/tiger
```

지금 살펴볼 SQL 문은 select 라는 키워드입니다. 아래와 같이 입력을 해 봅시다:

```sql
select * from tab;
```

|TNAME|TABTYPE|CLUSTERID|
|---------------------|-------|-------|
|BONUS|TABLE||
|DEPT|TABLE||
|EMP|TABLE||
|SALGRADE|TABLE||


우리는 처음으로 SQL 명령어를 사용하여 데이터베이스 내의 데이터에 접근을 했습니다.
우리가 적은 명령어의 의미를 풀어봅시다:

* select 는 SQL 명령문 중 DB에 저장된 데이터를 조회하기 위한 키워드 입니다.
* ' * ' 는 전체데이터를 의미하는 키워드 입니다.
* tab 은 table의 약자입니다.
* 명령문의 마지막엔 꼭 ; (세미콜론) 을 붙여주어 명령문이 끝났음을 알려줘야 합니다.

즉 위 SQL 명령어는 모든 테이블의 정보를 가지고 와라~ (조회하고 싶다~) 라는 뜻이 되겠습니다.



## 2. Oracle SQL Developer 설치 및 설정


하지만 아직은 익숙하지 않은 검은색 커맨드 프롬프트 화면에서 SQL을 작성하는게 익숙하지 않네요.
도스 커맨드창으로 명령어를 입력하는것이 멋있어 보이기는 하지만, 21세기, 2020년 현재와는 좀 맞아보이지 않습니다.

그렇기 때문에 데이터베이스를 조금 더 쉽고 윈도우 친화적으로 접근하기 위해 <span style="background-color: #e1e1ea">Oracle SQL Developer</span> 라는 프로그램을 사용합시다.


Oracle SQL Developer는 아래 링크에서 다운로드 받으실 수 있습니다:

>[Oracle SQL Developer 다운로드](https://www.oracle.com/tools/downloads/sqldev-downloads.html)

물론 Oracle SQL Developer를 이용하지 않고 기존의 커맨드 프롬프트 창을 이용하여 SQL문을 연습하여도 좋으나,
조금 더 쉽고 직관적이며 다양한 기능을 사용하며 SQL문을 작성하기 위해 위 프로그램을 사용하시길 추천합니다.

![개인 시스템에 맞는 버전을 다운받으면 됩니다.](/assets/images/OracleSQL/chap2/1.PNG)<br/><br/>



Oracle SQL Developer 는 설치하는 프로그램이 아니고 다운받은 실행 파일을 바로 실행하는 프로그램입니다.
압축파일을 풀고 사진의 아이콘을 누르시면 Oracle SQL Developer의 사용 준비가 완료 된것입니다!


![](/assets/images/OracleSQL/chap2/2.PNG)<br/><br/>

![파일을 더블클릭하면 다음과 같은 화면이 보입니다](/assets/images/OracleSQL/chap2/3.PNG)<br/><br/>

위와 같은 화면이 보인다면 Oracle SQL Developer의 사용 준비가 된것입니다.
본격적으로 데이터베이스에 접근하기 위해서는 로그인 환경 설정을 해줘야 합니다.
CMD 창에서 scott 계정에 접속하는것 처럼, 아래와 같이 Oracle SQL Developer 에서도 scott 계정에 접속을 해 봅시다.


![](/assets/images/OracleSQL/chap2/4.PNG)<br/><br/>

![복잡해 보이지만 순서대로 진행하면 안될리가 없읍니다.](/assets/images/OracleSQL/chap2/5.PNG)<br/><br/>

![이제 매번 scott/tiger 를 적을 필요 없이, 클릭 한번으로 로그인이 가능합니다.](/assets/images/OracleSQL/chap2/8.PNG)<br/><br/>

![왼쪽 위의 scott connection이 생성된것이 확인되면 준비가 끝난것 입니다.](/assets/images/OracleSQL/chap2/9.PNG)<br/><br/>


여기까지 잘 마무리 따라하셨다면 이제 정말로 SQL 의 심연속으로 빠질 준비가 된것입니다.
다음 강습부터 본격적인 SQL 문을 이용하여 데이터베이스를 접근해 봅시다!