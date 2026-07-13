# Şifre Cebi — Mobil (PWA) Kurulum

Bu klasördeki 6 dosya, telefona kurulabilen web uygulaması (PWA) sürümüdür.
iOS ve Android'de ücretsiz çalışır. Kasa formatı PC sürümüyle birebir uyumludur.

## 1) Hemen telefonda denemek (yayınlamadan)

PC ve telefon aynı Wi-Fi'dayken, bu klasörde:

```
python -m http.server 8000
```

Sonra telefonun tarayıcısından `http://<PC'nin-IP-adresi>:8000` aç
(PC'nin IP'sini görmek için: `ipconfig` → "IPv4 Address").

Not: Bu yöntem deneme içindir; "ana ekrana kurma" ve çevrimdışı çalışma
için HTTPS gerekir (aşağıdaki adım).

## 2) Kalıcı ve ücretsiz yayınlamak (GitHub Pages)

1. github.com'da ücretsiz hesap aç.
2. "New repository" → isim: `sifrecebi` → Public → Create.
3. "uploading an existing file" bağlantısıyla bu klasördeki 6 dosyayı yükle
   (index.html, manifest.webmanifest, sw.js, icon-192.png, icon-512.png, icon-180.png).
4. Repo → Settings → Pages → Source: "Deploy from a branch" → Branch: `main` → Save.
5. Birkaç dakika sonra adresin hazır: `https://KULLANICIADIN.github.io/sifrecebi/`

Not: Repoda sadece uygulama kodu olur — şifrelerin ASLA repoya gitmez,
tamamen telefonun kendi hafızasında şifreli durur.

## 3) Telefona kurma

- **iPhone (iOS):** Safari ile adresi aç → Paylaş (kare+ok) → "Ana Ekrana Ekle".
- **Android:** Chrome ile adresi aç → ⋮ menü → "Ana ekrana ekle" / "Uygulamayı yükle".

Artık ana ekranda normal bir uygulama gibi açılır, internet olmadan da çalışır.

## 4) PC'deki kasayı telefona taşıma

1. PC'de kasa dosyan: `%APPDATA%\SifreCebi\vault.dat`
   (dosya şifrelidir, ana şifren olmadan açılamaz — güvenle taşınabilir)
2. Dosyayı telefona gönder (mail, Drive, USB...).
3. Telefonda uygulamayı aç → ilk ekranda veya ⋮ menüden "Kasa Dosyası İçe Aktar".
4. Ana şifrenle aç.

Telefonda yaptığın değişiklikleri PC'ye taşımak için: ⋮ menü →
"Kasayı Dışa Aktar (vault.dat)" → dosyayı PC'de `%APPDATA%\SifreCebi\vault.dat`
üzerine kopyala.

## Bilinmesi gerekenler

- Veriler sadece telefonda, şifrelenmiş olarak saklanır; hiçbir sunucuya gitmez.
- Otomatik senkronizasyon yoktur; iki cihaz arasında taşıma dışa/içe aktarma iledir.
- Mail ile kurtarma kodu gönderme özelliği mobilde yok (PC sürümünde var);
  kurtarma kodu ekranda bir kez gösterilir — mutlaka not al.
- Ara sıra "Kasayı Dışa Aktar" ile yedek almak iyi bir alışkanlıktır
  (telefon kaybolursa/temizlenirse tek kopya kaybolmasın).
