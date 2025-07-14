# SQL Server Sistem Veritabanları

SQL Server, düzgün çalışabilmesi ve kullanıcı veritabanlarının sağlıklı yönetilebilmesi için bazı temel sistem veritabanlarına ihtiyaç duyar. SQL Server kurulumu sırasında otomatik olarak oluşturulan bu veritabanları, genellikle 5 ana başlık altında incelenir:

---

## 1. Master Veritabanı
**SQL Server'ın beyni** olarak kabul edilir. Bu veritabanı olmadan SQL Server çalışamaz.

- **Görevi:** Sunucunun yapılandırma ayarlarını, login bilgilerini, veritabanlarının konumlarını ve başlatma seçeneklerini saklar.
- **İçeriği:** Sunucu düzeyindeki tüm sistem bilgileri.
- **Önemi:** Bozulması durumunda SQL Server başlatılamaz. Bu nedenle mutlaka düzenli yedeklenmelidir.

---

## 2. Model Veritabanı
**Yeni veritabanları için şablon** görevi görür.

- **Görevi:** Oluşturulan her yeni veritabanı, model veritabanının bir kopyası olarak başlatılır.
- **İçeriği:** Varsayılan tablolar, görünümler, prosedürler gibi nesneler.
- **Önemi:** Tüm yeni veritabanlarda varsayılan olarak yer almasını istediğiniz yapıların burada tanımlanması mümkündür.

---

## 3. MSDB Veritabanı
**SQL Server Agent işlemleri ve otomasyon süreçleri** için kullanılır.

- **Görevi:** Zamanlanmış işler (jobs), uyarılar, operatörler ve SSIS paket geçmişi gibi yönetimsel bilgileri saklar.
- **İçeriği:** Yedekleme geçmişi, çoğaltma bilgileri, bakım planları.
- **Önemi:** SQL Server Agent tarafından kullanılan tüm otomasyon işlemleri burada tutulur. Kayıplar önemli veri ve görev kayıplarına yol açabilir.

---

## 4. TempDB Veritabanı
**Geçici işlemler ve veri** için kullanılan çalışma alanıdır.

- **Görevi:** Geçici tablolar, dahili sorgu işlemleri ve sıralama verileri gibi geçici içerikleri saklar.
- **Özellikleri:** SQL Server her yeniden başlatıldığında TempDB sıfırdan oluşturulur. İçeriği kalıcı değildir.
- **Önemi:** Performans için kritik öneme sahiptir. Özellikle sorguların yoğun kullanıldığı sistemlerde doğru yapılandırılması gerekir.

---

## 5. Resource Veritabanı (`mssqlsystemresource`)
**SQL Server'ın dahili sistem nesnelerini** barındıran özel bir veritabanıdır.

- **Görevi:** Tüm sistem tabloları, görünümler ve prosedürler gibi iç nesneleri saklar.
- **Özellikleri:** Kullanıcı tarafından erişilemez. `sys` şeması altında mantıksal olarak görünür.
- **Önemi:** SQL Server yükseltmeleri sırasında sistem nesnelerinin merkezi olarak yönetilebilmesini sağlar.

---

🚨 Sistem veritabanlarının her biri, SQL Server altyapısının sağlıklı ve güvenli çalışması için temel taşlardır. Yedekleme, performans ve güvenlik açısından bu veritabanlarının yapısını ve rollerini iyi anlamak, sağlam bir SQL Server yönetimi için kritik öneme sahiptir.

