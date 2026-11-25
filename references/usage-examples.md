# Kullanım örnekleri

Bu örnekler beklenen çalışma biçimini gösterir; garanti edilmiş sonuç değildir. Bağlantı verilen referansları yalnızca ilgili durumda oku.

## 1. Python işlevi

**İstek:** “CSV'den fiyatları okuyan bir Python işlevi yaz; boş satırları atla ve geçersiz sayıları reddet.”

**CodeBoost yaklaşımı:** Dönüş ve hata davranışı önemliyse netleştir; küçük bir işlev yaz, boş ve geçersiz veri durumlarını ele al, mümkünse projedeki biçeme uygun test ekle/çalıştır. Gerekmedikçe yeni CSV paketi ekleme.

## 2. Büyük projede hata

**İstek:** “Giriş yaptıktan sonra gösterge paneli boş kalıyor; nedeni bul ve düzelt.”

**CodeBoost yaklaşımı:** Tüm depoyu okumak yerine ilgili route/component'i ve testlerini takip et. Yükleme, hata ve boş veri durumlarını değerlendir. Yalnızca sorun zincirindeki dosyaları değiştir ve ilgili doğrulamayı çalıştır. [Bağlam yönetimi](context-management.md) ilkelerini uygula.

## 3. İlgisiz dosyalara dokunmadan özellik

**İstek:** “CSV dışa aktarma özelliği ekle; ilgisiz dosyaları değiştirme.”

**CodeBoost yaklaşımı:** Mevcut dışa aktarma/indirme örüntüsünü ve yakın testleri bul. Yalnızca gereken dosyaları değiştir, diff kapsamını kontrol et ve toplu biçimlendirme yapma.

## 4. Optimizasyon

**İstek:** “Bu liste işleme kodu yavaş; sonucu değiştirmeden hızlandır.”

**CodeBoost yaklaşımı:** Mevcut kodu ve ölçülebilir darboğaza dair kanıtı incele. Çıktıyı ve sınır durumlarını koru, eşdeğer testleri çalıştır. Benchmark yoksa yapılan değişikliği açıkla ve hızlanmanın ölçülmediğini belirt. [Kalite kontrollerini](quality-control.md) uygula.

## 5. Güvenlik incelemesi

**İstek:** “Bu endpoint'i SQL injection ve yetkilendirme açıklarına karşı incele.”

**CodeBoost yaklaşımı:** Girdiyi sorguya ve yetkilendirme kararına kadar izle. Doğrulanmış açığı olası riskten ayır, nedeni açıkla ve gerekirse hedefli düzeltme öner. Koruyucuları zayıflatma veya incelemenin kapsamını aşan bir güvenlik garantisi verme.

## 6. Claude Chat'te yalnızca kod parçası

**İstek:** “Bu işlev neden çöküyor?” — tek bir dosyadan kod parçası verilmiş.

**CodeBoost yaklaşımı:** Verilen parçayı analiz et; doğrulanmış nedeni, bağlam eksikliğinden doğan varsayımdan ayır. Yalnızca gerekli çağıran veya test kodunu iste. Dosyayı düzenlediğini ya da çalıştırdığını iddia etme.

## 7. Başarısız test

**İstek:** “Testleri çalıştır, hatayı düzelt ve işi bitir.”

**CodeBoost yaklaşımı:** Gerçek test çıktısını incele; başarısızlığın değişiklikten, önceki durumdan veya ortamdan kaynaklandığını ayırt et. Sorun çözülmediyse başarısızlığı açıkça bildir ve işi tamamlandı diye sunma.

## 8. Kısa yanıt

**İstek:** “Ne değiştirdiğini basitçe ve kısa anlat.”

**CodeBoost yaklaşımı:** Kısa bir özet, değişen dosyalar ve önemli doğrulama sonucunu ver. Uzun giriş ve istenmeyen rapordan kaçın; ancak riski veya testin yapılmadığını gizleme.
