<div class="cover">
<div class="university">USKUDAR UNIVERSITESI</div>
<div class="faculty">MUHENDISLIK VE DOGA BILIMLERI FAKULTESI</div>
<div class="course">YAPAY ZEKA DERSI - FINAL PROJESI</div>
<div class="title-main">RADYOMIK OZELLIKLER KULLANILARAK<br>PAPILODEM IKILI SINIFLANDIRMASI</div>
<div class="subtitle">Patient-Level Cross-Validation, MRMR Feature Selection, Calibrated Soft-Voting Ensemble</div>
<div class="author-block">
<div class="author-name">Hazirlayan: Goksel SAGIROGLU</div>
<div class="author-email">vespula.tr@gmail.com</div>
</div>
<div class="date">Haziran 2026</div>
</div>
<div class="abstract-page" markdown="1">
## OZET

Papilodem, intrakraniyal basincin yukselmesine bagli olarak gelisen bilateral optik disk sismesi olarak tanimlanmakta ve sebep oldugu olasi gorme kayiplari nedeniyle erken tanisi kritik onem tasimaktadir. Klinikte papilodem ile sahte papilodem arasindaki ayrimin uzman degerlendirmesine dayanmasi tani tutarliligini sinirlamaktadir [3] [12]. Bu calismada, optik diskten elde edilmis 746 radyomik ozellik kullanilarak makine ogrenmesi tabanli bir ikili siniflandirma sistemi gelistirilmistir. Veri seti 69 hastaya (48 normal, 21 papilodem) ait toplam 966 ornek icermektedir. Calismada hasta seviyesinde veri sizintisini engellemek amaciyla GroupShuffleSplit ile 10 dis tekrar ve StratifiedGroupKFold ile 5 ic kat capraz dogrulama kullanilmistir. Median imputation, dusuk varyans ve Pearson korelasyon esikli ozellik elemesi, RobustScaler olcekleme ve MRMR ozellik secimi adimlari, Optuna TPE ile hiperparametre optimizasyonu icinde, alti farkli siniflandirici (Lojistik Regresyon, RBF cekirdekli SVM, Rastgele Orman, ExtraTrees, Gradient Boosting, KNN) ve soft voting topluluk modeli ile uygulanmistir. Sigmoid kalibrasyon ve F1 maksimum esik secimi ile test asamasinda kullanilan model olasiliklarinin guvenilirligi saglanmistir. Sonuc olarak en yuksek ortalama makro-F1 degerine RBF cekirdekli SVM modeli ile ulasilmis (0.875 +/- 0.057), tek tekrar bazinda en iyi degeri yine SVM uretmistir (0.951). Friedman testi modeller arasinda anlamli bir genel fark bulundugunu (chi-kare = 15.83, p = 0.0147) gostermistir. SHAP tabanli yorumlanabilirlik analizi ile en bilgilendirici ozellikler raporlanmistir.


**Anahtar Kelimeler:** Radyomik, Papilodem, Ikili Siniflandirma, Hasta Seviyesinde Capraz Dogrulama, MRMR, Optuna, Kalibrasyon, SHAP.
</div>
<div class="abstract-page" markdown="1">
## ABSTRACT

Papilledema is defined as bilateral optic disc swelling caused by elevated intracranial pressure, and its prompt diagnosis is clinically important to avoid permanent vision loss. The differentiation between papilledema and pseudopapilledema is challenging and traditionally relies on expert interpretation [3] [12]. In this study, a machine learning based binary classification system was developed using 746 radiomic features extracted from the optic disc. The dataset contains 966 samples obtained from 69 subjects (48 normal, 21 papilledema). To prevent patient-level data leakage, GroupShuffleSplit with 10 outer repeats and StratifiedGroupKFold with 5 inner folds were used. Median imputation, low-variance filtering, Pearson correlation pruning, RobustScaler normalisation and MRMR feature selection were embedded in a sklearn Pipeline. Six base classifiers (Logistic Regression, RBF SVM, Random Forest, ExtraTrees, Gradient Boosting, KNN) were tuned using Optuna TPE sampler with 50 trials per model, then combined with soft voting. Sigmoid calibration and F1-maximising threshold optimisation were applied so that the probability outputs used at test time are well calibrated. The RBF SVM achieved the highest mean macro-F1 (0.875 +/- 0.057) and the best single-repeat macro-F1 (0.951). Friedman test confirmed a global difference among models (chi-square = 15.83, p = 0.0147). SHAP analysis identified the most informative features.


**Keywords:** Radiomics, Papilledema, Binary Classification, Patient-Level Cross-Validation, MRMR, Optuna, Calibration, SHAP.
</div>
<div class="toc" markdown="1">
## ICINDEKILER

