# Sürüm notları / Release notes

## 0.12.15 beta — 2026-10-28

- Görev başladıktan sonra gelen yükleniyor bildiriminin görevi yanlışlıkla kesildi olarak işaretlemesi düzeltildi. Görev, onu başlatan sayfanın documentId değeriyle eşleştirilir.
- Late loading events no longer interrupt an assigned task. Navigation completion probes the original document; a new document cannot claim or complete the old task.
- Validation: simulated claim → loading → completion closes the worker; wrong-document completion is rejected and real document replacement interrupts the task. Existing close retry tests passed. Live X behavior remains unverified.

## 0.12.14 beta — 2026-10-28

- Başarılı görev sekmesi ana sekmeden bildirim yanıtı beklemeden kapatılır. Kapatma başarısızsa bir kez yeniden denenir; kalıcı hata artık gizlenmez.
- Completion no longer waits for the origin tab notification. Failed tab removal is retried once and reported; rejected completion messages are surfaced.
- Validation: lifecycle regression and hanging origin, transient close failure, permanent close failure simulations passed. Live X reproduction remains unverified.

## 0.12.13 beta — 2026-10-28

- Yan panelin başına Ctrl + Shift + R düğmesi eklendi. Açık sekmeyi önbelleği atlayarak yeniler; TR/EN durum mesajları gösterir.
- Added an active-tab hard reload button at the top of the side panel.

## 0.12.12 beta — 2026-10-28

- Gönderi butonundan açılan görev sekmesi yorum ve isteğe bağlı beğeni işlemi bitince otomatik kapanır. Ana sekme korunur; hatalı görev sekmesi inceleme için açık kalır.
- Completed toolbar reply tasks now close their worker tab. Completion is persisted before closing; late completion messages cannot overwrite the result.
- Validation: mocked background lifecycle test covers successful closure, preserved failed task, origin notification and late message rejection. No live X post was sent.

## 0.12.11 beta — 2026-10-27

- Hedef gönderinin hemen altındaki satır içi yanıt kutusu desteklenir; yalnızca açılır pencereye bağlı kalınmaz.
- Başka gönderinin kutusu ve mevcut taslak korunur. Satır içi gönderim yalnızca kutu temizlendiğinde ve yeni yorum sayfada göründüğünde başarılı sayılır.
- Browser fixtures passed: inline reply, clear without confirmation, wrong post, existing draft, and the previous five DOM readiness scenarios. Live X failures have not been reproduced; this release addresses a confirmed missing composer path, not a proven diagnosis of those two links.

## 0.12.10 beta — 2026-10-27

- Wait for post text and reply controls before generation; reacquire the target post after a page re-render.
- Distinct errors for post loading, composer opening, send-button readiness and unconfirmed submission. No automatic retry after uncertain sending.
- Browser fixtures cover delayed post/text, replaced post, missing composer and unconfirmed send. The reported live X failure remains unverified.


## 0.12.9 beta — 2026-10-27

- Link kuyruğunda sekmenin açılıp yorumun başlamamasına neden olan sabit sürüm kontrolü düzeltildi. Panel ve içerik betiği sürümü manifestten okur.
- Kurulum iki ayrı numaralı kartla gösterilir: Ollama ve Welo bağlantısı. Zorunlu etiketleri ve ayrı indirme düğmeleri eklendi.
- Fixed a stale version check that prevented queued replies from starting. Both sides now read the manifest version. Setup now separates Ollama and Welo connection into clear numbered steps.
- Validation: nine queue scenarios, timeout/cancellation transport tests and actual content-script version responses passed. No live X reply was posted during testing.


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

