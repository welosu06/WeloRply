# WeloRply

**Local AI replies for X · X için yerel yapay zekâ yorum asistanı**

[Download WeloRply.zip / İndir](https://github.com/welosu06/WeloRply/raw/refs/heads/main/WeloRply.zip)

**Beta · v0.12.1** — The extension currently displays the name **Welo Reply**. This repository distributes the installable package and documentation; it does not include the development workspace.

---

## Türkçe

WeloRply, X gönderilerine Ollama üzerinden bilgisayarında çalışan bir modelle kısa yanıtlar hazırlayan Chrome eklentisidir. Arayüz Türkçe ve İngilizce arasında değiştirilebilir. Yorum dili, arayüz dilinden bağımsız olarak gönderiye göre belirlenir.

### Özellikler

- Gönderiye uygun yorum amacı ve seçilebilir yorum tonu.
- Taslak hazırlama ve ayrı gönderme işlemi; link listesiyle çalışma.
- Açılıp kapatılabilen yavaş yazım ve yazım düzeltmeleri.
- İsteğe bağlı gönderim sonrası beğeni, bekleme aralığı ve tekrar yorum ayarları.
- Küçük, sürüklenebilir ayar paneli.
- Yan panel içinde ilk kurulum; paneli açmak mevcut X sayfanı değiştirmez.
- Yerel model indirme ekranı ve Windows/Mac yardımcı paketleri.

### Kurulum

1. Üstteki **WeloRply.zip** bağlantısından indir; ZIP'i kalıcı bir klasöre çıkar.
2. Chrome'da `chrome://extensions` adresini aç.
3. **Geliştirici modu → Paketlenmemiş öğe yükle** seç.
4. İçinde `manifest.json` bulunan klasörü seç.
5. Welo'yu açıp **Kurulum** düğmesine bas. Ollama'yı ve cihazına uygun yerel modeli kur.
6. Önce **Ayarlar → Yerel modeli dene** ile bağlantıyı kontrol et. Bu test X'e yorum göndermez.
7. X sayfasını yenile. Panelin üstünden **TR / EN** seçebilirsin.

Güncellemede aynı eklenti klasörünün dosyalarını yenileriyle değiştir, Chrome uzantılar ekranında **Yenile** düğmesine bas ve X sekmelerini yenile. Kurulu eklentiyi kaldırmak ayar kaybına yol açabilir.

### Gereksinimler ve beta sınırları

- Güncel masaüstü Chrome; paket teknik olarak Chrome 116+ ister.
- Windows için Ollama: Windows 10 22H2 veya üzeri.
- Mac için Ollama: macOS 14+; mevcut Welo Mac yardımcısı ayrıca Node.js 22+ ister.
- 8 GB RAM ve küçük model başlangıç hedefidir; 16 GB RAM önerilir. Bunlar doğrulanmış minimum donanım garantisi değildir.
- Model/uygulama indirmeleri için boş disk alanı ve internet gerekir. X kullanımı internet gerektirir.
- **Mac paketi henüz gerçek Mac üzerinde test edilmedi.**
- Yardımcı kurucular imzasızdır; sistem güvenlik kontrolleri kurulumu engelleyebilir. Güvenlik korumalarını kapatmadan belgelenen yardımcısız yöntemi kullanabilirsin.
- Küçük modeller dilbilgisi, anlam veya dil seçimi hataları yapabilir.
- Gerçek X üzerinde kapsamlı uçtan uca doğrulama tamamlanmadı. Gönderim sonucu belirsizse tekrar denemeden önce X'te kontrol et.

### Veriler ve kullanım

Model istekleri bu sürümde bilgisayarındaki `127.0.0.1:11434` adresine gider. Ayarlar ve işlem kayıtları Chrome'un yerel uzantı depolamasında tutulur. Model indirmeleri, X işlemleri ve dış bağlantılar internet kullanır. Bu pakette Welo lisans sunucusu veya ücretli AI API bağlantısı yoktur.

X'in [otomasyon kurallarına](https://help.x.com/en/rules-and-policies/x-automation) uymak gerekir. Otomatik beğeni ve web arayüzü otomasyonu gibi mevcut özellikler platform kurallarıyla çelişebilir. Hesap güvenliği, görünürlük veya etkileşim artışı garantisi verilmez.

---

## English

WeloRply is a Chrome extension that prepares short replies to X posts using a local model through Ollama. Switch the interface between Turkish and English; replies still follow the post's language.

### Install

1. Download **WeloRply.zip** above and extract it to a permanent folder.
2. Open `chrome://extensions` in Chrome.
3. Enable **Developer mode**, select **Load unpacked**, and choose the folder containing `manifest.json`.
4. Open Welo and select **Setup** in the side panel. Install Ollama and a suitable local model.
5. Use **Settings → Test the local model** first. This test does not post to X.
6. Refresh X and choose your interface language using **TR / EN**.

For updates, replace the files in the same extension folder, reload the extension, and refresh X tabs.

### Features and limitations

Reply purposes and tones, drafts, sending, link lists, optional slow typing/corrections, post-send liking, pacing, repeat-reply settings, and a compact draggable settings panel are included. Setup opens inside the side panel without changing the active X page.

Use current desktop Chrome. Ollama requires Windows 10 22H2+ or macOS 14+. The Mac helper also requires Node.js 22+. An 8 GB RAM computer with a small model is a starting target; 16 GB is recommended, not a tested performance guarantee.

**This is a beta.** The Mac helper has not been tested on real Mac hardware. Helper installers are unsigned. Small models may make language or factual errors. Comprehensive live-X end-to-end validation is still pending. Check uncertain send results on X before retrying.

Generation requests go to local Ollama at `127.0.0.1:11434`; settings and operation records use local extension storage. Downloads and X actions require internet. No Welo licensing server or paid AI API is included.

Follow [X's automation rules](https://help.x.com/en/rules-and-policies/x-automation). Features such as automated likes and website automation may conflict with platform rules. No account-safety or engagement guarantees are offered.

## Report a problem / Sorun bildir

Use [Issues](https://github.com/welosu06/WeloRply/issues) with your operating system, Chrome version, Welo version, model name, and steps to reproduce. Remove personal data from screenshots. Never share passwords, session cookies, tokens or private conversations.

## Package verification

SHA-256 of `WeloRply.zip`:

```text
681f8ba1b02adad731a7c8c6f1639e74e212ae6a85efe3179dd560bdc795e56d
```

Ollama and downloaded models are separate components with their own licenses.
