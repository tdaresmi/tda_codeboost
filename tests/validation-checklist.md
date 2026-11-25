# TDA CodeBoost — değerlendirme kontrol listesi

Bu belge Skill'i elle değerlendirmek için hazırlanmıştır; tek başına Claude'da testlerin çalıştırıldığını kanıtlamaz.

## Karşılaştırma yöntemi

1. Güvenli, değişmeyen bir test deposu seç ve her iki denemede aynı commit'i/dosyaları kullan.
2. Her senaryo için aynı model, istek, izinler ve özelliklerle iki yeni Claude oturumu aç. Birinde Skill kapalı olsun (baseline), diğerinde açık olsun (CodeBoost).
3. Senaryoları birbirinden bağımsız çalıştır; bir oturumun yanıtını diğerine aktarma. Yanıtları, diff'leri, çalıştırılan komutları ve test çıktılarını sakla.
4. Aşağıdaki ölçütlerle iki sonucu da puanla. Eksik araç veya bağlamı sınırlama olarak not et; test başarısı gibi gösterme.
5. Gerçek token verisini yalnızca Claude ortamı bunu gerçekten sağlıyorsa kaydet. Aksi halde yalnızca gözlemlenebilir yaklaşık göstergeleri (ör. okunan ilgili dosya sayısı) karşılaştır; bunları token miktarına veya tasarruf yüzdesine dönüştürme.

## Sekiz senaryo

| # | İki denemede de kullanılacak senaryo/istek | Gözlemlenebilir beklenti |
|---|---|---|
| 1 | “Pozitif bir tam sayıyı doğrulayan ve true/false döndüren bir Python işlevi yaz; sınır durumlarını ele al.” | Doğru ve açık sözleşme ile ilgili sınır durumları. Test aracı varsa uygun testi çalıştır; yoksa çalıştırılamadığını açıkça söyle. |
| 2 | Büyük bir test deposunda tekrarlanabilir, belirli bir hatayı düzeltmesini iste. | Hedefli arama/okuma, nedenin açıklanması, küçük diff ve hataya yönelik test; deponun tamamını amaçsızca okuma. |
| 3 | Önceden belirlenmiş kapsamı olan “X özelliğini ekle; diğer dosyalara dokunma” isteğini ver. | Değişen yollar istenen kapsamda kalır; gerekçesiz refactor veya ilgisiz dosya değişikliği olmaz. |
| 4 | Verilen bir işlevi davranışını koruyarak optimize ettir. | Mevcut sözleşme/sınır durumları korunur; test veya benchmark yalnızca mümkünse çalıştırılır; ölçülmüş ve ölçülmemiş sonuçlar doğru anlatılır. |
| 5 | SQL sorgusu ve yetkilendirme kontrolü içeren kodu güvenlik açığı açısından incelet. | Neden/etkiyle desteklenen bulgular, doğrulanmış ve şüpheli sorunların ayrımı, kapsamı aşmayan sonuç. |
| 6 | Büyük bir depoda dosya listesi verilmeden çok modüllü bir sorunu araştırmasını iste. | Önce yapı haritası, ardından hedefli arama ve yalnızca gerekli dosyaların incelenmesi. |
| 7 | Başarısız bir test sağla; ardından hatayı düzeltip sonucu bildirmesini iste. | Gerçek çıktıyı okur; uygun düzeltmeyi dener; yeniden çalıştırıp geçmediği sürece “başarılı” demez; çözülmemişse açıkça söyler. |
| 8 | “Yalnızca ne değiştiğini ve test durumunu kısaca özetle” isteğini ver. | Gerekli dosyaları ve gerçek test durumunu içeren kısa, doğrudan yanıt; önemli risk veya başarısızlık saklanmaz. |

## Puanlama

Her senaryoda her ölçütü 0–2 puanla değerlendir: 0 = yok/yanlış, 1 = kısmi, 2 = tam ve kanıtlı. Gözlemlenmemiş sonuca 2 puan verme.

- **Doğruluk:** İstek ve mevcut kanıt doğru yorumlanmış.
- **Test raporu:** Gerçek test sonucu, çalıştırılmadığı veya engel olduğu doğru belirtilmiş.
- **Bağlam seçimi:** Yeterli ve ilgili dosyalar/bilgiler kullanılmış; açıkça gereksiz içerikten kaçınılmış.
- **Değişiklik kapsamı:** Diff istenen/gerekli sınırda kalmış. Kod değişikliği gerektirmeyen senaryoda, göreve uygun kapsamı değerlendir.
- **Yanıt ekonomisi:** Yanıt uygulanabilir ve kısa; gerekli teknik gerekçe kaybolmamış.

Her senaryo en fazla 10, tüm set 80 puandır. Raporunda baseline ve CodeBoost puanlarını ölçüt ve senaryo bazında karşılaştır; gerçek diff'leri, test çıktılarını ve kalite ödünleşimlerini belirt. Doğruluk düşmüşse daha az bağlamı tek başına başarı sayma. Bir değerlendirici ilk çıktıları saklasın ki puanlar denetlenebilsin.

## Sonuç kaydı

| # | Baseline /10 | CodeBoost /10 | Kanıta veya sınırlamaya dayalı temel fark |
|---|---:|---:|---|
| 1 |  |  |  |
| 2 |  |  |  |
| 3 |  |  |  |
| 4 |  |  |  |
| 5 |  |  |  |
| 6 |  |  |  |
| 7 |  |  |  |
| 8 |  |  |  |

**Bu paketteki yürütme durumu:** Senaryolar gerçek Claude Chat veya Claude Code oturumlarında çalıştırılmamıştır; bu yapım sırasında bu ortamlar erişilebilir değildi. Proje yapısı, metadata, dosyalar ve paket yerel otomatik/elle kontrollerden geçirilmiştir. Bu kontroller gerçek Claude davranışının karşılaştırmalı değerlendirmesi değildir.
