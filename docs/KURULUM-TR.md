# WeloRply kurulumu — adım adım

**Sürüm: 0.12.4 beta.** Eklentinin Chrome'daki adı **Welo Reply** olarak görünür. İndirdiğin dosyanın adı **WeloRply.zip**. İkisi aynı uygulamadır.

Bilgisayar konusunda deneyimli olman gerekmiyor. Aşağıdaki sırayı izle. Bir adımın sonunda yazan sonucu görmeden sonraki adıma geçme.

## Başlamadan önce

İki ayrı şey kuracağız:

- **WeloRply:** X'in yanında açılan düğmeler ve ayar paneli.
- **Ollama ve bir model:** Yorumları bilgisayarında hazırlayan bölüm. Model, Ollama'nın indirdiği ek bir dosyadır; eklenti ZIP'inin içinde değildir.

Güncel masaüstü Chrome kullan. Windows'ta Ollama için Windows 10 22H2 veya üzeri; Mac'te macOS 14 veya üzeri gerekir. 8 GB RAM küçük model için başlangıç hedefimizdir; 16 GB önerilir. Bunlar her bilgisayarda denenmiş minimumlar değildir. Yaklaşık 10 GB boş disk alanı ayır; seçtiğin modele göre daha fazlası gerekebilir. Telefon/tablet için kurulum paketi değildir.

**Mac paketi gerçek Mac üzerinde henüz test edilmedi.** Yardımcı kurucular imzasızdır. Bu bir beta sürümüdür.

## 1. Doğru ZIP dosyasını indir

