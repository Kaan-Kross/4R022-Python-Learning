# 4R022 Python Learning

**4R022 Python Learning** içeriğini gerçek bir e-kitap gibi okumanı
sağlayan, Python (PyQt6) ile yazılmış masaüstü uygulaması.

Marka: **4R022** · Yazar: **Kaan Kross**

---

## Özellikler

- **5 dilin tamamı hazır kurulu**: `content/` klasöründe TR, ENG, RU,
  FR, DE paketlerinin tamamı bulunur; araç çubuğundaki **🌐 Dil
  Değiştir** butonuyla istediğin an değiştirebilirsin.
- **Sorunsuz sayfa geçişleri**: Her klasördeki README/bölüm
  dosyalarındaki iç bağlantılar (`../Python-Orta-Kademe-TR/README.md`
  gibi) yakalanıp uygulama içinde, harici tarayıcıya çıkmadan,
  yumuşak bir **solma (fade) animasyonuyla** açılır.
- **İçindekiler paneli**: Sol tarafta, tüm bölüm/alt bölüm yapısını
  gösteren katlanabilir bir ağaç; ☰ butonuyla aç/kapa.
- **Yakınlaştırma**: Araç çubuğundaki `－` / `＋` ile veya yüzde
  etiketine tıklayarak sıfırlama.
- **Kalem takımı**: ✏ Kalem, 🖍 Vurgulama kalemi, 🩶 Şeffaf kalem,
  🧹 Silgi, 🗒 Yapışkan not — hepsi sayfa içeriğinin **üzerine**,
  sayfayla birlikte kayan bir katmana çizilir; renk seçimi 🎨
  butonundan yapılır. 🗑 ile o sayfanın tüm not/çizimlerini temizle.
- **Kaldığın yerden devam et**: Hangi dilde, hangi sayfada, sayfanın
  neresinde kaldığın (kaydırma oranı) sürekli ve otomatik olarak
  kaydedilir; uygulamayı kapatıp tekrar açtığında tam kaldığın yerden
  devam eder.
- **Ekran boyutuna otomatik uyum**: Pencere, birincil ekranın
  kullanılabilir alanına göre boyutlanır; yazı tipi boyutu ekranın
  DPI değerine göre ayarlanır.
- **Animasyonlu açılış ekranı**: 4R022 logosu yumuşak bir belirme
  animasyonuyla açılış ekranında gösterilir.
- **Sol üstte marka vurgusu**: Her ekranda "4R022 · Kaan Kross"
  ibaresi ve logo sabit olarak görünür.

## v1.3 Değişiklikleri (Performans)

- **Boşta CPU ≈ 0:** Sürekli çalışan sorgu zamanlayıcısı kaldırıldı. Sayfa yalnızca bir şey
  değişince (çizim, not, kaydırma bitişi) haber veriyor; 15 sn'lik seyrek güvenlik ağı
  yalnızca pencere etkinken çalışıyor, simge durumundayken hiçbir şey yapmıyor.
- Çizim katmanı çizim/araç yokken tamamen kapalı; kaydırmada boşuna yeniden çizim yok.
- Çizim noktaları sadeleştirildi (daha küçük kayıt, daha az iş).
- Kayıt dosyası küçük/sıkıştırılmış JSON; değişiklik yoksa diske yazılmıyor, yedek oturumda bir kez.
- Chromium: GPU ile çizim, WebGL/eklenti/DNS ön-yükleme/ağ arka plan işleri kapalı, disk önbelleği yok.
- Açılış: `markdown` kütüphanesi ilk sayfada yükleniyor, CSS/JS önbellekte, açılış ekranı
  daha hafif (QGraphicsEffect yerine pencere saydamlığı) ve kısaltıldı.
- Ölçüm (bu ortamda): içindekiler ağacı 16 ms, önbellekli sayfa üretimi 0,2 ms.

## v1.2 Değişiklikleri

