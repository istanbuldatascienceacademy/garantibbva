# 📘 Oracle SQL Tuning Eğitimi

Oracle veritabanında çalışan SQL sorgularının performansını analiz etmeyi ve iyileştirmeyi amaçlayan 3 günlük uygulamalı eğitim programıdır.

---

## 🗓️ 1. Gün – SQL Performansı ve Execution Plan’a Giriş

### ⏰ Sabah Oturumu (09:30 – 12:30)

#### 🧩 Konu 1: SQL Performansına Giriş
- SQL tuning neden gereklidir?
- Performans problemlerinin temel nedenleri
- Sorguların Oracle'daki yaşam döngüsü
  - Parse, Bind, Execute, Fetch aşamaları
- Soft parse vs Hard parse

#### 🧠 Konu 2: Oracle Optimizer
- Rule-Based (RBO) ve Cost-Based Optimizer (CBO)
- Optimizer kararları: 
  - Cardinality
  - Selectivity
  - Join Order
- İstatistiklerin önemi
  - DBMS_STATS, gather_* prosedürleri

#### 🛠️ Uygulama
- Yanlış istatistikler yüzünden kötü çalışan sorgu senaryosu
- İstatistik güncellemesi sonrası performans farkı

---

### ⏰ Öğleden Sonra Oturumu (13:30 – 17:00)

#### 🔍 Konu 3: Execution Plan Okuma
- Execution plan nedir?
- EXPLAIN PLAN, AUTOTRACE kullanımı
- SQL Developer Execution Plan ekranı
- Plan alanları: 
  - Operation, Cost, Cardinality, Bytes, CPU Cost

#### 🛠️ Konu 4: Temel Tuning Stratejileri
- SELECT * yerine hedef sütun seçimi
- Gereksiz subquery, view ve DISTINCT kullanımı
- OR yerine UNION
- EXISTS vs IN vs JOIN farkları

#### 💻 Uygulama
- Aynı sorgunun farklı varyasyonları ile performans analizi
- Execution Plan karşılaştırması: EXISTS vs IN vs JOIN

---

## 🗓️ 2. Gün – İndeksler, Hintler, Join Stratejileri

### ⏰ Sabah Oturumu (09:30 – 12:30)

#### ⚙️ Konu 1: İndekslerin Performansa Etkisi
- B-Tree vs Bitmap Index
- Composite, Unique, Function-Based Index
- İndeksin kullanılmama nedenleri:
  - Yanlış sıralama
  - Düşük selectivity
  - NULL değer dağılımı
  - Yanlış bind kullanımı

---

> 📌 Devam edecek:  
> 2. Gün Öğleden Sonra, 3. Gün, Case Study, SQL Script, PDF ve Sunum içerikleri için diğer dosyalara göz atabilirsiniz.


---

### ⏰ 2. Gün – Öğleden Sonra Oturumu (13:30 – 17:00)

#### 🔄 Konu 2: Hint Kullanımı ve Join Stratejileri
- Oracle Hint kavramı: /*+ HINT */
- INDEX, FULL, NO_INDEX, PARALLEL, USE_HASH, USE_NL gibi yaygın hint’ler
- Join türleri:
  - Nested Loop Join
  - Hash Join
  - Merge Join
- Join sırası (Join Order) ve LEADING hint ile kontrolü

#### 🔍 Konu 3: View ve Materialized View Kullanımı
- Inline view vs standard view
- View'ların execution plan'a etkisi
- Materialized View ve Query Rewrite avantajı

#### 💻 Uygulama
- JOIN türleri ile performans karşılaştırması
- Hint’li ve hint’siz sorguların analiz edilmesi
- View kullanımı ile tuning örnekleri

---

## 🗓️ 3. Gün – Performans Problemleri ve Gerçek Senaryolar

### ⏰ Sabah Oturumu (09:30 – 12:30)

#### 🧪 Konu 1: Performans Sorunlarının Tespiti
- v$sql, v$session, v$sqlarea ile yavaş sorgu analizi
- AWR (Automatic Workload Repository) raporları
- ASH (Active Session History) ile canlı sorgu izleme
- SQL Tuning Advisor & SQL Access Advisor

#### 🔐 Konu 2: Bind Variable Kullanımı
- Bind variable nedir, neden kullanılır?
- Literal vs Bind farkı ve Hard Parse etkisi
- Bind Peeking problemi
- CURSOR_SHARING ayarlarının etkisi

#### 💻 Uygulama
- En çok CPU tüketen sorguların tespiti
- Bind variable ile yeniden yazım ve performans farkı

---

### ⏰ Öğleden Sonra Oturumu (13:30 – 17:00)

#### 🧱 Konu 3: Büyük Veri ve Paralel İşleme
- Partitioning nedir, ne zaman kullanılır?
  - Range, List, Hash Partition türleri
- Partition Pruning
- Parallel Query yapısı ve avantajları

#### 🎯 Konu 4: Gerçek Senaryo Analizi
- Bir iş zekası raporunun yavaş çalışmasının analizi
- Execution plan ile darboğaz tespiti
- İndeks ekleme, sorgu yeniden yazımı ve istatistik güncellemesi ile iyileştirme

#### 💻 Uygulama
- Gerçek vakaya dayalı uçtan uca tuning çalışması

---

> ✅ Eğitimle birlikte sunulan destekleyici materyaller:
> - SQL script paketleri
> - Katılımcı PDF el kitabı
> - PowerPoint sunum dosyası
> - Uygulama senaryoları ve çözüm anahtarı

