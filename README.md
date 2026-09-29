*Türkçe: [KURULUM.md](KURULUM.md)*

# Installing djpull

djpull downloads Spotify and YouTube playlists from Soulseek, lossless
(FLAC/WAV/AIFF) whenever possible. Stuck downloads are moved to another source
automatically.

Requirements: an Apple Silicon Mac (M1 or later), macOS 12 or newer.

## 1. Download and install

1. Download `djpull_…_aarch64.dmg` from the [latest release](../../releases/latest) and open it.
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
