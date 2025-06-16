tüm aktif SQller vealışma değerli
```
SELECT sql_id,
       parsing_schema_name,
       executions,
       elapsed_time / 1000000 AS elapsed_sec,
       cpu_time / 1000000 AS cpu_sec,
       buffer_gets,
       disk_reads,
       sql_text
FROM v$sql
ORDER BY elapsed_time DESC
FETCH FIRST 20 ROWS ONLY;
```

Özet veriler
```


SELECT sql_id,
       executions,
       buffer_gets,
       disk_reads,
       parse_calls,
       substr(sql_text, 1, 100) AS sql_snippet
FROM v$sqlarea
ORDER BY buffer_gets DESC
FETCH FIRST 20 ROWS ONLY;
```


```

SELECT name, namespace, type, sharable_mem, kept
FROM v$db_object_cache
WHERE type IN ('PROCEDURE', 'FUNCTION', 'PACKAGE')
ORDER BY sharable_mem DESC;
```

selectivity
0---1
select  *  from product where category='laptop'

product tablosunda 10.000  kayıt  var
cate=laptop 100 ürünü filtree

100/10000 =0.01

cardinality =10000 X seelectivity =100


```

VARIABLE task_name VARCHAR2(30);
BEGIN
  :task_name := DBMS_SQLTUNE.CREATE_TUNING_TASK(
    sql_id => 'v$sqlden yakala',
    scope => 'COMPREHENSIVE',
    time_limit => 60,
    task_name => 'my_sql_tuning_task',
    description => 'Tuning task for slow query');
END;
/
```
```

BEGIN
  DBMS_SQLTUNE.EXECUTE_TUNING_TASK(task_name => 'my_sql_tuning_task');
END;
/
```
```

SET LONG 10000
SET PAGESIZE 1000
SELECT DBMS_SQLTUNE.REPORT_TUNING_TASK('my_sql_tuning_task') FROM DUAL;
```

GENERAL INFORMATION SECTION
---------------------------
Tuning Task Name   : tune_my_sql
Scope              : COMPREHENSIVE
Time Limit(seconds): 60

FINDINGS SECTION
----------------
1- Statistics Finding
  - Table "HR"."EMPLOYEES" has stale or missing statistics.

2- Index Finding
  - The execution plan can be improved by creating the following index:
    CREATE INDEX HR.IDX_EMP_SALARY ON EMPLOYEES(SALARY);

3- SQL Profile Finding
  - A potentially better execution plan was found.
    SQL Profile can be used to fix it.

BEGIN
  DBMS_SQLTUNE.ACCEPT_SQL_PROFILE(task_name => 'tune_my_sql', name => 'my_profile');
END;
/


bir sorgu sürekli yavs----- v$sql ile sqlid yakala

execution plan a bak ----  mantıksız- tuning advisor çalıştır mutlaka