| Bolum | Baslik |
|:-----:|:-------|
| | OZET |
| | ABSTRACT |
| | ICINDEKILER |
| | SEKILLER LISTESI |
| | TABLOLAR LISTESI |
| | KISALTMALAR |
| 1 | GIRIS |
| 1.1 | Problemin Tanimi ve Onemi |
| 1.2 | Calismanin Amaci ve Katkilari |
| 2 | LITERATUR TARAMASI |
| 2.1 | Papilodem Goruntuleme Tabanli Tani |
| 2.2 | Radyomik Veri ile Siniflandirma |
| 3 | MATERYAL VE YONTEM |
| 3.1 | Veri Seti |
| 3.2 | Veri On Isleme |
| 3.3 | Ozellik Secimi (MRMR) |
| 3.4 | Siniflandirma Modelleri |
| 3.5 | Hiperparametre Optimizasyonu |
| 3.6 | Capraz Dogrulama Yapisi |
| 3.7 | Kalibrasyon ve Esik Optimizasyonu |
| 3.8 | Topluluk Ogrenmesi (Ensemble) |
| 3.9 | Degerlendirme Metrikleri |
| 3.10 | Istatistiksel Analiz |
| 4 | BULGULAR |
| 4.1 | Genel Performans Karsilastirmasi |
| 4.2 | Istatistiksel Karsilastirma |
| 4.3 | Kalibrasyon Analizi |
| 4.4 | Ozellik Yorumlanabilirligi (SHAP) |
| 5 | TARTISMA |
| 6 | SONUC VE ONERILER |
| | KAYNAKLAR |

</div>
<div class="list-page" markdown="1">
## SEKILLER LISTESI

- **Sekil 3.1.** Calismada uygulanan veri akisi diyagrami
- **Sekil 4.1.** Modeller arasi ortalama makro-F1 karsilastirmasi
- **Sekil 4.2.** ROC egrileri (tum modeller, 10 outer repeat ortalamasi)
- **Sekil 4.3.** Precision-Recall egrileri
- **Sekil 4.4.** Karisiklik matrisi (en iyi model, en iyi tekrar)
- **Sekil 4.5.** Kalibrasyon egrileri (sigmoid Platt sonrasi)
- **Sekil 4.6.** Ozellik kararliligi: MRMR secim frekansi
- **Sekil 4.7.** SHAP ozet grafigi (ExtraTrees uzerinde)


## TABLOLAR LISTESI

- **Tablo 3.1.** Sinif dagilimi ve hasta sayilari
- **Tablo 3.2.** Optuna hiperparametre arama uzaylari
- **Tablo 4.1.** Modellerin tum metriklerde performansi (mean +/- std)
- **Tablo 4.2.** Macro-F1 siralamasi
- **Tablo 4.3.** Wilcoxon pairwise testi (Bonferroni duzeltmeli)
- **Tablo 4.4.** SHAP analizinde en yuksek katkili ilk 10 ozellik


## KISALTMALAR

| Kisaltma | Acilim |
|:--------:|:-------|
| AUC | Area Under Curve (Egri Alti Alan) |
| CV | Cross-Validation (Capraz Dogrulama) |
| ET | Extra Trees |
| GB | Gradient Boosting |
| KNN | K-Nearest Neighbors (K-En Yakin Komsu) |
| LR | Logistic Regression (Lojistik Regresyon) |
| MRMR | Minimum Redundancy Maximum Relevance |
| OKT | Optik Koherens Tomografi |
| ONH | Optic Nerve Head (Optik Sinir Basi) |
| PR | Precision-Recall |
| RF | Random Forest (Rastgele Orman) |
| ROC | Receiver Operating Characteristic |
| SHAP | SHapley Additive exPlanations |
| SVM | Support Vector Machine (Destek Vektor Makinesi) |
| TPE | Tree-structured Parzen Estimator |

</div>
## 1. GIRIS

### 1.1. Problemin Tanimi ve Onemi

Papilodem, intrakraniyal basincin yukselmesine bagli olarak gelisen ve bilateral optik disk sismesi seklinde kendini gosteren bir tablodur [12]. Klinik pratikte papilodemin sahte papilodem (pseudopapilledem) ile karistirilmasi sik karsilasilan bir durum olup, dogru tani saglanamadiginda gereksiz invaziv girisimlere ya da daha agir olarak gorme kaybiyla sonuclanan gecikmis mudahalelere yol acabilmektedir [3]. Geleneksel olarak tani fundus fotografi veya optik koherens tomografi (OKT) goruntulerinin uzman gozlemine dayanmakta, bu durum hem deneyim farklarindan kaynaklanan tutarsizliklara hem de uzun degerlendirme surelerine yol acmaktadir.

