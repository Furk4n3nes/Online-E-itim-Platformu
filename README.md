STEAM Akademi – Öğretmen Paneli ve İçerik Yönetimi
https://steam-akademi.com/
Modern bir öğretmen paneli, video içerik yönetimi ve ders planı paylaşım/değerlendirme özellikleri sunan PHP (PDO) + MySQL tabanlı bir web uygulaması.

## Özellikler
- Öğretmen girişi ve oturum yönetimi
- Öğretmen paneli (dashboard) istatistikleri (toplam video, izlenme, beğeni)
- Video yönetimi (yükleme, listeleme, durum bildirimleri)
- Ders planı yönetimi: ekleme, düzenleme, silme (sadece plan sahibi)
- Admin onayı ile aktif etme akışı
- Diğer öğretmenlerin planlarını görüntüleme ve 5 yıldız üzerinden değerlendirme
- Dinamik ünite seçimi (derse göre ünite listesi)
- Duyarlı arayüz (Bootstrap 5, Font Awesome)

## Dizim (Örnek)

  ogretmen/
    dashboard.php
    ders_plan_sil.php
    ders_plan_ekle.php
    update_plan.php
    get-unites.php
    ders_plan_degerlendir.php
    ders_plan_degerlendirme_kontrol.php
  config/
    db.php
  assets/
    images/logo.png

## Gereksinimler
- PHP 8.x (PDO etkin)
- MySQL 5.7/8.x
- Apache/Nginx (URL’ler doğrudan PHP dosyalarına yönlenebilir)

## Kurulum
1. Veritabanını oluşturun ve tabloları içe aktarın (ör: `Ogretmen`, `Video`, `Izlenme`, `Begenme`, `DersPlan`, `Ders`, `Sinif`, `Unite`).
2. Veritabanı bağlantısını yapılandırın: `new/config/db.php` içinde sunucu, veritabanı adı, kullanıcı, parola bilgilerini güncelleyin.
3. Sunucunuzu projenin kök klasörüne yönlendirin (ör. `new/`).
4. Tarayıcıdan giriş sayfasına gidin ve bir öğretmen hesabı ile giriş yapın.
5. Yayın haklarından dolayı web sitesinin kodlarını paylaşamıyorum.

## Önemli Dosyalar
- `/ogretmen/dashboard.php`: Öğretmen paneli, istatistikler ve ders planı listeleri
- `/ogretmen/ders_plan_sil.php`: Plan sahibinin planını silmesi için JSON endpoint 
- `/ogretmen/ders_plan_ekle.php`: Yeni ders planı ekleme (POST)
- `/ogretmen/update_plan.php`: Ders planını güncelleme (POST)
- `/ogretmen/get-unites.php`: Seçilen derse göre ünite listesini döndürür (GET, JSON)
- `/ogretmen/ders_plan_degerlendir.php`: 1-5 arası puan verme (POST)
- `/ogretmen/ders_plan_degerlendirme_kontrol.php`: Mevcut puanı sorgulama (GET, JSON)
- `/config/db.php`: PDO ile veritabanı bağlantısı

## Güvenlik Notları
- Tüm kritik sayfalarda oturum ve kullanıcı tipi kontrolü yapılır.
- Silme/güncelleme işlemlerinde sahiplik doğrulaması zorunludur (`PlanID` + `OgretmenID`).
- SQL işlemleri hazırlıklı ifadeler (prepared statements) ile yapılır.

## Kullanım
- Giriş yaptıktan sonra `dashboard.php` üzerinden:
  - Kendi planlarınızı listeleyin, görüntüleyin, güncelleyin veya silin.
  - Diğer öğretmenlerin planlarını inceleyin ve puanlayın.
  - Yeni plan eklerken Drive paylaşım bağlantısını eklemeyi unutmayın.



