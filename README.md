# Makine Öğrenmesi ile Kitap Türü Tahmini (Book Genre Predictor)

Bu proje, kitapların İngilizce arka kapak veya özet metinlerini analiz ederek hangi edebi türe ait olduğunu tahmin eden akademik standartlarda bir doğal dil işleme (NLP) ve makine öğrenmesi modelidir.

## Proje Hakkında
Proje kapsamında metin verileri TF-IDF yöntemiyle vektörleştirilmiş, veri kümesindeki sınıf dengesizliklerini gidermek için **SMOTE (Synthetic Minority Over-sampling Technique)** kullanılmış ve en doğru sınıflandırılamayı bulmak için 4 farklı algoritma birbiriyle yarıştırılmıştır.

### Kullanılan Algoritmalar
* **Multinomial Naive Bayes (NB)**
* **Logistic Regression**
* **Destek Vektör Makineleri (SVM)** — *Projenin Şampiyon Modeli*
* **Rastgele Orman (Random Forest)**

---

## Veri Seti (Dataset)
Modelin eğitim ve test süreçlerinde Kaggle üzerinde yer alan, Atharva Inamdar'a ait **Book Genre Prediction** veri seti kullanılmıştır. Veri seti içerisinde aşağıdaki 10 farklı edebi tür bulunmaktadır:

* Fantasy (Fantastik)
* Crime (Suç/Polisiye)
* History (Tarih)
* Horror (Korku)
* Psychology (Psikoloji)
* Romance (Romantik)
* Science Fiction (Bilimkurgu)
* Sports (Spor)
* Thriller (Gerilim)
* Travel (Gezi)

> *Buraya veri setinin dağılım grafiğini ekleyebilirsin:*
> ![Veri Seti Dağılımı](BURAYA_GRAFİK_LİNKİ_GELECEK)

---

## Eğitim Stratejisi ve Performans

Modelin geliştirilme sürecinde iki farklı yaklaşım test edilmiştir:

1.  **Klasik %80 Eğitim - %20 Test Ayrımı:** İlk denemelerde veri setindeki dengesizlikler ve sınırlı ayrım nedeniyle model hedeflediğimiz başarıya ulaşamamış, düşük performans göstermiştir.
2.  **5-Katlı Çapraz Doğrulama (5-Fold Cross-Validation) & SMOTE:** Modelin gerçek performansını görmek ve ezberlemeyi (overfitting) önlemek amacıyla veri seti SMOTE ile dengelenerek 5-Katlı Çapraz Doğrulama testine sokulmuştur. 

### Sonuçlar
Bu strateji sayesinde tüm algoritmalar **0.85'in üzerinde F-Skoruna** ulaşarak muazzam bir başarı göstermiştir. Özellikle **SVM** modelimiz gerçek hayat testlerinde (Antik Roma, Agatha Christie ve mitolojik eserler üzerinde) en tutarlı tahminleri üreten şampiyon model olmuştur.

> *Buraya modellerin başarı grafiklerini, Karmaşıklık Matrisini (Confusion Matrix) veya ROC eğrilerini ekleyebilirsin:*
> ![Karmaşıklık Matrisi](BURAYA_MATRİS_GRAFİK_LİNKİ_GELECEK)
> ![ROC Eğrisi](BURAYA_ROC_GRAFİK_LİNKİ_GELECEK)

---

## Kullanım (Hugging Face)
Bu model aynı zamanda canlı bir web arayüzüne dönüştürülmüştür. Kendi kitap özetlerinizle modeli test etmek için aşağıdaki platformu ziyaret edebilirsiniz:
🔗 [Hugging Face Space Uygulama Linki](BURAYA_HUGGING_FACE_SPACE_LİNKİNİ_YAPIŞTIR)