Son yillarda goruntuleme verisinden cikartilan radyomik ozellikler (birinci ve ikinci dereceden istatistikler, doku ozellikleri, sekil tanimlayicilari vb.) makine ogrenmesi yontemleriyle birlestirildiginde, uzman gozlemi olmaksizin yuksek dogruluklu tani sistemleri kurulabildigi gosterilmistir [1] [6]. Radyomik veride en buyuk teknik zorluk yuksek boyutluluk (sample basina yuzlerce ozellik) ile gorece kucuk hasta kohortlarinin bir arada bulunmasidir. Bu durum overfitting riskini arttirmakta ve ozellik secimi, kalibrasyon ve hasta seviyesinde sizintinin engellenmesi gibi metodolojik dikkat noktalarini one cikarmaktadir.

### 1.2. Calismanin Amaci ve Katkilari

Bu calismanin amaci, verilen radyomik veri seti uzerinde Normal ile Papilodem siniflarini ayirt etmek uzere akademik standartlara uygun, veri sizintisiz, kalibrasyonlu ve yorumlanabilir bir makine ogrenmesi pipeline'inin tasarlanmasi ve degerlendirilmesidir. Calismanin temel katkilari su sekilde ozetlenebilir:

* Hasta seviyesinde sizintiyi sistematik olarak engelleyen, GroupShuffleSplit ile dis tekrar ve StratifiedGroupKFold ile ic capraz dogrulamaya dayanan tutarli bir degerlendirme yapisi kurulmustur.
* Median imputation, dusuk varyans ve Pearson korelasyon esikli ozellik elemesi, RobustScaler olcekleme ve MRMR ozellik secimi adimlari tek bir sklearn Pipeline icinde butunlestirilmistir.
* Alti farkli siniflandirici Optuna TPE ile her tekrar icinde yeniden tunlanmis, hesaplama maliyetini dusurmek icin Pipeline cache mekanizmasi kullanilmistir.
* Sklearn 1.6 sonrasi `CalibratedClassifierCV` ile yasanan metadata routing sorununa karsi manuel grup-bilincli Platt scaling sarmalayicisi gelistirilmistir.
* SHAP TreeExplainer ile model yorumlanabilirligi saglanmis, ozellik kararliligi 10 dis tekrar boyunca olculmustur.


## 2. LITERATUR TARAMASI

### 2.1. Papilodem Goruntuleme Tabanli Tani

Papilodemin OKT veya fundus fotografi temelli otomatik siniflandirilmasina yonelik calismalar son yillarda hizla artmistir. Shenoy ve ark. [3] AutoML platformlari kullanarak yakin kizilotesi reflektans goruntuleri uzerinde papilodemin sahte papilodem ile ayrimi calismasinda Amazon Rekognition modelinin AUC 0.90 ve F1 0.81 ile en iyi sonucu verdigini bildirmistir. Szanto ve ark. [4] 3B OKT hacimleri uzerinde derin ogrenme tabanli bir yaklasimla papilodem, NAION ve saglikli gozleri ayirmis, ic dogrulamada %94.9 dogruluga ulasmistir. Girard ve ark. [5] optik sinir basinin 3B yapisal analizi yoluyla papilodemi optik disk drusen'den ayirt etmistir. Bu calismalar genel olarak derin ogrenme tabanli yaklasimlara odaklanmakla birlikte, kucuk veri rejimlerinde klasik makine ogrenmesi yontemleri ile birlikte ozellik muhendisligi yapilmasinin halen yuksek dogruluklu sonuclar saglayabildigi vurgulanmaktadir [12].

### 2.2. Radyomik Veri ile Siniflandirma

Radyomik veriyle ikili siniflandirma problemi, yuksek boyutluluk ve gorece sinirli ornek sayisi nedeniyle ozellik secimine son derece duyarli oldugundan, alandaki kapsamli karsilastirma calismalari onem tasimaktadir. Demircioglu [1] on radyomik veri seti uzerinde 29 ozellik secim yontemini karsilastirmis; sade yontemlerin (ANOVA, LASSO, MRMR ensemble) karmasik yontemlerden istatistiksel olarak farklilik gostermeden daha kararli sonuclar urettigini bildirmistir. Bu nedenle, calismamizda MRMR yontemi tercih edilmistir.

Sinif dengesizligi konusunda, ayni yazarin sonraki calismasi [2] on bes radyomik veri setinde dokuz farkli yeniden orneklem yontemini karsilastirmis ve resampling yontemlerinin AUC katkisinin ortalama +0.015 ile sinirli kaldigini gostermistir. Bunun yaninda yeniden orneklem hasta seviyesindeki gruplama kisitiyla cakistigi icin sentetik orneklerin grup yapisini bozdugu vurgulanmistir. Bu nedenle calismamizda `class_weight = 'balanced'` parametresi tercih edilmistir.


