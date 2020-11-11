---
layout: post
title: 자주 사용하는 Shell script
author: ppoox
color: purple
tags: [Shell, Script]

---


### 자주 사용하는 Shell script

---

**입출력 관련**

-   `>` : 파일이 없으면 생성, 있으면 덮어쓰기(write or overwrite)
-   `>>` : 파일이 없으면 생성, 있으면 덧붙이기(wirte or append)

-   `0` : 표준 입력(STDIN-standard input)
-   `1` : 표준 출력(STDOUT-standard output)
-   `2` : 표준 에러(STDERR-standard error)
-   `2 > &1` : 표준 에러를 표준 출력으로 리다이렉팅

-   `/dev/null` : 아무것도 아닌 장치파일

-   `/dev/null > 로그파일.log` : 로그파일을 비워주게된다.
-   `1 > /dev/null` : 표준 출력을 아무것도 아닌 파일로 출력한다(버린다)
-   `2 > /dev/null` : 표준 에러를 아무것도 아닌 파일로 출력한다(버린다)

-   `> /dev/null 2 > &1` : 표준 출력을 아무것도 아닌 장치파일에 기록하고(버리고) 표준 에러를 표준 출력으로 리다이렉팅, 결국 아무것도 보여주지마라

---

**연속적인 커맨드실행 관련**

-   `;` : 성공여부와 상관없이 다음 명령어 실행
-   `&&` : 성공한 경우에 다음 명령어 실행