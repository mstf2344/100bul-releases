# 100bul — Yüz Tanıma ve Kümeleme Uygulaması (Kurulum Dosyaları)

Bu depo, **100bul** uygulamasının güncel kurulum paketlerini, sürüm notlarını (Releases) ve kullanıcı kılavuzunu barındırmaktadır. 

> [!NOTE]
> Uygulamanın kaynak kodları güvenlik ve gizlilik gerekçesiyle özel (private) bir depoda tutulmaktadır. Bu depo, yalnızca son kullanıcıların uygulamayı indirebilmesi ve güncellemeleri takip edebilmesi için genel (public) olarak yayınlanmıştır.

---

## ⚡ Hangi Paketi İndirmeliyim?

Uygulamanın çalışacağı bilgisayarın donanım özelliklerine göre en uygun paketi indirmelisiniz:

| Varyant | Hedef Sistemler | Sistem Tespiti Nasıl Yapılır? | Tarama Hızı (Örn. 3000 Fotoğraf) |
| :--- | :--- | :--- | :--- |
| **100bul-CUDA** | NVIDIA Ekran Kartlı PC'ler | Başlat → `cmd` → `nvidia-smi` yazıldığında tablo çıkıyorsa | **~2.5 - 4 Dakika** (Yüksek Hassasiyet) |
| **100bul-DML** | AMD / Intel GPU veya Ekran Kartsız PC'ler | `nvidia-smi` komutu hata veriyorsa veya çalışmıyorsa | **~10 - 30 Dakika** (DirectML veya Otomatik CPU) |

> [!TIP]
> Emin değilseniz **100bul-DML** paketini indirin. Bu paket her bilgisayarda (ekran kartı olmasa dahi CPU moduna geçerek) sorunsuz çalışır.

---

## 📥 İndirme ve Kurulum

En güncel sürümleri indirmek için [Releases (Sürümler)](https://github.com/mstf2344/100bul-releases/releases) sayfasına gidin.

### Adım Adım Kurulum:
1. Bilgisayarınıza uygun olan `.exe` dosyasını (`100bul-X.X.X-nvidia-kurulum.exe` or `100bul-X.X.X-standart-kurulum.exe`) indirin.
2. İndirilen kurulum dosyasını çalıştırın. 
   - Uygulama, yönetici izni (admin) gerektirmeden kullanıcı klasörüne (`AppData\Local\100bul`) kurulacaktır.
3. Kurulum tamamlandığında masaüstünde oluşan **100bul** kısayoluna çift tıklayarak uygulamayı başlatın.

### Aktivasyon (İlk Kullanım):
* Uygulama ilk kez açıldığında sizden bir aktivasyon kodu isteyecektir.
* Size iletilen lisans anahtarını girerek cihazınızı kaydedin.
* Lisans anahtarı başarıyla doğrulandıktan sonra sol panelden tarama ayarlarını yapıp taramaya başlayabilirsiniz.

---

## 🛠️ Temel Özellikler

* **Yapay Zeka Destekli Yüz Tanıma:** En güncel derin öğrenme modelleri (InsightFace) kullanılarak fotoğraflardaki yüzleri yüksek doğruluk oranıyla tespit eder.
* **Gelişmiş Kümeleme:** Belirlenen kişileri fotoğraf havuzunuzda arar ve eşleşen yüzleri otomatik olarak gruplandırır.
* **Supabase / Neon Entegrasyonu:** Taramalar sonrasında verileri güvenli bulut veritabanına aktarır.
* **Yerel Veri Saklama:** Taranan klasörlerdeki veriler `faces.sqlite` dosyasında saklanır, böylece tekrar taramaya gerek kalmaz.

---

## 🔒 Güvenlik ve Gizlilik

* Uygulama, fotoğraflarınızın orijinallerini hiçbir bulut sunucusuna yüklemez. Tüm yüz analizi ve eşleşme işlemleri **tamamen yerel (local) olarak bilgisayarınızda gerçekleşir**.
* Yalnızca tarama istatistikleri ve aktivasyon durumları analiz için güvenli sunuculara (Neon veritabanı) iletilir.