## 3. MATERYAL VE YONTEM

### 3.1. Veri Seti

Calismada kullanilan veri seti, optik diskten cikartilmis 746 radyomik ozellik iceren iki CSV dosyasindan olusmaktadir: `normal_radiomics.csv` ve `papilodem_radiomics.csv`. Veri setinin ozet bilgileri Tablo 3.1'de verilmistir.

**Tablo 3.1.** Sinif dagilimi ve hasta sayilari.

| Sinif | Hasta Sayisi | Ornek Sayisi | Ornek/Hasta |
|:-----:|:------------:|:------------:|:-----------:|
| Normal (0) | 48 | 672 | 14 |
| Papilodem (1) | 21 | 294 | 14 |
| **Toplam** | **69** | **966** | **14** |

Her hasta icin sag ve sol goz olmak uzere iki taraf, her taraf icin yedi dilim olmak uzere toplam 14 ornek bulunmaktadir. `PatientIndex` sutunu her iki dosyada da 1'den baslayarak yeniden numaralandirildigi icin dogrudan birlestirildiginde ayni kimligin iki ayri hastayi temsil etmesi soz konusudur. Bu sorunun onune gecmek amaciyla normal hastalara `N_` ve papilodem hastalarina `P_` on eki eklenmistir. Veri yuklemenin ardindan (i) iki sinif arasinda hasta ortakligi olmadigi, (ii) her hastanin tek bir sinif etiketine sahip oldugu ve (iii) hasta basina ornek sayisinin sabit oldugu, otomatik assert ifadeleriyle dogrulanmaktadir.

### 3.2. Veri On Isleme

On isleme adimlarinin tamami `sklearn.Pipeline` icine yerlestirilmis ve yalnizca egitim verisi uzerinde fit edilmistir. Sirayla uygulanan adimlar sunlardir: ortanca deger ile eksik veri tamamlama (`SimpleImputer(strategy='median')`), 0.01 esikli dusuk varyans elemesi (`VarianceThreshold`), Pearson korelasyonu |r| > 0.95 olan ozelliklerin elenmesi (calismaya ozel yazilan `CorrelationFilter`) ve `RobustScaler` ile uc-noktaya duyarli olmayan olcekleme. Veri yuklemede tespit edilen tek bir sonsuz deger NaN'a donusturulerek imputer'a teslim edilmistir.

### 3.3. Ozellik Secimi (MRMR)

Ozellik secimi icin Peng ve ark. [10] tarafindan onerilen Minimum Redundancy Maximum Relevance (MRMR) algoritmasi uygulanmistir. Alaka skoru Mutual Information ile, artikilik skoru ise Pearson korelasyonu ile hesaplanmistir. Secilecek ozellik sayisi $k \in \{20, 50, 100\}$ olarak Optuna icinde kategorik bir parametre olarak optimize edilmistir.

### 3.4. Siniflandirma Modelleri

Calismada degerlendirilen alti temel siniflandirici sunlardir: Lojistik Regresyon (saga cozucu, `class_weight='balanced'`), RBF cekirdekli Destek Vektor Makinesi, Rastgele Orman, ExtraTrees, Gradient Boosting ve K-En Yakin Komsu [7]. Hiperparametre arama uzaylari Tablo 3.2'de verilmistir.

**Tablo 3.2.** Optuna hiperparametre arama uzaylari.

| Model | Parametre | Aralik / Set |
|:-----:|:---------|:-------------|
| LR | C | log[1e-3, 1e2] |
| LR | penalty | {l1, l2} |
| SVM | C | log[1e-2, 1e2] |
| SVM | gamma | log[1e-4, 1e0] |
| RF / ET | n_estimators | [100, 500] step 50 |
| RF / ET | max_depth | [3, 20] |
| RF / ET | min_samples_leaf | [1, 10] |
| RF / ET | max_features | {sqrt, log2} |
| GB | n_estimators | [100, 500] step 50 |
| GB | learning_rate | log[1e-3, 3e-1] |
| GB | max_depth | [2, 8] |
| GB | subsample | [0.5, 1.0] |
| KNN | n_neighbors | [3, 25] |
| KNN | weights | {uniform, distance} |
| KNN | metric | {euclidean, manhattan} |
| Tum modeller | mrmr_k | {20, 50, 100} |

### 3.5. Hiperparametre Optimizasyonu

Hiperparametre optimizasyonu Optuna kutuphanesi [8] ile gerceklestirilmistir. TPE (Tree-structured Parzen Estimator) ornekleyici sabit tohum 42 ile baslatilmis, model basina 50 trial calistirilmistir. Amac fonksiyonu olarak ic 5-kat capraz dogrulama uzerinden hesaplanan ortalama makro-F1 secilmistir. Grup folds altinda yuksek varyans riski nedeniyle median pruner kullanilmamistir.

