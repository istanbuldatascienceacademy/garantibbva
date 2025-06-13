Oracle SQL Tuning Eğitimi 


1. Gün – SQL Performansı ve Execution Plan’a Giriş
Sabah Oturumu (09:30 – 12:30)

Konu 1: SQL Performansına Giriş
SQL tuning neden gereklidir?

Performans problemlerinin temel nedenleri

Sorguların Oracle'daki yaşam döngüsü

Parse, Bind, Execute, Fetch aşamaları

Soft parse vs Hard parse

Konu 2: Oracle Optimizer
Rule-Based (RBO) ve Cost-Based Optimizer (CBO)

Optimizer kararları: Cardinality, Selectivity, Join Order

İstatistiklerin önemi (DBMS_STATS, gather_* prosedürleri)

Uygulama:
Yanlış istatistikler yüzünden kötü çalışan sorgu senaryosu

İstatistik güncellemesi sonrası performans farkı

Öğleden Sonra Oturumu 

Konu 3: Execution Plan Okuma
Execution plan nedir?

EXPLAIN PLAN, AUTOTRACE kullanımı

SQL Developer Execution Plan ekranı

Operation, Cost, Cardinality, Bytes, CPU Cost gibi alanlar

Konu 4: Temel Tuning Stratejileri
SELECT * vs hedef sütun seçimi

Gereksiz subquery, view ve DISTINCT kullanımı

OR yerine UNION

EXISTS vs IN vs JOIN farkları

Uygulama:
Aynı sorgunun farklı varyasyonları ile performans analizi

Execution Plan karşılaştırması: EXISTS vs IN vs JOIN

2. Gün – İndeksler, Hintler, Join Stratejileri
Sabah Oturumu (09:30 – 12:30)

Konu 1: İndekslerin Performansa Etkisi
B-Tree vs Bitmap Index

Composite, Unique, Function-Based Index

İndeksin kullanılmama nedenleri

Index-only access vs Table Access by Rowid

Konu 2: Hint Kullanımı
Hint nedir, ne zaman kullanılır?

Yaygın hintler: FULL, INDEX, LEADING, PARALLEL, USE_NL, NO_MERGE

Hint kullanımında dikkat edilmesi gerekenler

Uygulama:
Aynı sorguya çeşitli hint’ler vererek execution plan etkisini analiz etme

Gereksiz FULL SCAN önleme örneği

Öğleden Sonra Oturumu 

Konu 3: Join Stratejileri
Nested Loop, Hash Join, Merge Join

Hangi durumda hangi join daha iyidir?

Join sırasının optimizer üzerindeki etkisi

Join order değiştirme

Konu 4: View & Subquery Performansları
Inline View vs With Clause

View’ların execution plana etkisi

Materialized View kullanımı ve Query Rewrite

Uygulama:

JOIN stratejileri ile aynı veri üzerinde performans ölçümü

Complex view ile inline view karşılaştırması

3. Gün – Gerçek Hayat Senaryoları ve Sistem Seviyesi Tuning
Sabah Oturumu (09:30 – 12:30)

Konu 1: SQL Performans Problemleri Nasıl Tespit Edilir?
v$sql, v$session, v$sqlarea

Top 10 CPU tüketen SQL sorguları bulma

AWR, ASH raporları nasıl okunur?

SQL Tuning Advisor, SQL Access Advisor

Konu 2: Bind Variable ve Literals
Bind variable nedir? Literals ile farkı nedir?

Hard parse problemi

CURSOR_SHARING parametresi

Bind Peeking problemi

Uygulama:
Literal vs bind variable ile performans karşılaştırması

SQL tuning advisor çıktısı üzerinden analiz

Öğleden Sonra Oturumu 

Konu 3: Büyük Veri Setlerinde Performans
Partitioning kavramı (Range, List, Hash)

Parallel query yapısı

DML işlemlerinde performans tuning (MERGE, INSERT, DELETE)

Konu 4: Tuning Checklist ve Gerçek Senaryolar

SQL tuning için kontrol listesi

Sık karşılaşılan performans problemleri ve çözümleri

Örnek vaka analizi (slow report, batch job vb.)

Uygulama:
Gerçek bir senaryo üzerinden uçtan uca tuning egzersizi

AWR raporu -> execution plan -> tuning önerisi -> test
