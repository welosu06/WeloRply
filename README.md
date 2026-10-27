# WeloRply · Welo Reply

**X için yerel yapay zekâ yorum asistanı · Local AI replies for X**  
**Güncel sürüm / Current version: 0.12.7 beta — 25 Ekim / October 2026**

## İndir / Download

### [WeloRply.zip — güncel paketi indir / download the current package](https://github.com/welosu06/WeloRply/raw/refs/heads/main/WeloRply.zip)

Chrome'da eklentinin adı **Welo Reply** görünür. ZIP'in adı **WeloRply.zip**.

- **[Türkçe: adım adım ayrıntılı kurulum](docs/KURULUM-TR.md)**
- **[English: detailed step-by-step setup](docs/SETUP-EN.md)**
- [0.12.7 sürüm notları / release notes](CHANGELOG.md)

Doğrudan yukarıdaki paketi indir. **Code → Download ZIP** tüm depoyu indirir; doğrudan eklenti paketi değildir.

## Türkçe — ilk kurulum

1. **WeloRply.zip** dosyasını indir ve çıkar. Oluşan klasörü **Belgeler/WeloRply** gibi kalıcı bir yere koy.
2. Chrome'un adres çubuğuna `chrome://extensions` yaz. Sağ üstte **Geliştirici modu**nu aç.
3. **Paketlenmemiş öğe yükle** düğmesine bas. Doğrudan `manifest.json` içeren klasörü seç. Listede **Welo Reply 0.12.7** görünmeli.
4. Chrome'un yapboz/Uzantılar menüsünden Welo'yu sabitle ve simgesine tıklayıp paneli aç.
5. **Kurulum** bölümünden işletim sistemine uygun resmî **Ollama** indirme bağlantısını aç ve Ollama'yı kur.
6. Aşağıdaki **Mac** veya **Windows** adımlarını uygula.
7. Welo'da **Kurulumu kontrol et** düğmesine bas.
8. **Modeller** bölümünden **bir model** indir ve seç. Üçünü de indirmen gerekmez. İndirme sekmesini tamamlanana kadar açık tut.
9. **Ayarlar → Yerel modeli dene → Yalnızca yorum üret** ile örnek bir gönderi dene. Bu test X'e yorum göndermez.
10. X sayfasını yenile. İlk kullanımda **taslak üret**, yorumu oku ve göndermek istiyorsan X üzerinden gönder.

### Mac

1. Ollama'yı **Uygulamalar / Applications** klasörüne koy ve bir kez aç.
2. Welo'dan yardımcı paketini indir veya ana pakette **setup/welo-mac.zip** dosyasını bul. Bu ZIP'i de çıkar.
3. İçindeki **Kur.command** dosyasına çift tıkla. Terminal açılması normaldir; komut yazman gerekmez.
4. Kurucu isterse üst menü çubuğunda **Ollama → Quit / Çıkış** seç. Sadece uygulama penceresini kapatmak yeterli değildir.
5. Kurucuya dön ve **Enter** tuşuna bas. **Kurulum tamamlandı** mesajını bekle.
6. Welo'ya dönüp **Kurulumu kontrol et** seç.

