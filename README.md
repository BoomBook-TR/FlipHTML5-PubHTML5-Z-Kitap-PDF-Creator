# 📖 FlipHTML5, PubHTML5 Z-Kitap PDF Creator

Bu araç; **FlipHTML5**, **PubHTML5** ve çeşitli yayıncıların (Ata E-Kitap, Aydın Dijital vb.) **Z-Kitap** altyapılarında bulunan dijital materyalleri, ders kitaplarını ve dergileri tamamen yasal sınırlar dahilinde kendi bilgisayarınıza yüksek kaliteli **PDF** olarak kaydetmenizi sağlayan akıllı bir otomasyon scriptidir.

Arka planda **Batch**, **PowerShell**, **ImageMagick** ve isteğe bağlı **Ghostscript** güçlerini birleştirerek çalışır. İndirme ve dönüşüm süreçlerini tamamen optimize ederek sistem kaynaklarınızı en verimli şekilde kullanır.

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

## 🗜️ Devasa PDF Boyutlarını Sıkıştırma ve Optimizasyon Kılavuzu

Yüzlerce yüksek çözünürlüklü görsel birleştirildiğinde oluşan PDF dosyalarının boyutu bazen çok yüksek (200MB - 500MB+) olabilir. Dosya boyutunu düşürmek, internete yüklemeyi kolaylaştırmak ve tablet/mobil cihazlarda donmadan akıcı açılmasını sağlamak için **iki farklı yöntem** kullanabilirsiniz:

### 🔹 Yöntem 1: ImageMagick Sıkıştırma Ayarı (En Pratik Yol)
Script zaten ImageMagick kullandığı için harici bir şey kurmadan doğrudan kod üzerinden optimizasyon yapabilirsiniz.
1. `script.bat` dosyasını Notepad++ veya herhangi bir metin editörüyle açın.
2. Aşağıdaki satırı bulun:
   ```batch
   magick @"temp\filelist.txt" "pdf\%PDFNAME%"
3. Bu satırı şu şekilde güncelleyin (Script içinde RAM ayarlarına göre iki farklı noktada yer alabilir, uygun yere ekleyin):
    ```batch
    magick @"temp\filelist.txt" -quality 85 -compress jpeg "pdf\%PDFNAME%"
    ```
-quality 85: JPEG kalite seviyesini %85'e çeker. Göze hitap eden kaliteden ödün vermeden dosya boyutunu %60+ oranında küçültür.

-compress jpeg: Her bir sayfa görselini PDF içinde JPEG formatıyla akıllıca sıkıştırır.

### 🔹 Yöntem 2: Ghostscript Entegrasyonu (Profesyonel E-Kitap Standardı)

PDF üretildikten sonra tam kurumsal sıkıştırma (`/ebook` kalitesi) uygulamak isterseniz Ghostscript kullanabilirsiniz.

1. Bilgisayarınıza Ghostscript kurun:
   * **Ghostscript İndirme Adresi:** [ArtifexSoftware / GhostPDL](https://github.com/ArtifexSoftware/ghostpdl-downloads/) veya [Ghostscript Resmi İndirme Sayfası](https://ghostscript.com/releases/gsdnld.html)
2. Ghostscript'in `gswin64c.exe` aracının çalışabilmesi için kurulum dizinini (Örn: `C:\Program Files\gs\gs10.x.x\bin`) sisteminizin **Ortam Değişkenlerine (PATH)** ekleyin.
3. Script içindeki şu satırların önündeki yorum işaretlerini (`::`) kaldırarak aktifleştirin:

```batch
gswin64c -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/ebook ^
  -dNOPAUSE -dQUIET -dBATCH ^
  -sOutputFile="pdf\%BASE_NO_EXT%_compressed.pdf" "pdf\%PDFNAME%
```

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
```

## 🎯 Modların Kısa Kullanım Kılavuzu:

Seçenek 1 (FlipHTML5/PubHTML5): Kitabın normal tarayıcı linkini yapıştırmanız yeterlidir. Sistem arka planda config.js dosyasını çeker ve sayfaları kusursuz bir şekilde indirip PDF yapar.

Seçenek 2 (Otomatik Z-Kitap): F12 Ağ (Network) sekmesinden bulduğunuz herhangi bir sayfa görselinin linkini (örn: https://.../Page1.png) doğrudan yapıştırın. Script; baseURL, format ve suffix değerlerini kendi ayrıştırır, sizden sadece sayfa sayısını ister.

Seçenek 3 (Manuel Bölmeli Z-Kitap): Sayfa numarasının sağında ve solunda karmaşık parametreler olan linkler için manuel giriş modu sunar.

Seçenek 4 (Yerel Birleştirme): Elinizde halihazırda bulunan resimleri images/ klasörüne attıktan sonra sayısal sıralamaya göre (1, 2, 3...) tek tıkla PDF'e dönüştürür.

## 📑 Desteklenen URL Yapılarına Örnekler
Script, aşağıdaki tipteki tüm açık veya özel yapılandırılmış link mimarilerini desteklemektedir:

https://fliphtml5.com/[kullanici]/[token]/

https://online.fliphtml5.com/[kullanici]/[token]/

https://pubhtml5.com/[kullanici]/[token]/

https://.../files/mobile/1.jpg?[parametre]

https://.../Media/UserData/bookimages/[guid]/Page1.png