### 3.6. Capraz Dogrulama Yapisi

Dis dongude `GroupShuffleSplit` ile 10 patient-level tekrar uretilmistir; her tekrarda hastalarin %70'i egitim ve dogrulama, %30'u test olarak ayrilmistir. Ic dongude ise Optuna trial'inin her cagrisi sirasinda `StratifiedGroupKFold(n_splits=5)` ile hasta gruplari korunmustur. Boylece ayni hastaya ait orneklerin farkli setlere dusmesi engellenmis, sizinti olusturma riski ortadan kaldirilmistir.

### 3.7. Kalibrasyon ve Esik Optimizasyonu

Sklearn 1.6 surumunde `CalibratedClassifierCV.fit` cagrisi metadata routing API'si nedeniyle `StratifiedGroupKFold` ile birlikte kullanildiginda `groups` parametresini ic ayiriciya iletmemekte, bu da kalibrasyon foldlarinda hasta sizintisina yol acmaktadir. Sorunu cozmek icin calismaya ozel `GroupAwareSigmoidCalibrator` sinifi yazilmis ve ic foldlardan elde edilen olasiliklar uzerinde Platt scaling [11] uygulanmistir.

Esik optimizasyonu sirasinda yine StratifiedGroupKFold ile dogrulama tahminleri uretilmis ve [0.05, 0.95] araliginda 91 noktada F1 skoru hesaplanmistir. F1 maksimum esik daha sonra yalnizca test setinde uygulanmis, test verisi uzerinde esik ayari yapilmamistir.

### 3.8. Topluluk Ogrenmesi (Ensemble)

Tang ve ark. [6] gibi calismalarda etkinligi gosterilen soft voting yaklasimi tercih edilmistir. Kalibre edilmis Random Forest, ExtraTrees ve Gradient Boosting modellerinin olasilik ciktilari ortalanarak topluluk olasiligi elde edilmis, ardindan F1 maksimum esik uygulanmistir.

### 3.9. Degerlendirme Metrikleri

Spec dogrultusunda dokuz metrik raporlanmistir: Accuracy, Precision, Recall, F1, Macro-F1, ROC-AUC, PR-AUC, Balanced Accuracy ve Brier skoru. Her metrik 10 dis tekrar uzerinden ortalama ve standart sapma olarak verilmistir.

### 3.10. Istatistiksel Analiz

Yedi modelin (alti temel + topluluk) makro-F1 degerleri uzerinde Friedman testi uygulanmis, ardindan ikili karsilastirmalar Wilcoxon isaretli siralar testi ve Bonferroni duzeltmesi ile (21 ikili karsilastirma, alpha = 0.05/21 yaklasik 0.0024) yapilmistir.


## 4. BULGULAR

### 4.1. Genel Performans Karsilastirmasi

Tam pipeline calismasi 70 dakika surmus ve yedi modelin 10 dis tekrar uzerindeki performans ozeti Tablo 4.1'de verilmistir. En yuksek ortalama makro-F1 degeri SVM modeli ile (0.875) elde edilmistir. Tek tekrar bazinda ise 9. tekrarda SVM modeli ile makro-F1 = 0.951 olarak en iyi degere ulasilmistir. Sekil 4.1 modeller arasi makro-F1 karsilastirmasini gostermektedir.

**Tablo 4.1.** Modellerin tum metriklerde performansi (mean +/- std).


