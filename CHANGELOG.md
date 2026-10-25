# Sürüm notları / Release notes

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
