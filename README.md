# Kalp Hastalığı Risk Tahmini – Bitirme Projesi 🎓🩺

Bu repo, **Yapay Zeka Akademisi** bünyesinde hazırladığım bitirme projesinin Jupyter Notebook çalışmasını içerir. Çalışmanın amacı, *UCI Heart Disease* veri setini kullanarak bireylerin kalp hastalığı riski taşıyıp taşımadığını makine öğrenimi algoritmalarıyla tahmin etmek ve en yüksek doğruluk–hata dengesini sağlayan modeli belirlemektir.

## İçerik
| Klasör / Dosya | Açıklama |
| -------------- | -------- |
| `elif_karadeniz_yapay_zeka_akademisi_bitirme_projesi.ipynb` | Projenin ana Jupyter Notebook'u |
| `data/` | Ham ve işlenmiş veri dosyaları (`heart.csv` vs.) |
| `figures/` | EDA ve model sonuçlarına ait grafikler |
| `requirements.txt` | Gerekli Python kütüphaneleri |

## Kullanılan Yöntem ve Teknolojiler
- **Python 3.10**
- **Pandas, NumPy, Matplotlib, Seaborn** – Veri işleme & görselleştirme  
- **Scikit‑learn** – Modelleme ve metrikler  
- **CatBoost, XGBoost** – Gradient boosting tabanlı algoritmalar  
- **Random Forest, SVM, KNN, Logistic Regression** – Klasik makine öğrenimi modelleri  
- **Jupyter Notebook** – Deneylerin yürütülmesi

## Proje Adımları
1. **Problem Tanımı & Veri Seti** – UCI Heart Disease veri setinin tanıtımı  
2. **Keşifsel Veri Analizi (EDA)** – Eksik değer analizi, görselleştirmeler, hedef değişken dönüşümü  
3. **Ön İşleme & Feature Engineering** – Eksik değer doldurma, kategorik kodlama, yeni değişken üretimi  
4. **Model Eğitimi & Değerlendirme** – 6 farklı algoritma, 5‑kat çapraz doğrulama  
5. **Sonuçların Karşılaştırılması** – ROC‑AUC, Accuracy, Precision‑Recall, Confusion Matrix  
6. **Modelin Pratik Kullanımı** – Yanlış negatiflerin azaltılması ve klinik senaryolara uygunluk  
7. **Sonuç & Gelecek Çalışmalar** – Model geliştirme, veri genişletme ve API entegrasyonu fikirleri

## Öne Çıkan Sonuçlar 📊
| Model | ROC‑AUC | Accuracy | Öne Çıkan Özellik |
| ----- | ------- | -------- | ----------------- |
| **CatBoost** | 0.925 | 0.8478 | Age, cp, thalach |
| **Random Forest** | 0.920 | 0.8478 | ca, thal, oldpeak |
| **SVM (RBF)** | 0.918 | 0.8424 | - |

> En yüksek ROC‑AUC skorunu elde eden **CatBoost**, sadece genel doğrulukta değil, aynı zamanda kritik yanlış negatifleri en aza indirerek sağlık alanındaki uygulamalar için güçlü bir aday olduğunu kanıtladı ve bu sayede klinik karar destek sistemlerine entegre edilerek erken teşhis süreçlerine katkı sağlayabilir.

## Bulgular ve Değerlendirme

- **Veri Analizi Bulguları:**  
  - `ca` ve `thal` değişkenlerinde yüksek oranda eksik veri tespit edildi. Bu eksiklikler uygun stratejilerle giderildi.  
  - Kalp hastalığı ile en güçlü ilişkili değişkenler arasında `cp`, `thalach`, `oldpeak` ve `ca` yer aldı.  
  - Kategorik değişkenlerin dağılımları incelenerek hedef değişkenle olan ilişkileri ortaya kondu.

- **Model Performans Değerlendirmesi:**  
  - CatBoost modeli, hem doğruluk oranı (%85) hem de ROC-AUC (0.92) ile en iyi sonuçları verdi.  
  - Random Forest modeli benzer doğruluk oranı sunsa da, CatBoost’un daha düşük yanlış negatif oranı sağlık açısından daha güvenli bulundu.  
  - KNN ve Logistic Regression gibi bazı klasik modeller, dengesiz veri dağılımı nedeniyle daha düşük performans gösterdi.

- **Klinik Uygulama Açısından:**  
  - Yanlış negatiflerin minimize edilmesi önceliklendirildi çünkü yanlış negatif bir tahmin, hasta bireyin risksiz kabul edilmesi anlamına gelmekte.  
  - Bu nedenle ROC-AUC ve recall değerleri, genel doğruluktan daha önemli metrikler olarak ele alındı.

---

Proje, sağlık verileri üzerinde makine öğrenimi algoritmalarının etkili bir şekilde nasıl uygulanabileceğini göstermekte ve gerçek dünya senaryolarına entegre edilebilecek bir temel sunmaktadır.