| model    | accuracy        | precision       | recall          | f1              | macro_f1        | roc_auc         | pr_auc          | balanced_accuracy   | brier           |
|:---------|:----------------|:----------------|:----------------|:----------------|:----------------|:----------------|:----------------|:--------------------|:----------------|
| ET       | 0.894 +/- 0.045 | 0.918 +/- 0.063 | 0.716 +/- 0.154 | 0.794 +/- 0.089 | 0.860 +/- 0.058 | 0.927 +/- 0.056 | 0.901 +/- 0.069 | 0.843 +/- 0.073     | 0.085 +/- 0.039 |
| Ensemble | 0.864 +/- 0.054 | 0.788 +/- 0.109 | 0.779 +/- 0.152 | 0.772 +/- 0.082 | 0.836 +/- 0.059 | 0.927 +/- 0.055 | 0.901 +/- 0.073 | 0.839 +/- 0.067     | 0.085 +/- 0.036 |
| GB       | 0.865 +/- 0.097 | 0.797 +/- 0.288 | 0.663 +/- 0.292 | 0.709 +/- 0.268 | 0.810 +/- 0.163 | 0.910 +/- 0.064 | 0.888 +/- 0.081 | 0.812 +/- 0.135     | 0.094 +/- 0.038 |
| KNN      | 0.891 +/- 0.041 | 0.894 +/- 0.072 | 0.723 +/- 0.149 | 0.790 +/- 0.091 | 0.858 +/- 0.058 | 0.882 +/- 0.074 | 0.842 +/- 0.096 | 0.844 +/- 0.070     | 0.092 +/- 0.035 |
| LR       | 0.836 +/- 0.074 | 0.921 +/- 0.100 | 0.544 +/- 0.249 | 0.640 +/- 0.186 | 0.766 +/- 0.114 | 0.879 +/- 0.079 | 0.852 +/- 0.079 | 0.756 +/- 0.108     | 0.127 +/- 0.039 |
| RF       | 0.890 +/- 0.042 | 0.900 +/- 0.077 | 0.721 +/- 0.168 | 0.787 +/- 0.093 | 0.856 +/- 0.058 | 0.921 +/- 0.058 | 0.896 +/- 0.076 | 0.841 +/- 0.076     | 0.088 +/- 0.035 |
| SVM      | 0.902 +/- 0.043 | 0.917 +/- 0.092 | 0.753 +/- 0.144 | 0.817 +/- 0.089 | 0.875 +/- 0.057 | 0.922 +/- 0.051 | 0.887 +/- 0.071 | 0.861 +/- 0.068     | 0.086 +/- 0.038 |

**Tablo 4.2.** Macro-F1 siralamasi (en iyi -> en kotu).


| Sira | Model | Macro-F1 (mean +/- std) |
|:----:|:-----:|:-----------------------:|
| 1 | SVM | 0.875 +/- 0.057 |
| 2 | ET | 0.860 +/- 0.058 |
| 3 | KNN | 0.858 +/- 0.058 |
| 4 | RF | 0.856 +/- 0.058 |
| 5 | Ensemble | 0.836 +/- 0.059 |
| 6 | GB | 0.810 +/- 0.163 |
| 7 | LR | 0.766 +/- 0.114 |

![Sekil 4.1. Modeller arasi makro-F1 karsilastirmasi.](../04_GRAFIKLER/model_comparison_macro_f1.png)
*Sekil 4.1. Modeller arasi ortalama makro-F1 karsilastirmasi.*

![Sekil 4.2. ROC egrileri.](../04_GRAFIKLER/roc_curves.png)
*Sekil 4.2. ROC egrileri (tum modeller, 10 outer repeat ortalamasi).*

![Sekil 4.3. PR egrileri.](../04_GRAFIKLER/pr_curves.png)
*Sekil 4.3. Precision-Recall egrileri.*

![Sekil 4.4. Karisiklik matrisi.](../04_GRAFIKLER/confusion_matrix.png)
*Sekil 4.4. Karisiklik matrisi (SVM, 9. tekrar).*

### 4.2. Istatistiksel Karsilastirma

Yedi modelin 10 tekrarli makro-F1 degerleri uzerinde yapilan Friedman testi sonucunda chi-kare = 15.83, p = 0.0147 degerleri elde edilmistir. p < 0.05 oldugundan modeller arasinda genel bir farkin bulundugu istatistiksel olarak dogrulanmistir.

Tablo 4.3, Bonferroni duzeltmeli Wilcoxon isaretli siralar testinin sonuclarini sunmaktadir. Toplam 21 ikili karsilastirmadan 0 tanesi Bonferroni duzeltmesi sonrasi anlamliligini korumustur. Bu durum, 10 tekrarli kucuk orneklem ile 21 esli karsilastirma yapilmasinin getirdigi sikilastirilmis alpha = 0.0024 esiginin dogal bir sonucudur ve sonuclarin yon gosterici olarak yorumlanmasi gerektigini ortaya koymaktadir.

**Tablo 4.3.** Wilcoxon pairwise testi (Bonferroni duzeltmeli).


| model_a   | model_b   |   statistic |    p_value |   p_bonferroni | significant   |
|:----------|:----------|------------:|-----------:|---------------:|:--------------|
| ET        | Ensemble  |          13 | 0.160156   |      1         | False         |
| ET        | GB        |          22 | 0.625      |      1         | False         |
| ET        | KNN       |          19 | 0.678402   |      1         | False         |
| ET        | LR        |           1 | 0.00390625 |      0.0820312 | False         |
| ET        | RF        |          18 | 0.375      |      1         | False         |
| ET        | SVM       |          19 | 0.431641   |      1         | False         |
| Ensemble  | GB        |          19 | 0.431641   |      1         | False         |
| Ensemble  | KNN       |          15 | 0.232422   |      1         | False         |
| Ensemble  | LR        |          12 | 0.130859   |      1         | False         |
| Ensemble  | RF        |          12 | 0.130859   |      1         | False         |
| Ensemble  | SVM       |           5 | 0.0195312  |      0.410156  | False         |
| GB        | KNN       |          26 | 0.921875   |      1         | False         |
| GB        | LR        |          11 | 0.105469   |      1         | False         |
| GB        | RF        |          27 | 1          |      1         | False         |
| GB        | SVM       |          12 | 0.130859   |      1         | False         |
| KNN       | LR        |           1 | 0.00390625 |      0.0820312 | False         |
| KNN       | RF        |          26 | 0.921875   |      1         | False         |
| KNN       | SVM       |          16 | 0.275391   |      1         | False         |
| LR        | RF        |           3 | 0.00976562 |      0.205078  | False         |
| LR        | SVM       |           1 | 0.00390625 |      0.0820312 | False         |
| RF        | SVM       |          18 | 0.375      |      1         | False         |

