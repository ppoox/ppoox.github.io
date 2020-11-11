---
layout: post
title: Table schema to Java model
author: ppoox
tags: [Back-end, Java, Oracle, Model]
---


**ORACLE 테이블 스키마를 자바 모델로 조회**

```sql
SELECT '/* '||NVL(COMMENTS, 'COMMENTS가 없습니다.')||' */'||CHR(10)
        ||'private '||DECODE (DATA_TYPE , 'VARCHAR2' , 'String ' ,'NUMBER',  'java.lang.Integer ', 'DATE','java.sql.Timestamp ','String ')
        || LOWER(SUBSTR(REPLACE(INITCAP(A.COLUMN_NAME),'_'),1,1))
        || SUBSTR(REPLACE(INITCAP(A.COLUMN_NAME),'_'),2) || ';' AS columnName
      , instr (A.COLUMN_NAME , '_') AS columnSz
   FROM ALL_TAB_COLUMNS A
      , ALL_COL_COMMENTS B
  WHERE A.TABLE_NAME = B.TABLE_NAME
    AND A.OWNER = B.OWNER
    AND A.TABLE_NAME = B.TABLE_NAME
    AND A.COLUMN_NAME = B.COLUMN_NAME
    AND A.TABLE_NAME = '테이블명';
```

---
출력 예시 -     
/* 코멘트 */     
private java타입 컬럼명;
