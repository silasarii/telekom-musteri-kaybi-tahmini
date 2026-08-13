# Telekom Sektöründe Müşteri Kaybının Tahmini

Bu proje, telekom sektöründe müşterilerin hizmeti bırakma (`Churn`) olasılığını tahmin etmek amacıyla gerçekleştirilmiş uçtan uca bir veri bilimi çalışmasıdır.

Proje kapsamında veri temizleme, keşifsel veri analizi, veri ön işleme, farklı makine öğrenmesi modellerinin karşılaştırılması ve final modelin hata analizi gerçekleştirilmiştir.

## 📌 Proje Amacı

Telekom şirketleri için müşteri kaybını önceden tahmin etmek, müşteri elde tutma stratejilerinin geliştirilmesi açısından önemlidir.

Bu projede temel amaç:

- Müşteri kaybıyla ilişkili faktörleri incelemek
- Müşteri profillerindeki farklılıkları analiz etmek
- Churn tahmini yapabilecek sınıflandırma modelleri geliştirmek
- Modelleri farklı performans metrikleriyle karşılaştırmak
- En uygun modeli seçmek
- Modelin yaptığı hataları iş problemi açısından değerlendirmek

## 📊 Veri Seti

Projede **IBM Telco Customer Churn** veri seti kullanılmıştır.

- Başlangıç kayıt sayısı: **7.043**
- Değişken sayısı: **21**
- Hedef değişken: **Churn**
- Temizleme sonrası kayıt sayısı: **7.032**

`TotalCharges` değişkeninde bulunan 11 eksik kayıt incelenmiş ve bu kayıtların tamamında `tenure = 0` olduğu görülmüştür. Bu nedenle ilgili kayıtlar veri setinden çıkarılmıştır.

## 🔎 Proje Süreci

Proje aşağıdaki aşamalardan oluşmaktadır:

1. Veri Setini Tanıma
2. Veri Temizleme
3. Keşifsel Veri Analizi (EDA)
4. Veri Ön İşleme
5. Makine Öğrenmesi Modeli
6. Model Değerlendirmesi ve Hata Analizi

## 🤖 Kullanılan Modeller

Müşteri kaybı tahmini için dört farklı sınıflandırma algoritması karşılaştırılmıştır:

- Logistic Regression
- Random Forest
- K-Nearest Neighbors (KNN)
- Decision Tree

Karşılaştırma sonucunda **Logistic Regression** final model olarak seçilmiştir.

## 📈 Final Model Performansı

Logistic Regression modelinin test sonuçları:

| Metrik | Sonuç |
|---|---:|
| Accuracy | %80,53 |
| Precision | %65,15 |
| Recall | %57,49 |
| F1-Score | %61,08 |
| ROC-AUC | 0,8361 |
| Average Precision | 0,6230 |

Confusion Matrix sonuçları:

- True Negative (TN): 918
- True Positive (TP): 215
- False Positive (FP): 115
- False Negative (FN): 159

Özellikle **False Negative** değerlerinin müşteri kaybı açısından önemli olduğu değerlendirilmiştir. Çünkü bu müşteriler gerçekte ayrılmasına rağmen model tarafından doğru şekilde tespit edilememiştir.

## 💡 Öne Çıkan Bulgular

Keşifsel veri analizi sonucunda bazı müşteri gruplarında belirgin Churn farklılıkları gözlemlenmiştir.

Örneğin:

- Aylık sözleşmeye sahip müşterilerde Churn oranı: **%42,7**
- İki yıllık sözleşmeye sahip müşterilerde Churn oranı: **%2,8**
- Fiber optik kullanıcılarında Churn oranı: **%41,9**
- DSL kullanıcılarında Churn oranı: **%19,0**

Lojistik Regresyon katsayıları incelendiğinde ise `Contract_Two year`, `tenure` ve `InternetService_Fiber optic` değişkenleri öne çıkmıştır.

Bu ilişkiler nedensellik olarak değil, veri içerisindeki ilişkiler ve modelin tahmin yaparken kullandığı değişkenlerin yönü olarak değerlendirilmiştir.

## 🛠️ Kullanılan Teknolojiler

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
- GitHub

## 📁 Proje Yapısı

```
├── data/
│   ├── WA_Fn-UseC_-Telco-Customer-Churn.csv
│   ├── telco_temiz.csv
│   ├── X_train.csv
│   ├── X_test.csv
│   ├── y_train.csv
│   ├── y_test.csv
│   ├── model_karsilastirma.csv
│   └── lojistik_regresyon_tahminleri.csv
│
├── notebooks/
│   ├── 01_Veri_Setini_Tanıma.ipynb
│   ├── 02_Veri_Temizleme.ipynb
│   ├── 03_Kesifsel_Veri_Analizi.ipynb
│   ├── 04_Veri_On_İsleme.ipynb
│   ├── 05_Makine_Ogrenmesi_Modeli.ipynb
│   └── 06_Model_Degerlendirmesi.ipynb
│
└── README.md
```

## 📝 Detaylı Proje Yazısı

👉 [Telekom Sektöründe Müşteri Kaybının Tahmini: Uçtan Uca Bir Veri Bilimi Projesi](https://medium.com/@silasari/telekom-sekt%C3%B6r%C3%BCnde-m%C3%BC%C5%9Fteri-kayb%C4%B1n%C4%B1n-tahmini-u%C3%A7tan-uca-bir-veri-bilimi-projesi-09669211926e)

<div align="center">

### 👤 Sıla Sarı
🎓 **Dokuz Eylül Üniversitesi - Ekonometri**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sıla-sarı-5293451a4)