### 4.3. Kalibrasyon Analizi

Sigmoid kalibrasyon sonrasinda elde edilen Brier skorlarinin 0.08 ile 0.13 araliginda yogunlastigi gozlenmistir (Tablo 4.1). Kalibrasyon egrileri (Sekil 4.5) tum modellerde diyagonale yakin seyretmis, agac tabanli modellerin tipik over/under confidence egilimi sigmoid kalibrasyonla buyuk olcude duzelmistir [11].

![Sekil 4.5. Kalibrasyon egrileri.](../04_GRAFIKLER/calibration_curves.png)
*Sekil 4.5. Kalibrasyon egrileri (sigmoid Platt sonrasi).*

### 4.4. Ozellik Yorumlanabilirligi (SHAP)

ExtraTrees modeli uzerinde SHAP TreeExplainer ile hesaplanan ortalama mutlak SHAP degerleri, en yuksek katkili ilk on radyomik ozelligi belirlemistir. Sonuclar Tablo 4.4'te verilmistir. SHAP ozet grafigi Sekil 4.7'de sunulmustur.

**Tablo 4.4.** SHAP analizinde en yuksek katkili ilk 10 ozellik.


| Sira | Ozellik | mean |SHAP| |
|:----:|:-------:|:------------:|
| 1 | `Feature_0479` | 0.0748 |
| 2 | `Feature_0478` | 0.0305 |
| 3 | `Feature_0102` | 0.0284 |
| 4 | `Feature_0028` | 0.0259 |
| 5 | `Feature_0061` | 0.0254 |
| 6 | `Feature_0067` | 0.0249 |
| 7 | `Feature_0647` | 0.0246 |
| 8 | `Feature_0072` | 0.0218 |
| 9 | `Feature_0464` | 0.0217 |
| 10 | `Feature_0006` | 0.0203 |

Ayrica MRMR'in 10 outer tekrar boyunca tekrar tekrar sectigi ozellikler ozellik kararliligi grafiginde (Sekil 4.6) sunulmustur. SHAP siralamasi ile ortusen ozelliklerin yuksek frekansta secilmesi yorumlamayi guclendirmektedir.

![Sekil 4.6. Ozellik kararliligi.](../04_GRAFIKLER/feature_stability.png)
*Sekil 4.6. MRMR secim frekansi (10 outer repeat uzerinde).*

![Sekil 4.7. SHAP ozet grafigi.](../04_GRAFIKLER/shap_summary.png)
*Sekil 4.7. SHAP ozet grafigi (ExtraTrees).*


## 5. TARTISMA

Bulgular, calismanin uc temel iddiasini desteklemektedir. Birincisi, hasta seviyesindeki sizintinin sistematik olarak engellenmesi metodolojik bir zorunluluk olarak gozetildiginde bile, model performansi klinik olarak makul aralikta kalmaktadir (SVM makro-F1 0.875 +/- 0.057). Ikincisi, kalibre edilmis temel modellerin yakin karar yuzeyleri ogrenmesi nedeniyle soft voting topluluk modeli en iyi tek modeli geride birakamamistir. Tang ve ark. [6] benzer bir gozlemi farkli agirliklandirma sutrateilerini onererek tartismistir; bu yon ileride incelenebilecek bir adim olabilir.

Ucuncu ve kritik nokta, sklearn'in son surumunde ortaya cikan metadata routing davranisinin radyomik gibi grup yapisi guclu alanlarda kolayca gozden kacip sizintiya yol acabilecegidir. Calismada, varsayilan `CalibratedClassifierCV`'nin `StratifiedGroupKFold` ile birlikte kullanildiginda groups parametresini ic ayiriciya tasimadigi gosterilmis ve manuel Platt scaling sarmalayicisi ile bu sorun cozulmustur. Ileride sklearn'in metadata routing'inin daha kararli hale gelmesiyle bu sarmalayicinin daha kisa bir bicimde yeniden yazilabilmesi mumkun olacaktir.

