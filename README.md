# SQL Server Sistem Veritabanları

SQL Server'ın sağlıklı çalışabilmesi ve kullanıcı veritabanlarının doğru yönetilebilmesi için bazı temel sistem veritabanlarına ihtiyaç vardır.

🎯 **Sistem veritabanlarının her biri, SQL Server'ın güvenli ve kararlı çalışması için kritik yapı taşlarıdır.**  
Yedekleme, performans ve güvenlik açısından bu veritabanlarının rollerini iyi anlayabilen biri;  
sağlam ve sürdürülebilir bir SQL Server yönetimi sağlayabilir.

SQL Server kurulumu sırasında otomatik olarak oluşturulan bu veritabanları genellikle **5 ana başlık** altında incelenir:

---

## 1. Master Veritabanı  
**SQL Server'ın beyni** olarak kabul edilir. Bu veritabanı olmadan SQL Server çalışamaz.

- **Görevi:** Sunucu yapılandırmaları, login bilgileri, veritabanı konumları, başlatma seçenekleri.
- **İçeriği:** Sunucu düzeyindeki tüm sistem bilgileri.
- **Önemi:** Bozulması durumunda SQL Server başlatılamaz. Mutlaka düzenli olarak yedeklenmelidir.

---

## 2. Model Veritabanı  
**Yeni veritabanları için şablon** görevi görür.

- **Görevi:** Yeni veritabanları, model veritabanının bir kopyası olarak başlatılır.
- **İçeriği:** Varsayılan tablolar, görünümler, prosedürler vb.
- **Önemi:** Tüm yeni veritabanlarda ortak yapıların bulunmasını sağlar. Şablon olarak özelleştirilebilir.

---

## 3. MSDB Veritabanı  
**SQL Server Agent işlemleri ve otomasyon süreçleri** için kullanılır.

- **Görevi:** Zamanlanmış işler (jobs), uyarılar, operatörler, SSIS paket geçmişi gibi bilgileri saklar.
- **İçeriği:** Yedekleme geçmişi, çoğaltma verileri, bakım planları.
- **Önemi:** SQL Server Agent’ın işlediği tüm otomasyon burada saklanır. Bozulması görev kayıplarına neden olabilir.

---

## 4. TempDB Veritabanı  
**Geçici işlemler ve veriler** için kullanılan dinamik çalışma alanıdır.

- **Görevi:** Geçici tablolar, sorgu işlemleri ve sistem içi geçici veriler.
- **Özellikleri:** Her SQL Server yeniden başlatıldığında sıfırdan oluşturulur. Kalıcı veri içermez.
- **Önemi:** Performans açısından çok kritiktir. Yoğun sistemlerde dosya yapısı ve boyutu doğru yapılandırılmalıdır.

---

## 5. Resource Veritabanı (`mssqlsystemresource`)  
**Sistem nesnelerinin merkezi saklama alanıdır.**

- **Görevi:** Tüm sistem tabloları, görünümler ve prosedürler gibi iç nesneler burada saklanır.
- **Özellikleri:** Doğrudan erişilemez, ancak `sys` şeması altında mantıksal olarak görünür.
- **Önemi:** SQL Server güncellemeleri sırasında sistem nesnelerinin kolayca değiştirilmesini sağlar.

---

> 🚨 Bu temel sistem veritabanları, yalnızca SQL Server'ın değil; veriye dayalı her sistemin sürdürülebilirliği için kritik birer yapı taşıdır.