- ENG ve TR kapak sayfasında `# başlık` / `**kalın**` işaretleri ham yazı görünüyordu
  (`<div align="center">` içindeki markdown işlenmiyordu). Tüm kitapta düzeltildi;
  `<details>` (cevap göster) bloklarındaki kod blokları da artık düzgün görünür.
- Tablolar dar ekranda taşmaz; kaydırılabilir.
- Dil değiştirince aynı bölüm/sayfaya geçilir (eskiden ilk sayfaya dönüyordu).
- Klasör bağlantıları ilgili README'yi açar; yerel bağlantılar sayfayı boşaltmaz.
- Kısayollar: Ctrl+S kaydet, Alt+←/→ sayfa, Ctrl+B içindekiler, Ctrl +/-/0 yakınlaştırma.
- Ekran değişse bile pencere ekran dışında açılmaz.

## v1.1 Değişiklikleri

- Dil paketi klasörleri artık anlamlı: `4R022 Python Learning TR / ENG / RU / DE / FR`.
  Dil seçim penceresinde Türkçe, English, Русский, Deutsch, Français adları görünür.
- İlk açılışta dil seçimi İngilizce sorulur; seçilen dile göre **tüm arayüz**
  (butonlar, ipuçları, onay pencereleri, not aracı, renk seçici) o dilde olur.
- Kalem artık sol menü açık/kapalı olsa da kaymaz (çizimler içerik kutusuna göre saklanır).
- Yapışkan not aracı düzeltildi; 💾 **Sayfayı kaydet** düğmesi eklendi.
- Çizimler sayfa yenilense / dil değişse / uygulama kapansa da silinmez
  (sayfadan çıkmadan ve kapanışta zorunlu kayıt).
- Scroll donması giderildi (dev canvas ve opaklık efekti kaldırıldı); genel optimizasyon yapıldı.
- Kurulum bitince `Book/4R022 Python Learning.exe` oluşur.

## Kurulum (Otomatik)

- **Windows:** `Build\Kurulum-Windows.bat` dosyasına çift tıkla.
- **Linux / macOS:** terminalde `bash Build/Kurulum-Linux-MacOS.sh` çalıştır.

