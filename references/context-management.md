# Bağlam yönetimi

## Hedef

Doğru karar vermeye yetecek en küçük, güvenilir bağlamı topla. Bağlamı azaltmak doğruluk, güvenlik veya gerekli doğrulamadan ödün vermek anlamına gelmez.

## Depoda çalışma

1. Kök dizini ve ilgili üst düzey klasörleri belirle; görevle ilgisiz kaynakları açma.
2. İstenen davranış için giriş noktasını ve çağrı zincirini arama ile bul. Önce dosya adlarını, sembolleri ve yapılandırma ipuçlarını kullan; tüm dosyaları sırayla okuma.
3. İlgili uygulama kodu, mevcut testleri ve davranışı belirleyen yapılandırma/dokümantasyon bölümlerini incele. Bir varsayımı sınamak için gereken dar bölümü oku.
4. Depoda izin varsa `git status` veya eşdeğer değişiklik görünümünü kontrol et; kullanıcının önceden yaptığı değişiklikleri koru.
5. Gerekli bir dosya ya da bilgi yoksa, erişilebilir değilse veya iki kanıt çelişiyorsa bunu belirt; yapıyı uydurma.

## Büyük depolar ve belgeler

- Önce hedef paketi/modülü, olası bağımlılık sınırlarını ve testlerin yerini saptayarak harita çıkar.
- Aramayı ilgili klasör, sembol, hata izi veya yapılandırma anahtarıyla daralt; sonuçlardan yalnızca çağrıya/bug'a/özelliğe etkili dosyaları oku.
- Uzun bir README/API belgesinde yalnızca ilgili başlıkları ve komşu örnekleri al; tamamını bağlama kopyalama.
- Semboller arası ilişki belirsizse bir adım dışarı genişlet; dosya kapsamını tek seferde tüm depoya yayma.
- Daha önce doğrulanmış, halen güncel bilgiyi tekrar toplama. Bağlam değiştiyse veya kanıt eskidiyse yeniden doğrula.

## Claude Chat ile dosya paylaşımı

Claude Chat'te yüklenen ya da yapıştırılan dosya ve metinlerle sınırlı ol. Eksik mimari ayrıntısını tahmin etmek yerine ilgili dosyayı iste. Kod parçacığı tek başına davranışı doğrulamaya yetmiyorsa gerekli çağıran/test/config dosyasını açıkça belirt. Dosya düzenleme veya test çalıştırma olanağı bu Skill'den varsayılmaz.
