# djpull kurulumu

djpull, Spotify ve YouTube playlist'lerini Soulseek'ten, mümkünse kayıpsız
(FLAC/WAV/AIFF) indirir. Takılan indirmeleri kendisi başka kaynağa taşır.

Gerekenler: Apple Silicon (M1 ve sonrası) bir Mac, macOS 12 ya da yenisi.

## 1. İndir ve kur

1. [Son sürümün sayfasından](../../releases/latest) `djpull_…_aarch64.dmg`
   dosyasını indir ve aç.
2. Açılan pencerede **djpull**'u **Applications** (Uygulamalar) klasörüne sürükle.

## 2. İlk açılış (sadece bir kez)

djpull Apple'a kayıtlı bir geliştirici tarafından imzalanmadığı için macOS ilk
açılışta engeller. Bu normal:

1. Uygulamalar'dan **djpull**'u aç. "Apple, djpull'un kötü amaçlı yazılım
   içermediğini doğrulayamadı" uyarısı çıkar. **Bitti**'ye bas.
   (**Çöp Sepetine Taşı**'ya basma.)
2. **Sistem Ayarları → Gizlilik ve Güvenlik**'i aç, sayfanın en altına in.
   "djpull engellendi" satırının yanındaki **Yine de Aç**'a bas, Mac şifreni gir.
3. djpull'u tekrar aç; son onayda yine **Yine de Aç** de.

Sonraki açılışlarda bu adımlar gelmez.

"djpull hasarlı, açılamıyor" dersen: dosya indirilirken bozulmuş ya da eski
bir sürümdür; yeniden indir. Sürmezse Terminal'de şunu çalıştır:

```
xattr -dr com.apple.quarantine /Applications/djpull.app
```

## 3. İzinler

- **Yerel ağ:** "djpull yerel ağınızdaki aygıtları bulmak istiyor" → **İzin Ver.**
  djpull modemine Soulseek portunu açtırmak için bunu kullanır.
- **Klasörler:** Müzik klasörüne erişim sorarsa izin ver.

## 4. İlk kurulum (djpull içinde)

1. **Soulseek hesabı:**
   - Hesabın varsa (SoulseekQt, Nicotine+) **Hesabım var** de, bilgilerini gir.
   - Yoksa **Yeni hesap**: bir kullanıcı adı ve şifre uydur, ilk girişte hesap
     açılır. **Şifre kurtarma yok, bir yere not al.**
   - Aynı hesabı djpull açıkken SoulseekQt/Nicotine+'ta da açma: Soulseek tek
     oturuma izin veriyor, biri diğerini düşürür.
2. **Klasörler:**
   - İndirilenler varsayılan olarak `Müzik/djpull`'a gider.
   - "Müzik kütüphanen": zaten sende olan track'ler tekrar indirilmez.
     Rekordbox/Serato kütüphaneni gösterebilirsin.
   - Masaüstü, Belgeler ve İndirilenler kullanılamaz (macOS bu klasörleri arka
     plan işlemlerine kapatıyor). Kütüphanen oradaysa Müzik klasörüne taşı.
3. **Paylaşım:** Soulseek'te herkes paylaşır. **500 dosyanın altında paylaşana
   birçok kullanıcı indirme vermez.** Başkaları sadece klasör adını görür,
   Mac'indeki yolu görmez. Rekordbox veritabanı hiçbir zaman paylaşılmaz.
   Yükleme hızını internetine göre ayarla (varsayılan 500 KB/s).

## 5. Kullanım

- **Spotify:** playlist ya da albüm linkini yapıştır. Spotify herkese açık
  playlist'lerde ilk 100 track'i veriyor; daha uzunsa kalanını tracklist olarak
  yapıştır.
- **YouTube / YouTube Music:** playlist linki (500 videoya kadar).
- **Tracklist:** "Sanatçı - Parça" satırları (djooni, 1001Tracklists…).

## 6. Sorun çıkarsa

- **Port kapalı / CGNAT:** Bağlantı kutusunda (sol üstteki yeşil nokta) "port
  kapalı · CGNAT" görürsen operatörün seni paylaşımlı bir IP arkasına koymuş.
  Portu da kapalı olan kullanıcılardan indiremezsin. Operatörünü arayıp
  "CGNAT'tan çıkarılmak, public IP istiyorum" de.
- **Bağlanmıyor:** kullanıcı adı ya da şifre yanlış olabilir; ilk kurulum
  ekranı sebebini yazar.
- **Hata bildirmek için:** şu iki dosyayı gönder:
  `~/Library/Application Support/djpull/panel.log` ve `slskd.log`.
  (Finder → Git → Klasöre Git → yukarıdaki yol.)

## Kaldırma

1. Uygulamalar'dan **djpull**'u Çöp Sepeti'ne at.
2. İstersen ayarları ve kayıtları da sil:
   `~/Library/Application Support/djpull` (indirdiğin müzikler `Müzik/djpull`'da
   kalır).