Her iki betik de: Python'u kontrol eder → sanal ortam (`.venv`) oluşturur →
bağımlılıkları kurar → PyInstaller ile uygulamayı derler → proje klasöründe
**`Book/`** klasörü oluşturup içine **`4R022 Python Learning.exe`** koyar ve
başlatır. Sonraki çalıştırmalarda doğrudan başlatır. (Kayıtlar kullanıcı
veri klasöründe tutulur: Windows'ta `%APPDATA%\4R022\KitapSistemi`.)

## Elle Çalıştırma

```bash
pip install -r requirements.txt
python Main/main.py
```

> Not: `PyQt6-WebEngine` paketi Chromium tabanlı bir motor içerdiği
> için indirmesi büyüktür (yüzlerce MB); ilk kurulum biraz zaman
> alabilir.

## Klasör Yapısı

```
4R022-Kitap-Sistemi/
├── Main/
│   └── main.py                 → Giriş noktası, açılış ekranı
├── core/                       → Arayüzden bağımsız iş mantığı
│   ├── i18n.py               → 5 dilde tüm arayüz metinleri
│   ├── config.py               → Yollar, marka renkleri, ekran hesaplamaları
│   ├── content_loader.py       → Dil paketlerini keşfetme, İçindekiler ağacı
│   ├── markdown_renderer.py    → Markdown -> temalı HTML dönüşümü
│   ├── annotations.py          → Not/çizim veri modeli
│   └── state_manager.py        → Atomik JSON ile durum kaydı/yükleme
├── ui/                         → PyQt6 arayüz bileşenleri
│   ├── splash_screen.py        → Animasyonlu açılış ekranı
│   ├── main_window.py          → Ana pencere, marka şeridi, akış yönetimi
│   ├── book_view.py            → Sayfa görüntüleyici (QWebEngineView + köprü)
│   ├── toc_panel.py            → İçindekiler paneli
│   ├── toolbar_panel.py        → Araç çubuğu (gezinme, zoom, kalem takımı)
│   └── language_dialog.py      → Dil seçim penceresi
├── web/
│   └── bridge.js                → Canvas tabanlı not/çizim motoru + köprü
├── assets/
│   └── 4r022-logo.png
├── content/                     → 5 dilin tam içeriği (4R022 Python Learning TR/ENG/RU/DE/FR)
├── requirements.txt
├── LICENSE.txt
├── Build/
│   ├── build.spec               → PyInstaller derleme betiği
│   ├── Kurulum-Windows.bat      → Windows: otomatik kurulum + başlatma
│   └── Kurulum-Linux-MacOS.sh   → Linux/macOS: otomatik kurulum + başlatma
└── README.md
```

## Mimari Notlar

- **Neden `core/` + `ui/` ayrımı?** İş mantığı (içerik okuma, durum
  kaydetme, markdown dönüşümü) arayüzden tamamen bağımsızdır; bu
  sayede pencere hiç açılmadan da test edilebilir.
- **Neden QWebEngineView?** Kitap içeriğindeki tablolar, kod blokları
  ve `<details>` gibi ham HTML parçaları (bkz. Temel Eğitim
  bölümlerindeki katlanır ipucu kutuları) yalnızca gerçek bir
  tarayıcı motoruyla eksiksiz ve bozulmadan görüntülenebilir.
- **Not/çizim katmanı nasıl çalışıyor?** Her sayfaya, sayfayla
  birlikte kayan (position: absolute, sabit değil) tam boy bir
  `<canvas>` ve yapışkan not `<div>`'leri eklenir. Bu sayede
  kaydırma/yakınlaştırma sırasında çizimler içerikle birlikte hareket
  eder. Veri, JavaScript tarafından `QWebChannel` üzerinden Python'a
  iletilip `state_manager.py` aracılığıyla diske atomik olarak
  yazılır.
- **Atomik kayıt:** Durum dosyası önce `.tmp`'ye yazılır, eski dosya
  `.bak` olarak yedeklenir, sonra `.tmp` asıl dosyanın üzerine
  taşınır — yarım yazılmış/bozuk bir durum dosyası oluşamaz.

## Yeni Bir Dil Paketi Eklemek

`content/` klasörüne, mevcut 5 paketle **aynı iç yapıya** sahip
(Genel Bakış / Temel / Orta / Üst Düzey / Veri Kavramları / Modüller
/ Etik klasörleri, her birinde `README.md`) yeni bir klasör
kopyalaman yeterlidir — uygulama onu otomatik olarak dil listesinde
gösterir.

## PyInstaller ile Tek Dosya Uygulama Oluşturma

```bash
pip install pyinstaller
pyinstaller --noconfirm --distpath . --workpath build_tmp Build/build.spec
```

Çıktı `Book/4R022 Python Learning.exe` olarak oluşur. Windows'ta özel
bir uygulama simgesi istiyorsan `assets/4r022-logo.png` dosyasını
`.ico` formatına çevirip `Build/build.spec` içindeki `icon=` satırını
buna göre güncelle (PyInstaller'ın simge alanı en güvenilir şekilde
`.ico` uzantısıyla çalışır).

## Bilinen Sınırlamalar

- Not/çizim katmanı sayfa **yeniden boyutlandırıldığında** (pencere
  genişliği değiştiğinde) otomatik olarak yeniden ölçeklenmez; sayfa
  genişliği sabit kaldığı sürece (ki içerik `max-width: 880px` ile
  ortalanmıştır) bu bir sorun yaratmaz.
- Çok büyük ölçüde yakınlaştırma/uzaklaştırma yapıldığında mevcut
  çizimlerin konumu küçük bir sapma gösterebilir; bu durumda 🗑 ile
  o sayfanın çizimlerini temizleyip yeniden çizebilirsin.
