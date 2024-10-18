# Balık Türleri Sınıflandırma Projesi

## Proje Amacı
Bu proje, görüntü işleme tekniklerini kullanarak farklı balık türlerini sınıflandırmayı amaçlamaktadır. Veri seti, 9 farklı balık türüne ait toplam 9000 görüntü içermektedir. Proje, derin öğrenme yöntemleri ile balık türlerini doğru bir şekilde tanımlamayı hedefler.

## Veri Seti
Veri seti, her biri farklı özelliklere sahip olan 9 balık türüne ait görüntüleri içermektedir. Her türden eşit sayıda örnek bulunması, modelin dengeli bir şekilde eğitilmesini sağlamaktadır.

### Veri Setinin Sütunları:
- Görüntü: Balık türlerine ait görsel veriler.
- Etiket: Balık türünü belirten sınıf bilgisi.

### Veri Setinin Genel Bilgileri:
- Toplam Görüntü Sayısı: 9000
- Sınıf Sayısı: 9

### Özet İstatistikler:
- Her tür için ortalama görüntü sayısı: 1000

## Keşifsel Veri Analizi (EDA)
Veri analizi aşamasında aşağıdaki grafikler oluşturulmuştur:
- **Sınıf Dağılımı:** Her balık türünün temsil oranlarını gösterir.
- **Görsel Örnekler:** Her tür için rastgele seçilmiş görüntüler.

## Veri Ön İşleme
Veri seti, eğitim ve test setlerine ayrılmıştır. Eğitim seti %80 (%7200 görüntü) ve test seti %20 (%1800 görüntü) oranıyla belirlenmiştir. Ayrıca, görüntü boyutları normalize edilerek modelin daha iyi öğrenmesi sağlanmıştır.

## Hiperparametre Optimizasyonu
Modelimin performansını iyileştirmek amacıyla farklı hiperparametreler üzerinde çeşitli denemeler yaptım:

- **Katman Sayısı ve Düğüm Sayısı:** Katman sayısını artırmanın belirli bir noktadan sonra modelin performansını iyileştirmediğini gözlemledim. Bu, aşırı karmaşık modellerin overfitting'e yol açabileceğini gösterdi. Optimal bir denge sağladım. Düğüm sayısını artırıp azaltarak performanstaki değişiklikleri dikkatle inceledim. Aşırı sayıda düğüm, modelin genelleme kapasitesini düşürdü, bu nedenle bu parametreyi de dengeli bir seviyede tutmaya karar verdim.

- **Dropout Oranı:** Dropout oranını %0.2 ve %0.5 arasında uygulayarak overfitting'i engellemeye çalıştım. Bu oranlar, modelin daha iyi genelleme yapmasını sağladı.

- **Optimizer Seçimi:** Farklı optimizer algoritmaları (Adam, RMSprop, SGD) denedim. En iyi sonuçları Adam optimizer ile elde ettim, çünkü bu optimizer modelin öğrenme hızını dengeli bir şekilde ayarlayarak daha hızlı ve stabil bir eğitim sağladı.

- **Eğitim ve Validasyon Performansı:** Modelimin overfit etmediğinden emin olmak için eğitim ve validasyon doğruluklarını ve kayıplarını karşılaştırdım. Eğitim ve validasyon doğruluğunun yakın olması, modelin genelleme yeteneğinin iyi olduğunu gösterdi.

Bu süreçte, elde ettiğim bulguları markdown hücrelerimde detaylandırarak tüm deneme ve sonuçları adım adım açıklamaya özen gösterdim. Modelin performansı optimize edildiğinde, elde edilen sonuçlar tatmin edici bir noktaya ulaştı ve en iyi modelimi seçmiş oldum.

## Sonuçlar
### Model Performansı
Aşağıda kullanılan model ve ilgili performans skoru verilmiştir:
- **Yapay Sinir Ağı:**
  - Eğitim Doğruluğu: %98.95
  - Test Doğruluğu: %98.33
  - Eğitim Kaybı: 0.0529
  - Test Kaybı: 0.0659

### Temel Bulgular
- Model, eğitim sürecinde %34.61'den %98.95'e kadar doğruluk oranı elde ederek yüksek bir öğrenme kapasitesine sahip olduğunu göstermiştir.
- Confusion matrix ile yapılan analiz, modelin sınıflar arasındaki ayırımı ne kadar iyi yaptığını ortaya koymuştur.

## Sonuç
Bu proje, derin öğrenme teknikleri ile balık türlerini başarıyla sınıflandırmıştır. En iyi performansı sağlayan model, %98.33 test doğruluğu ile yüksek bir başarı sergilemiştir. Gelecekte, daha da yüksek doğruluk oranları elde edilebilir.

## Veri Seti ve Kaggle 
Bu proje, balık türlerini sınıflandırmak için kullanılan veri setini içermektedir. Veri seti hakkında detaylı bilgiye [Kaggle veri seti sayfasından](https://www.kaggle.com/code/kadiraltiparmak/a-large-scale-fish-dataset-nlp) ulaşabilirsiniz.