Node.js gerekiyorsa otomatik hazırlanır. **Welo Kurulum.app** aynı kurucunun pencereli alternatifidir; onunla ilerliyorsan **Kur**, sonra gerekirse **Devam** düğmesini kullan. macOS dosyayı engellerse ve diğer hatalarda [ayrıntılı Mac adımlarına](docs/KURULUM-TR.md#5b-macte-kolay-kurulum) bak.

### Windows

1. Welo → **Kurulum → Otomatik bağlantıyı kur / onar** düğmesine bas.
2. Yardımcı yoksa **WeloBaglantiKur.exe** indirilir. Dosyayı aç ve **Kur ve baglan** düğmesine bas. İlk kurucuyu sen açmalısın; eklenti kendiliğinden Windows programı kuramaz.
3. Welo’ya dönüp aynı düğmeye tekrar bas. Yardımcı zaten kuruluysa düğme doğrudan bağlantıyı onarır. Eski yardımcı sorun çıkarıyorsa ana ZIP içindeki **setup/WeloBaglantiKur.exe** dosyasını bir kez çalıştır.
4. Model listesini yenile ve kurulu modelini seç. Terminal açman veya modelleri yeniden indirmen gerekmez.

Onarım Ollama’yı yeniden başlatabilir ve devam eden işleri kesebilir. Yeni kurucu yardımcıyı ihtiyaç üzerine Chrome’un başlatması için kaydeder. İmzasız kurucu engellenirse genel güvenlik korumasını kapatma.

### Hangi model?

| Model | Yaklaşık indirme |
| --- | --- |
| Qwen 3.5 · 0.8B | 1,2 GB |
| Qwen 3.5 · 2B | 2,7 GB |
| Gemma 3 · 1B | 806 MB |

Boyutlar sürüme göre değişebilir. Model dosyası Welo ZIP'inin içinde değildir; Ollama ayrıca indirir. Her modelde yorumun dilini ve içeriğini kontrol et. TR/EN seçimi yalnızca arayüz dilini değiştirir.

### Zaten kuruluysa güncelle

1. Kuyruğu durdur ve devam eden gönderimin sonucunu kontrol et.
2. Yeni ZIP'i ayrı bir yere çıkar.
3. İçindeki dosyaları mevcut Welo eklenti klasörüne kopyala; aynı adlı dosyaları değiştir.
4. `chrome://extensions` ekranında **Welo Reply → Yenile** seç ve sürümün **0.12.7** olduğunu kontrol et.
5. Açık X sekmelerini yenile; paneli kapatıp aç.
6. Eski Mac yardımcısı varsa yeni yardımcıyı bir kez çalıştır. v4 yardımcısı zaten kurulu ve bağlantı çalışıyorsa tekrar kurman gerekmez. Modelleri yeniden indirme.

Eklentiyi kaldırmadan güncelleyebilirsin. GitHub'dan kurulan eklenti otomatik güncellenmez. Kurulum klasörünü silme veya taşıma.

## English — quick start

1. Download **WeloRply.zip** above and extract it into a permanent folder.
2. Open `chrome://extensions`, enable **Developer mode**, and choose **Load unpacked**.
3. Select the folder directly containing `manifest.json`; verify **Welo Reply 0.12.7**.
4. Pin Welo, open its panel, and choose **Setup**. Install Ollama from the official link for your OS.
5. **Mac:** extract **setup/welo-mac.zip**, double-click **Kur.command**, and follow its prompts. If asked, quit Ollama from its menu bar icon, then press Enter in the installer. Node.js is prepared automatically when needed.
6. **Windows:** choose Setup → Set up / repair automatic connection. Open the downloaded WeloBaglantiKur.exe once, install, then click the button again.
7. In Welo, choose **Check setup**, download one model, and run **Settings → Test the local model → Generate a reply only**.
8. Refresh X and review a draft before posting.

For upgrades, replace the files in the original extension folder, reload Welo at `chrome://extensions`, and refresh X. Keep existing model downloads. See the [full English guide](docs/SETUP-EN.md) for prerequisites, detailed steps, Mac opening permissions, troubleshooting and manual setup.

## Bu sürüm / This version

- Mac'te Node.js gerektiğinde otomatik indirilip doğrulanır. / Node.js is downloaded and verified when needed on Mac.
- Edge klasör izni Chrome kurulumunu durdurmaz. / Edge folder permissions no longer abort Chrome setup.
- Ollama yeniden başlatılacaksa kurucu açık çıkış adımlarıyla devam eder. / Setup guides the user through quitting Ollama when a restart is needed.
- Mac'teki Qwen modellerinde dil talimatları ve tekrar deneme düzeltildi. / Mac Qwen language instructions and retry feedback were corrected.
- Windows üretim davranışı ve Gemma 1B'nin mevcut davranışı korundu. / Windows generation and existing Gemma 1B behavior were preserved.

Üç modelle gerçek Mac üzerinde yerel yanıt üretimi kontrol edildi; kullanıcı son paketin çalıştığını doğruladı. Bu, her cihaz ve gönderide hatasız sonuç garantisi değildir. Küçük modeller yanlış dil veya içerik üretebilir; ayrıntılı test kapsamı [sürüm notlarında](CHANGELOG.md).

All three models were checked through local generation on a real Mac, and the user confirmed the package works. Small models can still produce language or content errors; see the [release notes](CHANGELOG.md) for scope.

## Kullanım ve yardım / Use and help

- **Kuyruk çalışırken Chrome'u ve yan paneli açık, bilgisayarı uyanık tut.** / Keep Chrome and the side panel open and the computer awake during queue processing.
- **Başlat** ve **hemen gönder** yorum yayımlar; taslak/yerel test farklıdır. / Queue Start and immediate-send actions publish replies; draft/local-test actions are different.
- Belirsiz gönderimi tekrarlamadan önce X'te kontrol et. / Check X before retrying an uncertain send.
- Yorum üretimi yerel Ollama üzerinden yapılır. Model indirme ve X işlemleri internet ister. / Generation uses local Ollama; downloads and X actions need internet.
- [Sorun bildir / Report an issue](https://github.com/welosu06/WeloRply/issues): işletim sistemi, Welo sürümü, model ve hata metnini ekle; şifre veya oturum bilgisi paylaşma.

Paket bütünlüğü / Package checksum: [SHA256SUMS.txt](SHA256SUMS.txt).

Bu depo hazır paket ve belgeleri dağıtır; gerekli JavaScript ZIP'in içindedir. Yardımcı kurucular imzasızdır. Ollama ve modellerin ayrı lisansları vardır. [X otomasyon kurallarını](https://help.x.com/en/rules-and-policies/x-automation) incele.

