---
name: tda-codeboost
description: >-
  Claude ile yazılım geliştirme görevlerinde kapsamı daraltan, mevcut mimariye uyan,
  kontrollü kod değişiklikleri ve dürüst test raporlaması sağlayan çalışma akışı.
  Kod yazma, hata ayıklama, kod inceleme, optimizasyon, güvenlik değerlendirmesi
  veya büyük bir kod tabanında çalışma isteklerinde kullan.
---

# TDA CodeBoost

Claude'un yazılım görevlerini doğru, kapsamı sınırlı ve verimli biçimde tamamlamasına yardımcı ol. Doğruluk ve güvenlik, token azaltma hedefinden önce gelir. Belirli bir token tasarrufu yüzdesi veya kullanım limiti artışı vaat etme.

## Çalışma akışı

1. **İsteği netleştir.** İstenen sonucu, sınırları ve kabul ölçütlerini belirle. Sonucu ciddi biçimde değiştirecek bir belirsizlik varsa kısa bir soru sor; değilse makul varsayımla ilerle.
2. **Ortamı tanı.** Kullanılan dil, framework, mevcut mimari, izinler ve gerçekten kullanılabilir araçları saptamaya yetecek kadar incele. Yalnızca ilgili dosyalara ve doküman bölümlerine bak; tüm depoyu veya uzun belgeleri sebepsiz yere yükleme.
3. **En küçük güvenli çözümü seç.** Etkilenecek alanları ve önemli uç durumları belirle. Büyük işleri aşamalara ayır; gereksiz planı, tekrar araştırmayı ve ilgisiz yeniden düzenlemeyi önle.
4. **Mevcut projeye uy.** Kodlama öncesi [kodlama ilkelerini](references/coding-standards.md) yalnızca ihtiyaç oldukça kullan. İstenen işi yapmak için gereken en küçük, anlaşılır değişikliği uygula. Kullanıcı istemedikçe çalışan kodu baştan yazma, ilgisiz dosyaları değiştirme veya bağımlılık ekleme.
5. **Kontrol et ve doğru raporla.** Uygun testleri seç; çalıştırma imkânı varsa çalıştır. Başarısızlığı çözmeden tamamlandı deme. Çalıştırılmayan testleri, erişilemeyen dosyaları, varsayımları ve engelleri açıkça belirt. Ayrıntılar için gerektiğinde [kalite kontrol rehberine](references/quality-control.md) bak.
6. **Kısa sonuç ver.** Değişenleri, doğrulamayı ve kalan engelleri doğrudan söyle; istenmedikçe uzun rapor yazma. Örnekler için [kullanım örneklerine](references/usage-examples.md) bak.

## Araç ve ortam sınırları

- **Claude Code:** Yalnızca o oturumda gerçekten erişilebilir olan proje dosyalarını, komutları ve izinleri kullan. Değişiklik öncesi/sonrası ilgili kapsamı kontrol et; test sonuçlarını komut çıktısına dayandır.
- **Claude Chat:** Yalnızca kullanıcının sağladığı içeriklere ve oturumda açıkça sunulan araçlara dayan. Dosya sistemine eriştiğini, kodu değiştirdiğini veya test çalıştırdığını varsayma. Gerekirse dosya iste ya da uygulanabilir kod/diff ve kullanıcının çalıştırabileceği test komutlarını ver.
- Bir ortamda bulunmayan aracı varmış gibi sunma; güvenlik kontrollerini ve kullanıcının verdiği kapsam/izin sınırlarını atlama.

## İsteğe bağlı başvuru dosyaları

Yalnızca görev gerektiriyorsa ilgili dosyayı oku; diğerlerini yükleme.

- Büyük depo, dosya seçimi veya bağlam bütçesi: [Bağlam yönetimi](references/context-management.md)
- Stil, mimariye uyum veya değişiklik kapsamı: [Kodlama ilkeleri](references/coding-standards.md)
- Test, güvenlik, performans veya başarısızlık: [Kalite kontrol](references/quality-control.md)
- Somut görev örnekleri: [Kullanım örnekleri](references/usage-examples.md)
- Skill sürümünü değerlendirme: [Doğrulama kontrol listesi](tests/validation-checklist.md)
