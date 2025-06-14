
---

## 🔧 A. Gvenzl Oracle XE Docker Container Kurulumu

### 1. Docker Kurulu mu Kontrol Et

Terminalde çalıştır:

```bash
docker --version
```

Eğer yoksa [https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop) adresinden kur.

---

### 2. Docker Compose Dosyasını Oluştur

📄 `docker-compose.yml` adlı bir dosya oluştur ve içine şunu yapıştır:

```yaml
version: '3.8'

services:
  oracle-xe:
    image: gvenzl/oracle-xe:21.3.0
    container_name: oracle-xe
    ports:
      - "1521:1521"
    environment:
      ORACLE_PASSWORD: Oracle123
    volumes:
      - oracle-data:/opt/oracle/oradata
    restart: unless-stopped

volumes:
  oracle-data:
```

---

### 3. Container’ı Başlat

Aynı dizinde terminal aç ve şunu çalıştır:

```bash
docker-compose up -d
```

📌 Komut sonrası yaklaşık 30–60 saniyede veritabanı hazır olur. Durumu kontrol et:

```bash
docker ps
```

---

## 🔌 B. Oracle XE’ye Bağlanma

### Yöntem 1: **SQL Developer (GUI) ile Bağlantı**

| Parametre | Değer       |
| --------- | ----------- |
| Host      | `localhost` |
| Port      | `1521`      |
| Kullanıcı | `system`    |
| Şifre     | `Oracle123` |
| SID       | `XE`        |

> ✅ *“Test” tuşuna bastığında başarılı bağlantıyı göstermelidir.*

---

### Yöntem 2: **Komut Satırından Bağlantı (`sqlplus`)**

Önce konteyner içine gir:

```bash
docker exec -it oracle-xe bash
```

Sonra bağlan:

```bash
sqlplus system/Oracle123@XE
```

Komut sonrası SQL prompt’u açılır:

```sql
```

---

## ✅ C. İlk Ayarlar ve Örnek Kullanım

### 1. Yeni kullanıcı oluştur:

```sql
CREATE USER demo IDENTIFIED BY demo123;
GRANT CONNECT, RESOURCE TO demo;
```

### 2. Örnek tablo:

```sql
CREATE TABLE demo.test_table (
  id NUMBER,
  name VARCHAR2(50)
);

INSERT INTO demo.test_table VALUES (1, 'Veri');
COMMIT;
```

---
