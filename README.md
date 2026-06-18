# IMDB Film Yorumu Duygu Analizi

IMDB film yorumları üzerinde **ikili duygu sınıflandırması** (pozitif / negatif) yapan, yedi farklı makine öğrenmesi algoritmasını karşılaştırmalı olarak değerlendiren bir çalışma.

## İçerik

50.000 yorumluk dengeli IMDB veri seti üzerinde metin ön işleme, TF-IDF vektörizasyonu ve yedi sınıflandırma algoritmasının eğitimi ile karşılaştırması yapılmıştır. Lojistik regresyon hem `statsmodels` (istatistiksel yorumlanabilirlik için) hem de `sklearn` ile modellenmiş; GridSearchCV ile hiperparametre optimizasyonu, 10-katlı çapraz doğrulama, ROC/PR eğrileri ve hata analizi uygulanmıştır.

## Kullanılan Modeller

| Grup | Modeller | Optimizasyon |
|------|----------|--------------|
| Optimize | Lojistik Regresyon · Naive Bayes · SVM | GridSearchCV |
| Baseline | MLP · CART · Random Forest · Gradient Boosting | Varsayılan parametreler |

## Sonuçlar

**Optimize modeller**

| Model | Accuracy | F1-Score | ROC-AUC |
|-------|----------|----------|---------|
| Lojistik Regresyon | 0.9063 | 0.9067 | 0.9671 |
| SVM | 0.9049 | 0.9053 | 0.9672 |
| Naive Bayes | 0.8832 | 0.8839 | 0.9511 |

**Baseline modeller**

| Model | Accuracy | F1-Score | ROC-AUC |
|-------|----------|----------|---------|
| MLP | 0.8991 | 0.8991 | 0.9620 |
| Random Forest | 0.8585 | 0.8576 | 0.9341 |
| Gradient Boosting | 0.8119 | 0.8214 | 0.8993 |
| CART | 0.7216 | 0.7214 | 0.7216 |

En iyi model olarak **Lojistik Regresyon** önerilmektedir: en yüksek Accuracy/F1 skorunu vermesinin yanında `statsmodels` ile katsayıların istatistiksel olarak (p-değeri, güven aralığı, Pseudo-R²) yorumlanabilmesi avantaj sağlamaktadır.

## İş Akışı

1. Veri yükleme ve keşifsel veri analizi (EDA)
2. Metin ön işleme (HTML temizleme, tokenizasyon, stop word eleme, lemmatization)
3. Kelime bulutu ve frekans analizi
4. TF-IDF vektörizasyonu (bigram, 50.000 özellik) ve veri bölme
5. Model eğitimi, optimizasyon ve çapraz doğrulama
6. Model değerlendirme, karşılaştırma ve hata analizi

## Kullanılan Kütüphaneler

`numpy` · `pandas` · `matplotlib` · `seaborn` · `scikit-learn` · `statsmodels` · `nltk` · `textblob` · `wordcloud` · `beautifulsoup4`

## Veri Seti

[IMDB Dataset of 50K Movie Reviews](https://www.kaggle.com/datasets/lakshmipathi/imdb-dataset-of-50k-movie-reviews)

## Kullanım

```bash
pip install numpy pandas matplotlib seaborn scikit-learn statsmodels nltk textblob wordcloud beautifulsoup4
jupyter notebook IMDB_Film_Yorumu_Projesi.ipynb
```
