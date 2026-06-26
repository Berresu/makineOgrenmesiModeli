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

---

## Eğitim Stratejisi ve Performans

Modelin geliştirilme sürecinde iki farklı yaklaşım test edilmiştir:

1.  **Klasik %80 Eğitim - %20 Test Ayrımı:** İlk denemelerde veri setindeki dengesizlikler ve sınırlı ayrım nedeniyle model hedeflediğimiz başarıya ulaşamamış, düşük performans göstermiştir.
2.  **5-Katlı Çapraz Doğrulama (5-Fold Cross-Validation) & SMOTE:** Modelin gerçek performansını görmek ve ezberlemeyi (overfitting) önlemek amacıyla veri seti SMOTE ile dengelenerek 5-Katlı Çapraz Doğrulama testine sokulmuştur. 

### Sonuçlar
Bu strateji sayesinde tüm algoritmalar **0.85'in üzerinde F-Skoruna** ulaşarak muazzam bir başarı göstermiştir. Özellikle **SVM** modelimiz gerçek hayat testlerinde (Antik Roma, Agatha Christie ve mitolojik eserler üzerinde) en tutarlı tahminleri üreten şampiyon model olmuştur.


<img width="781" height="657" alt="image" src="https://github.com/user-attachments/assets/98a89f68-18e8-4a28-8ef7-8e953a91c5e1" />

<img width="748" height="535" alt="image" src="https://github.com/user-attachments/assets/8d4c5485-7f7a-49a7-addc-25c027de76b2" />

<img width="742" height="652" alt="image" src="https://github.com/user-attachments/assets/76c51460-3e29-4780-abd4-e5ab8a3b4ae0" />

<img width="731" height="532" alt="image" src="https://github.com/user-attachments/assets/da813b47-7730-40b1-8834-560933919f0f" />

<img width="753" height="655" alt="image" src="https://github.com/user-attachments/assets/720b97ae-13b8-46ff-aca9-e75de0c1f945" />

<img width="707" height="528" alt="image" src="https://github.com/user-attachments/assets/1457601a-359f-4a29-a89e-6a6d26b4f957" />

<img width="750" height="655" alt="image" src="https://github.com/user-attachments/assets/5b741640-a498-403b-865b-974252af0efa" />

<img width="712" height="533" alt="image" src="https://github.com/user-attachments/assets/e7e833dc-ded6-418b-ab35-dafe41860897" />

---

## Kullanım (Hugging Face)
Bu model aynı zamanda canlı bir web arayüzüne dönüştürülmüştür. Kendi kitap özetlerinizle modeli test etmek için aşağıdaki platformu ziyaret edebilirsiniz:
🔗 (https://huggingface.co/spaces/berre00/book-genre-predictor)