1. [WeloRply.zip'i indir](https://github.com/welosu06/WeloRply/raw/refs/heads/main/WeloRply.zip).
2. Dosyayı İndirilenler klasöründe bul.
3. GitHub'ın yeşil **Code → Download ZIP** düğmesini kullanma. O düğme depo dosyalarını indirir; doğrudan kurulacak paket yukarıdaki **WeloRply.zip** bağlantısıdır.

**Sonuç:** Bilgisayarında WeloRply.zip dosyasını görmelisin.

## 2. ZIP'i klasöre çıkar

**Windows:** Dosyaya sağ tıkla → **Tümünü ayıkla / Tümünü çıkar** → hedef olarak Belgeler içinde **WeloRply** klasörünü seç → **Ayıkla**.

**Mac:** ZIP'e çift tıkla. Oluşan klasörü Belgeler gibi kalıcı bir yere taşı.

Çıkardığın klasörü aç. İçinde `manifest.json`, `panel.html`, `background.js` ve `setup` klasörü gibi dosyalar olmalı. Dosya uzantıları gizliyse manifest dosyası yalnızca **manifest** diye görünebilir.

**Önemli:** ZIP'in içini görüntülemek, ZIP'i çıkarmak değildir. Chrome'a ZIP dosyasını değil, çıkarılmış klasörü göstereceğiz. Bu klasörü kurulumdan sonra silme veya başka yere taşıma.

## 3. Eklentiyi Chrome'a ekle

1. Chrome'u aç.
2. Üstteki adres çubuğuna `chrome://extensions` yaz ve Enter'a bas. Bunu Google arama kutusuna yazma.
3. Sağ üstteki **Geliştirici modu** anahtarını aç.
4. **Paketlenmemiş öğe yükle** düğmesine bas.
5. Bir önceki adımda çıkardığın, içinde `manifest.json` bulunan klasörü seç.
6. **Klasör seç / Aç** düğmesine bas.

**Sonuç:** Uzantılar sayfasında **Welo Reply**, sürüm **0.12.4** görünmeli. Etkinleştirme anahtarı açık olmalı.

“Manifest dosyası eksik” hatası çıkarsa yanlış klasörü seçmişsindir. Seçtiğin klasörün bir altındaki klasörü kontrol et. `manifest.json` dosyasını açman değil, dosyanın bulunduğu klasörü seçmen gerekiyor.

## 4. Welo panelini aç

1. Chrome'un sağ üstündeki yapboz şeklindeki **Uzantılar** simgesine bas.
2. **Welo Reply** yanındaki sabitleme simgesine bas.
3. Araç çubuğundaki Welo simgesine bas.
4. Welo sağ tarafta açılır. X sayfan yerinde kalır.
5. Üstte **TR · Türkçe** seç.
6. **Kurulum** düğmesine bas. Kurulum ekranı bu yan panelin içinde açılır.

**Geri** düğmesi Welo'nun ana ekranına döndürür. Kurulumdaki resmî indirme bağlantıları ise tıkladığında ayrı tarayıcı sekmesi açabilir.

## 5A. Windows'ta Ollama'yı kur

1. Welo kurulumundaki **Ollama resmî kurulumunu aç** bağlantısına bas veya [Ollama Windows](https://ollama.com/download/windows) sayfasına git.
2. Resmî Windows kurucusunu indir ve çalıştır.
3. Kurulumu tamamla. Ollama'yı Başlat menüsünden aç.
4. Bir model indirmediysen henüz yorum üretilemez; modeli 7. adımda indireceğiz.

### Windows yardımcısı — isteğe bağlı kolaylık

Yardımcı, Ollama bağlantısını başlatmayı ve onarmayı kolaylaştırır. Yardımcısız yöntem aşağıda var.

1. Welo'daki **Yardımcı kurulum paketini indir** bağlantısına bas.
2. İndirilen yardımcı ZIP'ini de ayrı bir klasöre çıkar.
3. Çıkan `Setup.ps1` dosyasına sağ tıkla. Gerekirse **Daha fazla seçenek göster → PowerShell ile çalıştır** seç.
4. Açılan Welo yardımcı penceresinde eklenti kimliği önceden doldurulmuş olmalı.
5. **Kur ve baslat** düğmesine bas.
6. Başarılı kurulum mesajını gördükten sonra Welo paneline dön ve **Kurulumu kontrol et** düğmesine bas. Gerekirse **Bağlantıyı onar / Ollama'yı başlat** seç.

Yardımcı Windows oturum açılışında çalışacak şekilde kaydolur. Onarım sırasında Ollama yeniden başlatılabilir; devam eden başka Ollama işleri kesilebilir.

Windows dosyayı engellerse güvenlik ayarlarını kapatma. Aşağıdaki yardımcısız yöntemi kullan.

## 5B. Mac'te Ollama ve yardımcı

1. [Ollama Mac](https://ollama.com/download/mac) sayfasından resmî uygulamayı indir.
2. İndirilen disk görüntüsünü aç; Ollama'yı **Applications / Uygulamalar** klasörüne taşı ve aç.
3. Yardımcı kullanacaksan [Node.js resmî indirme sayfasından](https://nodejs.org/en/download) **22 veya daha yeni LTS** sürümünün macOS kurucusunu yükle. Cihazına uygun Apple Silicon veya Intel sürümünü seç.
4. Welo'dan **Yardımcı kurulum paketini indir** seç ve ZIP'i çıkar.
5. **Uygulamalar → İzlenceler → Terminal** uygulamasını aç.
6. Terminal'e `bash` yaz ve ardından bir boşluk bırak. Henüz Enter'a basma.
7. Çıkardığın `Kur.command` dosyasını Terminal penceresinin içine sürükle. Dosyanın yolu otomatik eklenir.
8. Enter'a bas. Kurulum tamamlandı mesajını bekle.
9. Welo panelinde **Kurulumu kontrol et** seç.

Eksik bileşen uyarısı gelirse belirtilen resmî uygulamayı kurup adımı yeniden uygula. Mac'te 403 hatası sürerse Ollama menüsünden **Quit** ile çıkıp Welo'da **Bağlantıyı onar** seç. Sistem güvenlik korumalarını devre dışı bırakma.

## 6. Yardımcı olmadan bağlanma

Yardımcı kurmak istemiyorsan veya kurulamıyorsa:

1. Önce Ollama'nın kurulu olduğundan emin ol.
2. Ollama'yı tamamen kapat. Windows'ta sağ alttaki gizli simgeler okundan Ollama'ya sağ tıklayıp çık; Mac'te menü çubuğundan **Quit** seç. Sadece uygulama penceresini kapatmak yeterli olmayabilir.
3. Welo'da **Ayarlar → Bağlantı yardımı** bölümünü bul.
4. **Komutları kopyala** düğmesine bas. Bu komutlar senin eklenti kimliğine ve işletim sistemine göre hazırlanır.
5. Windows'ta Başlat menüsünden **PowerShell**, Mac'te **Terminal** aç.
6. Komutları yapıştır ve Enter'a bas.
7. Bu terminal penceresini açık bırak; Welo'ya dönüp bağlantıyı yenile.

“Address already in use / adres kullanımda” mesajı gelirse başka Ollama işlemi zaten açıktır. Önce açık Ollama'yı kapat; ikinci bir sunucuyu aynı adreste başlatmaya çalışma.

**Sonuç:** Welo'nun yerel model bölümünde **Bağlı** yazmalı. “Henüz model kurulu değil” görürsen sonraki adıma geç.

## 7. Bir model indir

1. Ana ekrana dön. **Modeller** sekmesine veya **+ Model indir / kur** düğmesine bas.
2. İlk deneme için küçük seçenek olan **Qwen 3.5 · 0.8B** ile başlayabilirsin.
3. **İndir ve kullan** düğmesine bas.
4. Ayrı model indirme sekmesi açılır. Gerekirse oradaki **İndir ve kullan** düğmesine de bas.
5. İndirme tamamlanana kadar bu sekmeyi açık bırak. İlk indirme internet hızına göre zaman alır.
6. Model hazır mesajından sonra Welo yan paneline dön. Model normalde otomatik seçilir; görünmüyorsa model listesinin yanındaki **↻** düğmesine bas.

Küçük model daha az kaynak kullanır ama dilbilgisi veya anlam hataları yapabilir. Modelin indirme boyutu, çalışırken gereken RAM miktarı değildir.

## 8. X'e hiçbir şey göndermeden test et

1. Welo'da **Ayarlar** sekmesine bas.
2. **Yerel modeli dene** alanına kısa bir örnek gönderi yaz.
3. **Yalnızca yorum üret** düğmesine bas.
4. Altında bir yorum görünmesini bekle. Modelin ilk yüklenmesi sonraki denemelerden daha uzun sürebilir.

**Bu düğme X'e yorum göndermez.** Önce bu testin çalıştığını gör.

## 9. X'te ilk kullanım

1. Chrome'da X hesabına giriş yap.
2. Açık X sayfasını yenile.
3. Metin içeren bir gönderinin altındaki Welo düğmelerini bul. Üzerlerine gelince görevleri görünür.
4. İlk denemede **Yorum üret ve taslak olarak aç** seç. Yorumu incele; göndermek istersen X'in **Yanıtla** düğmesine kendin bas.
5. **Yorum üret ve hemen gönder** ayrı bir işlemdir; yorum gönderir. Hazırlık ayrı görev sekmesinde yapılabilir.

Dil ve üslup: Welo'nun **Yazım** sekmesinden amaç ve ton seç. TR / EN arayüz seçimi, yorum dilini değiştirmez. Yorumun gönderinin dilinde olması hedeflenir; model hataları mümkündür.

## 10. Link listesiyle çalışma

1. X gönderisinin bağlantısını kopyala.
2. Welo ana ekranındaki **Manuel link ekleme** kutusuna yapıştır. Birden fazla bağlantı varsa her satıra bir tane yaz.
3. **+ Link ekle** seç. Bağlantıların **Link listesi** altında göründüğünü kontrol et.
4. **Başlat** düğmesine bas. Bu işlem listedeki gönderilere otomatik yorum gönderir.
5. **Yan paneli ve Chrome'u açık tut; bilgisayarı uykuya alma. İşlem sekmesindeki yanıt alanına müdahale etme.**
6. Başarılı gönderim yanıtı alınan link listeden silinir; sıradakine geçilir. Çalışma sırasında kaydedilen yeni linkler de kuyruğa alınır.
7. **Durdur** yeni işlemleri durdurmayı ister. Daha önce gönderilmiş yorumları geri almaz.

Son linkin sonucu gelmeden “Tamamlandı” gösterilmez. Hatalı link kalırsa “Tamamlanamadı” görürsün. Gönderim başlamadan oluşan model hatası bir kez yeniden denenir; gönderilip gönderilmediği belirsiz işlem otomatik tekrarlanmaz. Böyle bir durumda X'te kontrol et.

## 11. Yeni sürüme güncelleme

1. Kuyruğu durdur, devam eden işlemin sonucunu kontrol et.
2. Yeni **WeloRply.zip** dosyasını indir ve ayrı bir geçici klasöre çıkar.
3. Yeni dosyaları Chrome'a daha önce gösterdiğin kalıcı Welo klasörünün içine kopyala; aynı adlı dosyaları değiştir. Yeni klasörü eski klasörün içine iç içe yerleştirme.
4. `chrome://extensions` sayfasında Welo kartının **Yenile** düğmesine bas.
5. Sürümün **0.12.4** olduğunu kontrol et.
6. Açık X sekmelerini yenile, Welo panelini kapatıp yeniden aç.

Eklentiyi **Kaldır** düğmesiyle silmen gerekmez; kaldırmak ayarları kaybettirebilir. GitHub'dan yapılan bu kurulum otomatik güncellenmez.

## Sorun olursa

| Gördüğün durum | Yapılacak işlem |
| --- | --- |
| Manifest eksik | ZIP'i çıkar; doğrudan manifest.json içeren klasörü seç. |
| Welo simgesi yok | Chrome'un Uzantılar/yapboz menüsünden Welo'yu sabitle. |
| Bağlantı yok | Ollama'nın açık olduğunu kontrol et, sonra ↻ veya Bağlantıyı onar seç. |
| Ollama 403 | Yardımcıyla onar; düzelmezse 6. adımdaki yardımcısız başlatmayı uygula. |
| Model bulunamadı | Modeller bölümünden bir model indir ve seç. |
| Model zaman aşımı | Küçük model seç, yoğun uygulamaları kapat, model testini tekrar yap. |
| Extension context invalidated | X sayfasını yenile ve Welo panelini yeniden aç. |
| Gönderi açıldı ama bekliyor | Durum ve ilerleme alanındaki aşamayı oku. Model yükleme veya ayarladığın bekleme süresi devam ediyor olabilir. Hata gelirse tam metni kaydet. |
| Son link kaldı | Sürümü kontrol et. X'te yorumun gönderilip gönderilmediğine bak; durum/hata metniyle sorun bildir. |
| Yanıt metni eşleşmedi | Taslağı X'te kontrol et. Tekrar başlatmadan önce önceki yorumun gönderilmediğinden emin ol. |
| Önceki gönderim kaydı var | Önce X'teki yorumu kontrol et. Bilerek tekrar istiyorsan Ayarlar'daki tekrar yorum seçeneğini aç. |

[GitHub Issues üzerinden sorun bildir](https://github.com/welosu06/WeloRply/issues). İşletim sistemi, Chrome sürümü, Welo sürümü, model adı ve tam hata metnini ekle. Ekran görüntülerinden kişisel bilgileri çıkar. Şifre, oturum çerezi veya anahtar paylaşma.

## Beta ve veri bilgisi

Gönderiler yorum üretmek için yerel Ollama'ya gönderilir. Ayarlar ve işlem kayıtları Chrome'un yerel uzantı depolamasında tutulur. Model indirmeleri, dış bağlantılar ve X kullanımı internet gerektirir. Bu sürümde Welo lisans sunucusu veya ücretli AI API yoktur.

Gerçek X üzerinde kapsamlı uçtan uca doğrulama tamamlanmadı; son-link beklemesinin kullanıcının ortamındaki kesin nedeni henüz doğrulanmadı. Son değişiklikler test ortamında kontrol edildi; sorunların tüm cihazlarda çözüldüğü garantisi yoktur.

[X otomasyon kurallarını](https://help.x.com/en/rules-and-policies/x-automation) incele. Otomatik beğeni ve web arayüzü otomasyonu gibi özellikler bu kurallarla çelişebilir. Hesap güvenliği veya etkileşim artışı garantisi verilmez. Ollama ve modellerin ayrı lisansları vardır.
