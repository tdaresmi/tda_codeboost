# Kalite kontrolü

## Değişiklik öncesi

- İsteği gözlemlenebilir kabul ölçütlerine dönüştür.
- Projedeki testleri, lint/tür denetimi komutlarını ve yakındaki değişiklik örneklerini bul.
- Riskle orantılı doğrulama seç; önemli sınır durumlarını, hata yollarını, güvenliği ve gerektiğinde performansı değerlendir.
- Testlerin mevcut, başarılı veya çalıştırılabilir olduğunu varsayma.

## Değişiklik sonrası

1. Kendi diff'ini inceleyerek kazara veya ilgisiz değişiklikleri, yeni bağımlılıkları, gizli bilgileri, hata yönetimini ve proje stilinden sapmaları denetle.
2. En yakın anlamlı testi çalıştır; gerekiyorsa daha geniş test takımına geç. Başarısızlığı gizlemek için testleri kaldırma.
3. Bir denetim başarısızsa bunun yeni değişiklikten mi, önceden var olan bir durumdan mı, yoksa ortam engelinden mi kaynaklandığını ayırt et. Değişikliğinin yol açtığı sorunu düzelt ve yeniden dene.
4. Gerçekte çalıştırılmamış bir testi başarılı diye bildirme. Test çalıştırılamıyorsa nedenini ve uygulanabilir komut ya da sonraki adımı belirt.
5. Ölçüm olmadan performans artışı iddia etme. Karşılaştırma yapıyorsan aynı ortamı, girdileri ve ölçüm yöntemini kullan.

## Raporlama

Nelerin değiştiğini, hangi denetimin gerçekten çalıştırılıp ne sonuç verdiğini, nelerin doğrulanmadığını ve kalan engelleri kısaca açıkla. “Geçti”, “başarısız”, “çalıştırılmadı” ve “statik inceleme” durumlarını birbirinden ayır. Claude Chat'te dosya veya çalıştırma aracı yoksa yalnızca gerekçelendirilebilen analizi sun; yapılmamış değişiklik ya da test iddiasında bulunma.
