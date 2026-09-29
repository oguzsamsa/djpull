**[⬇ Download the latest version](https://github.com/oguzsamsa/djpull-surumler/releases/latest)** · [Türkçe kurulum rehberi ↓](#türkçe)

# Installing djpull

djpull downloads Spotify and YouTube playlists from Soulseek, lossless
(FLAC/WAV/AIFF) whenever possible. Stuck downloads are moved to another source
automatically.

Requirements: an Apple Silicon Mac (M1 or later), macOS 12 or newer.

## 1. Download and install

1. Download `djpull_…_aarch64.dmg` from the [latest release](https://github.com/oguzsamsa/djpull-surumler/releases/latest) and open it.
2. Drag **djpull** into the **Applications** folder in the window that opens.

## 2. First launch (once)

djpull isn't signed by an Apple-registered developer, so macOS blocks it the
first time. This is expected:

1. Open **djpull** from Applications. You'll see "Apple could not verify
   djpull is free of malware". Click **Done**.
   (Don't click **Move to Trash**.)
2. Open **System Settings → Privacy & Security** and scroll to the bottom.
   Next to "djpull was blocked", click **Open Anyway** and enter your Mac
   password.
3. Open djpull again and click **Open Anyway** once more.

You won't see these steps again.

If you get "djpull is damaged and can't be opened": the download was
corrupted or it's an old version; download it again. If that doesn't help, run
this in Terminal:

```
xattr -dr com.apple.quarantine /Applications/djpull.app
```

## 3. Permissions

- **Local network:** "djpull would like to find devices on your local network"
  → **Allow.** djpull uses it to open the Soulseek port on your router.
- **Folders:** if it asks for access to your Music folder, allow it.

## 4. First-time setup (inside djpull)

1. **Soulseek account:**
   - If you have one (SoulseekQt, Nicotine+), choose **I have an account** and
     sign in.
   - Otherwise choose **New account**: make up a username and password; the
     account is created on first login. **There's no password recovery, so
     write them down.**
   - Don't use the same account in SoulseekQt/Nicotine+ while djpull is open:
     Soulseek allows one session per account, and one kicks the other out.
2. **Folders:**
   - Downloads go to `Music/djpull` by default.
   - "Your music library": tracks you already have won't be downloaded again.
     You can point it at your Rekordbox/Serato library.
   - Desktop, Documents and Downloads can't be used (macOS blocks them for
     background apps). If your library is there, move it to your Music folder.
3. **Sharing:** everyone on Soulseek shares. **Many users won't let you
   download if you share fewer than 500 files.** Others only see folder names,
   never paths on your Mac. Your Rekordbox database is never shared. Set the
   upload speed to suit your connection (500 KB/s by default).

## 5. Using it

- **Spotify:** paste a playlist or album link. Spotify only provides the first
  100 tracks of public playlists; for longer ones, paste the rest as a
  tracklist.
- **YouTube / YouTube Music:** a playlist link (up to 500 videos).
- **Tracklist:** "Artist - Title" lines (djooni, 1001Tracklists…).
- **Language:** the **EN/TR** button in the top bar.

## 6. If something goes wrong

- **Port closed / CGNAT:** if the connection box (the green dot at the top
  left) shows "port closed · CGNAT", your ISP puts you behind a shared IP. You
  can't download from users whose port is also closed. Call your ISP and ask
  for a public IP.
- **Can't connect:** the username or password may be wrong; the setup screen
  tells you why.
- **Reporting a problem:** send these two files:
  `~/Library/Application Support/djpull/panel.log` and `slskd.log`
  (Finder → Go → Go to Folder → the path above). The connection box shows your
  djpull version.

## Uninstalling

1. Move **djpull** from Applications to the Trash.
2. Optionally delete its settings and records too:
   `~/Library/Application Support/djpull` (your downloaded music stays in
   `Music/djpull`).

---

<a id="türkçe"></a>
<details>
<summary><b>Türkçe kurulum rehberi</b></summary>

## djpull kurulumu

djpull, Spotify ve YouTube playlist'lerini Soulseek'ten, mümkünse kayıpsız
(FLAC/WAV/AIFF) indirir. Takılan indirmeleri kendisi başka kaynağa taşır.

Gerekenler: Apple Silicon (M1 ve sonrası) bir Mac, macOS 12 ya da yenisi.

### 1. İndir ve kur

1. [Son sürümün sayfasından](https://github.com/oguzsamsa/djpull-surumler/releases/latest) `djpull_…_aarch64.dmg` dosyasını indir ve aç.
2. Açılan pencerede **djpull**'u **Applications** (Uygulamalar) klasörüne sürükle.

### 2. İlk açılış (sadece bir kez)

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

### 3. İzinler

- **Yerel ağ:** "djpull yerel ağınızdaki aygıtları bulmak istiyor" → **İzin Ver.**
  djpull modemine Soulseek portunu açtırmak için bunu kullanır.
- **Klasörler:** Müzik klasörüne erişim sorarsa izin ver.

### 4. İlk kurulum (djpull içinde)

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

### 5. Kullanım

- **Spotify:** playlist ya da albüm linkini yapıştır. Spotify herkese açık
  playlist'lerde ilk 100 track'i veriyor; daha uzunsa kalanını tracklist olarak
  yapıştır.
- **YouTube / YouTube Music:** playlist linki (500 videoya kadar).
- **Tracklist:** "Sanatçı - Parça" satırları (djooni, 1001Tracklists…).
- **Dil:** Üst bardaki **EN/TR** düğmesi.

### 6. Sorun çıkarsa

- **Port kapalı / CGNAT:** Bağlantı kutusunda (sol üstteki yeşil nokta) "port
  kapalı · CGNAT" görürsen operatörün seni paylaşımlı bir IP arkasına koymuş.
  Portu da kapalı olan kullanıcılardan indiremezsin. Operatörünü arayıp
  "CGNAT'tan çıkarılmak, public IP istiyorum" de.
- **Bağlanmıyor:** kullanıcı adı ya da şifre yanlış olabilir; ilk kurulum
  ekranı sebebini yazar.
- **Hata bildirmek için:** şu iki dosyayı gönder:
  `~/Library/Application Support/djpull/panel.log` ve `slskd.log`.
  (Finder → Git → Klasöre Git → yukarıdaki yol.) Bağlantı kutusunda djpull
  sürümün de yazıyor.

### Kaldırma

1. Uygulamalar'dan **djpull**'u Çöp Sepeti'ne at.
2. İstersen ayarları ve kayıtları da sil:
   `~/Library/Application Support/djpull` (indirdiğin müzikler `Müzik/djpull`'da
   kalır).

</details>
