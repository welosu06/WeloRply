# Sürüm notları / Release notes

## 0.12.8 beta — 2026-10-27

- Windows kurucusu açıldığında otomatik başlar; panel kurulumu algılar, bağlantıyı onarır ve hazır durumunu gösterir. Tekrar düğmeye basmak gerekmez. İlk dosyayı kullanıcı açmalıdır.
- Panel yeniden açıldığında bekleyen kurulum takibi sürer.
- Windows installer starts on opening; the panel detects installation and prepares the connection automatically. Reopening the panel resumes waiting.
- Real Windows helper registration and native connection call passed. Download/poll/resume flow passed browser fixtures. The Chrome download and Windows security prompt were not tested end-to-end.

## 0.12.7 beta — 2026-10-27

- Windows: eklentide kur/onar düğmesi ve terminal gerektirmeyen EXE kurucusu. Erişim izni kullanıcı ayarlarına kaydedilir. İlk kurucu kullanıcı tarafından açılır.
- X makale başlığı ve gövdesi için metin okuma desteği.
- GitHub’daki Mac yardımcısı ve model dili düzeltmeleri korundu.
- Windows setup/repair button, GUI installer and persisted origin permission; article text extraction. Existing Mac fixes preserved.
- Validation: compiled helper protocol, setup-button branches and article extraction fixtures passed. Live Windows repair and the reported X article remain unverified.


## 0.12.6 beta — 2026-10-25

### Türkçe

1. Mac yardımcısı, uygun Node.js yoksa resmî kaynaktan indirir ve SHA-256 özetiyle doğrular.
2. Microsoft Edge klasörüne yazılamaması, Chrome yardımcısının kurulmasını engellemez.
3. Ollama'nın AppleScript ile kapatılmasında görülen `Kullanıcı vazgeçti (-128)` adımı kaldırıldı. Bağlantı ayarı için yeniden başlatma gerektiğinde kullanıcı menü çubuğundan Ollama'dan çıkar; kurucu Enter / Devam ile sürer.
4. Mac Qwen 0.8B ve 2B için daha kısa talimatlar, açık dil adları ve tekrar denemede düzeltme mesajları kullanılır. Güvenilir olmayan dil tespitleri kesin bir dil uyuşmazlığı sayılmaz.
5. Windows üretim istekleri ile Gemma 1B'nin önceki davranışı karşılaştırma testleriyle korundu. Windows yardımcı ZIP'i byte düzeyinde aynıdır.
6. Kurulum, güncelleme ve sorun çözme rehberleri Türkçe ve İngilizce olarak yenilendi. Eklenti sürüm etiketleri 0.12.6 olarak eşitlendi.

**Kontrol kapsamı:** Üç modelin her biriyle gerçek Mac üzerinde bir İngilizce ve bir Türkçe örnek, toplam altı yerel üretim yapıldı. Qwen 0.8B ve 2B doğru dilde döndü. Gemma 1B İngilizce örnekte çalıştı; Türkçe örneğe İngilizce döndü. Kullanıcı son paketin çalıştığını doğruladı. Testlerde X'e yorum gönderilmedi; tüm gönderiler ve cihazlar için garanti verilmez. Dil tespiti/tekrar deneme, Windows eşdeğerliği ve kurucu hata durumları ayrıca otomatik testlerle kontrol edildi.

**Güncelleme:** ZIP'in içeriğini mevcut eklenti klasörüne kopyala, Chrome'da Welo'yu yenile ve X sekmelerini yenile. Modelleri tekrar indirme. Eski Mac yardımcısını kullanıyorsan yeni yardımcı paketini bir kez çalıştır.

### English

1. The Mac helper downloads Node.js from its official source when needed and verifies its SHA-256 checksum.
2. An Edge folder permission error no longer aborts Chrome registration.
3. The failing AppleScript quit step was removed. When the origin setting requires a restart, setup asks the user to quit Ollama from the menu bar and continue.
4. Mac Qwen 0.8B/2B use shorter instructions, explicit language names and retry feedback. Unreliable language detections are not treated as definite mismatches.
5. Regression comparisons preserve Windows generation requests and existing Gemma 1B behavior. The Windows helper ZIP is byte-for-byte unchanged.
6. Turkish and English setup, update and troubleshooting guides were revised; extension version labels now read 0.12.6.

**Validation scope:** Six local generations on a real Mac: one English and one Turkish example for each model. Both Qwen models used the expected language. Gemma 1B worked on English but answered the Turkish sample in English. The user confirmed the current package works. No comments were posted to X during these tests. Language/retry handling, Windows equivalence and installer failure cases were also checked with automated tests.

