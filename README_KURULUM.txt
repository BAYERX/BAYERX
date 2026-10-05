BAYERX — WEB / TELEFON KURULUM
================================

Uygulama tamamen statiktir (sunucu tarafı kod yok). Tüm dosyaları aynı
klasöre koyup bir web sunucusundan yayınlaman yeterli.

PAKET İÇERİĞİ (hepsi aynı klasörde dursun):
  index.html          -> uygulamanın kendisi (BayerX.html ile aynı)
  kur.js              -> TCMB döviz satış kuru
  ihale_config.js     -> aranacak kelimeler + iller
  ihale_veri.js       -> bulunan ihaleler
  ihale_log.js        -> arama günlüğü
  manifest.json       -> "Ana ekrana ekle" (PWA) ayarı
  icon-192.png / icon-512.png -> uygulama ikonu

GİRİŞ ŞİFRESİ: index.html içindeki APP_CONFIG.password (varsayılan BayerX2026)

---------------------------------------------------
A) GITHUB PAGES (ücretsiz, en kolay)
---------------------------------------------------
1. github.com > New repository > ad: bayerx > Public > Create.
2. "Add file" > "Upload files" ile paketteki TÜM dosyaları yükle,
   Commit.  (Ana dosya index.html olduğu için kök adresten açılır.)
3. Settings > Pages > Build and deployment:
   Source: "Deploy from a branch", Branch: main / (root) > Save.
4. 1-2 dk sonra adres: https://<kullanici-adi>.github.io/bayerx/
   Bu linki telefonda aç.

NOT: GitHub Pages herkese açıktır; fiyat listesi ve giriş şifresi
kaynak kodda görünür olur (şifre gerçek koruma SAĞLAMAZ). Gizli fiyatlar
için erişim korumalı bir host (örn. Netlify/Cloudflare + parola) ya da
üyelik girişli sunucu aşaması önerilir.

---------------------------------------------------
B) KENDİ SUNUCUN / HOSTING (cPanel, Nginx, Apache...)
---------------------------------------------------
- Dosyaları public_html (veya bir alt klasör) içine yükle.
- https://alanadin.com/  ya da  https://alanadin.com/bayerx/ aç.
- HTTPS önerilir (kur/ihale verileri ve SheetJS internetten çekilir).

---------------------------------------------------
TELEFONDA KULLANIM
---------------------------------------------------
- Linki telefon tarayıcısında aç, giriş yap.
- iPhone: Paylaş > "Ana Ekrana Ekle".  Android: menü > "Ana ekrana ekle".
  Böylece BayerX ikonu ile tam ekran, uygulama gibi açılır.

---------------------------------------------------
GÜNCELLEME
---------------------------------------------------
- Fiyat listesi: index.html'i aç, Excel yükle (masaüstü/tarayıcı).
  Sunucudaki herkeste aynı görünmesi istenirse sunucu aşamasında
  veriyi ortak dosyaya/veritabanına taşırız.
- İhale verisi: ihale_veri.js / ihale_log.js dosyalarını güncelleyip
  tekrar yükle (Claude tarama sonrası bunları üretir).
- Kur: kur.js güncellenir; site açılışta canlı TCMB'yi de dener.

İnternet gerekir: Excel okuma kütüphanesi (SheetJS) ve kur/ihale
verileri çevrimiçi gelir.
