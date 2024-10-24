# Akbank-Fish-Species-Classification

Bu proje, Kaggle platformunda bulunan [balık](https://www.kaggle.com/datasets/crowww/a-large-scale-fish-dataset) veri setini kullanarak farklı balık türlerini sınıflandırmayı amaçlamaktadır. Proje kapsamında, balık görüntüleri üzerinde derin öğrenme yöntemleri kullanılarak sınıflandırma modeli geliştirilmiştir.

## Proje Özeti
- **Veri Seti:** 9000 görüntüden oluşan bir veri seti kullanılmıştır. Veri setinde farklı balık türlerini temsil eden görüntüler bulunmaktadır.
  
- **Veri Analizi:**
  - Veri setinin boyutu `(9000, 2)` olup, iki sütun içermektedir: `path` (görüntü yolu) ve `label` (balık türü).
  - Toplamda 9 farklı balık türü bulunmaktadır.
  - Veri analiz sürecinde, her balık türünden örnek görüntüler seçilerek görselleştirilmiş ve veri setinin dengesi değerlendirilmiştir. Her türden belirli sayıda örnek görüntü kullanılarak veri dengesi sağlanmaya çalışılmıştır.
  - Eğitim ve test verisi olarak veri seti, %80 eğitim ve %20 test olacak şekilde ayrılmıştır.
    
- **Modelleme:**
  - Yapay Sinir Ağı (ANN) modeli, TensorFlow ve Keras kullanılarak oluşturulmuştur.
  - Model, 128x128 boyutunda RGB balık görüntüleri üzerinde eğitim almıştır.
  - Model, üç gizli katmandan oluşmaktadır ve her katmanda `BatchNormalization` ve `Dropout` katmanları kullanılarak overfitting (aşırı öğrenme) önlenmeye çalışılmıştır.
  - Çıkış katmanında `softmax` aktivasyon fonksiyonu kullanılarak her bir balık türü için sınıflandırma yapılmıştır.
    
- **Eğitim:**
  - Model, %20 doğrulama verisi ile birlikte 20 epoch boyunca eğitilmiştir.
  - Eğitim sürecinde, `EarlyStopping` (erken durdurma) ve `ReduceLROnPlateau` gibi teknikler kullanılarak eğitim süresince modelin doğrulama doğruluğu (validation accuracy) izlenmiş ve en iyi model ağırlıkları korunmuştur.
  - Eğitim süreci boyunca doğruluk (accuracy) ve kayıp (loss) değerleri düzenli olarak izlenmiş ve model performansındaki iyileşmeler değerlendirilmiştir.
    
- **Sonuçlar:** Modelin doğrulama doğruluğu (validation accuracy) ve kaybı (validation loss) değerlendirilmiş, en iyi sonuçlar elde edilen model kullanılarak sınıflandırma başarıyla gerçekleştirilmiştir.

Proje detaylarına ve kodlarına ulaşmak için aşağıdaki bağlantıya tıklayabilirsiniz:
