# Kodlama ilkeleri

## Mevcut projeye uyum

- Dil, framework sürümü, biçimlendirme, adlandırma, hata yönetimi ve test desenlerini yakındaki çalışan koddan çıkar.
- Mevcut yardımcı işlev veya bağımlılık işi karşılıyorsa onu tercih et; yeni bağımlılık eklemeden önce gerekliliği ve maliyetini değerlendir.
- Kullanıcı açıkça istemedikçe biçimlendirme dalgası, yeniden adlandırma, kapsam dışı refactor veya yeni özellik ekleme.

## Değişikliği tasarlama

- İstenen davranışa ulaşan en küçük, okunabilir değişikliği yap; ancak tek satır/az kodu amaç haline getirip doğruluğu ve açıklığı düşürme.
- Arayüzleri, veri biçimlerini, hata semantiğini ve geriye dönük uyumluluğu koru; değiştirmek gerekiyorsa etkisini açıkla.
- Hata düzeltmesinde kök nedeni hedefle. Özellikte mevcut örüntülere ve kabul ölçütlerine uy.
- Tekrarlanan mantığı azalt, fakat tek kullanım için gereksiz soyutlama kurma.

## Güvenlik ve dayanıklılık

- Girdi doğrulama, yetkilendirme, hassas veri, enjeksiyon, yol/komut güvenliği ve güvenli varsayılanları ilgili bağlamda gözden geçir.
- Uç değerleri, boş/null girdi, hata yolları, yarış koşulları ve kaynak sınırlarını etkisine göre ele al.
- Sırları kaynak koda, loglara veya kullanıcıya açık çıktıya koyma. Güvenlik açığını “token verimliliği” gerekçesiyle atlama.

## İzin ve kapsam

Yalnızca kullanıcının yetkilendirdiği dosya ve kapsamda değişiklik yap. Önceden var olan kullanıcı değişikliklerini üzerine yazma. Gerekli değişikliğin kapsamı geniş veya kırıcı görünüyorsa önce etkisini değerlendir ve gerekliyse kullanıcıdan karar iste.