Sinif dengesizliginin yonetimi yonunden, SMOTE benzeri yontemler yerine `class_weight` tabanli yaklasimin tercih edilmesinin literaturle uyumlu oldugu ifade edilebilir [2]. Sentetik orneklerin hasta kimligi olmayan veri noktalari uretmesi, grup folds yapisini bozar ve sizintisiz bir cerceveyi ortadan kaldirir; bu nedenle calismamizda SMOTE yontemine basvurulmamistir.

Istatistiksel test gucu, n = 10 blok ve 21 ikili karsilastirmanin getirdigi sikilastirilmis Bonferroni esigi (alpha yaklasik 0.0024) nedeniyle sinirlidir. Bu durum Wilcoxon karsilastirmalarinin cogunda anlamliliga ulasilamamasinda etkili olmus, ancak Friedman testi modeller arasi farkin varligini dogrulamistir. Daha cok dis tekrar veya daha buyuk orneklem ile bu sinirin asilmasi mumkundur.


## 6. SONUC VE ONERILER

Bu calismada, hasta seviyesinde veri sizintisini engelleyen, 10 dis tekrar ve 5 ic fold uzerine kurulu, kalibrasyonlu ve yorumlanabilir bir radyomik ikili siniflandirma sistemi gelistirilmistir. Sistem MRMR ozellik secimi, Optuna TPE hiperparametre optimizasyonu, sigmoid kalibrasyon, F1 maksimum esik secimi ve soft voting topluluk asamalarini tek bir cerceve icinde bulusturmaktadir. Toplam calisma suresi 70 dakika olup, en yuksek ortalama makro-F1 degerine RBF cekirdekli SVM modeli ile (0.875) ulasilmistir.

Ileriye yonelik oneriler asagidaki bicimde siralanabilir: (i) outer repeat sayisinin 20 veya uzeri arttirilmasi ile ikili karsilastirma istatistiklerinin gucunun arttirilmasi, (ii) farkli hasta kohortlari uzerinde dis dogrulama yapilmasi, (iii) topluluk modelinde agirlik ogrenimi veya stacking yaklasimlarinin denenmesi, (iv) sklearn metadata routing'inin olgunlasmasi ile manuel kalibrasyon sarmalayicisinin yeniden duzenlenmesi, (v) hem klinik ozelliklerin (yas, cinsiyet, semptom suresi) eklenmesiyle multimodal bir modele gecilmesi.


## KAYNAKLAR

[1] Demircioglu A. Benchmarking Feature Selection Methods in Radiomics. Investigative Radiology, 2022.
[2] Demircioglu A. The effect of data resampling methods in radiomics. Scientific Reports, 2024.
[3] Shenoy R., Samra G.S., Sekhri R., et al. Clinician-Led Code-Free Deep Learning for Detecting Papilledema and Pseudopapilledema Using Optic Disc Imaging. Translational Vision Science & Technology, 2026.
[4] Szanto D., Erekat A., Woods B., et al. Multimodal Deep Learning Differentiates Papilledema and Non-Arteritic Anterior Ischemic Optic Neuropathy From Healthy Eyes. IOVS, 2026.
[5] Girard M.J.A., Panda S., Tun T.A., et al. Discriminating Between Papilledema and Optic Disc Drusen Using 3D Structural Analysis of the Optic Nerve Head. Neurology, 2023.
[6] Tang G., Du L., Ling S., Che Y., Chen X. Multi-type classification of lung nodules based on CT radiomics and ensemble learning for diversity weighting. Quantitative Imaging in Medicine and Surgery, 2024.
[7] Pedregosa F., Varoquaux G., Gramfort A., et al. Scikit-learn: Machine Learning in Python. Journal of Machine Learning Research, 12: 2825-2830, 2011.
[8] Akiba T., Sano S., Yanase T., Ohta T., Koyama M. Optuna: A Next-generation Hyperparameter Optimization Framework. ACM SIGKDD, 2019.
[9] Lundberg S.M., Lee S.I. A Unified Approach to Interpreting Model Predictions. Advances in Neural Information Processing Systems, 2017.
[10] Peng H., Long F., Ding C. Feature selection based on mutual information: criteria of max-dependency, max-relevance, and min-redundancy. IEEE TPAMI, 27(8): 1226-1238, 2005.
[11] Platt J.C. Probabilistic outputs for support vector machines and comparisons to regularized likelihood methods. Advances in Large Margin Classifiers, 10(3): 61-74, 1999.
[12] Fang S.S., Chen S.H. AI-assisted diagnosis of neuro-ophthalmic disorders: a systematic review from optic neuritis to papilledema. BMC Ophthalmology, 2026.