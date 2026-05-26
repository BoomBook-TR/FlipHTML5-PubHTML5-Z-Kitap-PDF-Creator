# 📖 FlipHTML5, PubHTML5 & Z-Kitap PDF Creator

Bu araç; **FlipHTML5**, **PubHTML5** ve çeşitli yayıncıların (Ata E-Kitap, Aydın Dijital vb.) **Z-Kitap** altyapılarında bulunan dijital materyalleri, ders kitaplarını ve dergileri tamamen yasal sınırlar dahilinde kendi bilgisayarınıza yüksek kaliteli **PDF** olarak kaydetmenizi sağlayan akıllı bir otomasyon scriptidir.

Arka planda **Batch**, **PowerShell** ve **ImageMagick** güçlerini birleştirerek çalışır. İndirme ve dönüşüm süreçlerini tamamen optimize ederek sistem kaynaklarınızı en verimli şekilde kullanır.

> 🚫 **CRACK / ILLEGAL METOTLAR İÇERMEZ!**
> Bu script, tarayıcınızın zaten önbelleğe aldığı veya herkese açık olarak paylaşılan görsel dosyalarını (`.jpg`, `.png`, `.webp`) sizin adınıza sırayla indiren ve bunları birleştiren şeffaf bir otomasyon aracıdır.

---

## ✨ Öne Çıkan Özellikler

* **Çift Yönlü Akıllı Ayrıştırma (Regex):** FlipHTML5 ve PubHTML5 linklerindeki şifreli/karmaşık dosya adlarını (`config.js`) otomatik olarak okur ve orijinal yüksek kaliteli görsel yollarını çözer.
* **🧠 Donanım Tabanlı Akıllı Optimizasyon (RAM Guard):** Sisteminizdeki RAM miktarını (8GB, 16GB, 32GB, 64GB+) otomatik olarak algılar. ImageMagick'in bilgisayarınızı dondurmaması için RAM, işlemci çekirdeği ve sıkıştırma kalitesini donanımınıza göre dinamik olarak ayarlar.
* **🧼 Gelişmiş Karakter Temizliği:** PDF çıktısı alırken Türkçe karakterleri (`ç, ğ, ı, ö, ş, ü`) ve geçersiz işaretleri otomatik olarak temizleyerek dosya sistemi hatalarını önler.
* **🔐 Şifreli (Encrypted) Sayfa Desteği:** `fliphtml5_pages` verisi şifrelenmiş olan zorlu kitaplarda, script otomatik olarak geçici bir Chrome konsol kodu (`console.js.txt`) üretir. Bu kod sayesinde şifreyi tarayıcıda çözüp listeyi tek tıkla scripte aktarabilirsiniz.
* **⚙️ Otomatik ImageMagick Entegrasyonu:** Sistemde ImageMagick kurulu değilse, resmi arşivden en güncel uyumlu sürümü (`Q16-HDRI-x64-dll`) otomatik indirir, kurar ve ortam değişkenlerine (PATH) kalıcı olarak işler.
* **💾 Akıllı Disk Seçimi (Temp Drive):** C: sürücünüzün dolmaması veya yavaşlamaması için sistemdeki diğer yerel diskleri (D: vb.) otomatik tarar ve yüksek boyutlu geçici dosyaları (`IMTemp`) orada işler.

---

## 🚀 Kullanım Seçenekleri ve Menü Yapısı

Scripti yönetici olarak çalıştırdığınızda sizi oldukça işlevsel bir interaktif menü karşılar:

```text
===========================================================
                 HTML5 to PDF Creator - MENU
===========================================================
 1. FlipHTML5 - PubHTML5 PDF Creator
 2. Manuel (Otomatik URL Ayrıştırma) Z-Kitap PDF Creator
 3. Manuel Z-Kitap PDF Creator
 4. Images Klasöründekileri PDF yap
 5. IMAGEMAGICK Kurulum
 6. Çıkış
===========================================================
