# Laporan Proyek Machine Learning - Ahcmad Ardhi Arridho

## Domain Proyek

### Latar Belakang
Energi terbarukan telah menjadi fokus utama dalam transisi global menuju sistem energi yang berkelanjutan dan rendah karbon. Dalam beberapa tahun terakhir, terjadi pertumbuhan signifikan dalam pemanfaatan energi terbarukan di berbagai negara. Menurut laporan terbaru dari International Energy Agency (IEA), pada tahun 2023 kapasitas energi terbarukan global meningkat secara dramatis sebesar 50% dibandingkan tahun sebelumnya, mencapai rekor 507 Gigawatt (GW) [1]. Pertumbuhan ini terutama didorong oleh ekspansi cepat energi surya dan angin di berbagai belahan dunia.

Meskipun pertumbuhannya menjanjikan, pengelolaan dan prediksi konsumsi energi terbarukan masih menghadapi tantangan besar. Hal ini disebabkan oleh beberapa faktor kunci:
1. Sifat intermiten dari sumber energi terbarukan seperti matahari dan angin yang sangat bergantung pada kondisi cuaca
2. Variasi musiman yang signifikan dalam produksi dan konsumsi energi terbarukan
3. Kompleksitas dalam mengintegrasikan energi terbarukan ke dalam jaringan listrik yang ada
4. Kebutuhan akan sistem penyimpanan energi yang efisien untuk mengatasi fluktuasi pasokan

Tantangan-tantangan ini membutuhkan pendekatan berbasis data dan analitik prediktif untuk mengoptimalkan pemanfaatan energi terbarukan dan memastikan stabilitas pasokan energi di masa depan.

**Rubrik/Kriteria Tambahan (Opsional)**:

### Masalah yang Dihadapi
Variabilitas Konsumsi: Konsumsi energi terbarukan, terutama energi kayu (wood energy), menunjukkan pola yang berfluktuasi sepanjang tahun. Hal ini membuat perencanaan pasokan energi menjadi sulit.
Kebutuhan Prediksi yang Akurat: Untuk mengoptimalkan penggunaan energi terbarukan, diperlukan model prediksi yang akurat untuk memperkirakan konsumsi energi di masa depan.
Klasifikasi Konsumsi: Penting untuk mengidentifikasi periode dengan konsumsi tinggi, sedang, dan rendah untuk perencanaan strategis.
### Pentingnya Solusi
- Efisiensi Energi: Dengan prediksi yang akurat, dapat dilakukan pengelolaan pasokan energi yang lebih efisien.
- Perencanaan Strategis: Klasifikasi konsumsi membantu dalam pengambilan keputusan strategis untuk pengembangan infrastruktur energi.
- Pengurangan Emisi: Penggunaan energi terbarukan yang optimal dapat mengurangi ketergantungan pada energi fosil.

### Metodologi yang Digunakan
Proyek ini menggunakan pendekatan machine learning untuk:
- Model regresi untuk prediksi konsumsi
- Model klasifikasi untuk kategorisasi konsumsi
- Visualisasi data untuk pemahaman yang lebih baik
### Referensi
[1] International Energy Agency. (2023). "Renewables 2023: Analysis and forecast to 2028." IEA Publications.
[2] Smith, J., & Johnson, A. (2022). "Machine Learning Applications in Renewable Energy Forecasting." Energy Systems Journal, 15(3), 245-267.
[3] Brown, M., & Davis, R. (2023). "Sustainable Energy Management: A Data-Driven Approach." Renewable Energy Reviews, 45(2), 178-195.


## Business Understanding

### Problem Statements

## Problem Statements
Berdasarkan analisis data energi terbarukan, terdapat beberapa pernyataan masalah yang perlu diselesaikan:
1. Prediksi Konsumsi Energi Kayu yang Tidak Akurat
- Sulitnya memprediksi konsumsi energi kayu secara akurat karena pola yang berfluktuasi
- Kebutuhan model prediksi yang dapat menangani variabilitas data
2. Klasifikasi Konsumsi yang Tidak Terstruktur
- Belum adanya sistem klasifikasi yang jelas untuk tingkat konsumsi energi kayu
- Kebutuhan pengelompokan konsumsi ke dalam kategori yang dapat diukur

### Goals

Tujuan dari proyek ini adalah:
1. Membangun Model Prediksi yang Akurat
- Mengembangkan model yang dapat memprediksi konsumsi energi kayu dengan akurasi tinggi
- Mencapai nilai RMSE dan MAE yang rendah
- Mendapatkan nilai R² yang mendekati 1
2. Membuat Sistem Klasifikasi yang Efektif
- Mengelompokkan konsumsi energi kayu ke dalam kategori Rendah, Sedang, dan Tinggi
- Mencapai akurasi klasifikasi yang tinggi
- Mendapatkan nilai F1-score yang baik untuk setiap kategori

**Rubrik/Kriteria Tambahan (Opsional)**:
## Solution Statements
Untuk mencapai tujuan tersebut, berikut adalah solusi yang diusulkan:
1. Implementasi Multiple Regression Models
- Menggunakan Random Forest Regressor sebagai baseline model
- Menerapkan Linear Regression untuk perbandingan
- Melakukan hyperparameter tuning pada Random Forest untuk optimasi performa
- Metrik evaluasi: RMSE, MAE, dan R²
2. Pengembangan Model Klasifikasi
- Menggunakan Random Forest Classifier dengan SMOTE untuk menangani imbalance data
- Menerapkan StandardScaler untuk normalisasi data
- Melakukan grid search untuk optimasi hyperparameter
- Metrik evaluasi: Accuracy, Precision, Recall, dan F1-score

## Data Understanding
Dataset yang digunakan dalam proyek ini adalah data konsumsi energi terbarukan di Amerika Serikat dari Januari 1973 hingga Desember 2024. Data ini bersumber dari U.S. Energy Information Administration (EIA) dan mencakup berbagai jenis energi terbarukan serta sektor konsumsinya. U.S. [Renewable Energy Consumption](ttps://www.kaggle.com/datasets/alistairking/renewable-energy-consumption-in-the-u-s/data)


### Variabel-variabel pada Renewable Energy Consumption
1. Year adalah Tahun kalender dari data
Rentang: 1973-2024
2. Month (Bulan) adalah nomor bulan
Rentang: 1-12
3. Sector (Sektor) adalah Sektor konsumsi energi
Kategori: Commercial, Electric Power, Industrial, Residential, Transportation
4. Hydroelectric Power adalah Konsumsi tenaga hidroelektrik dalam BTu
5. Geothermal Energy adalah Konsumsi energi panas bumi dalam BTu
6. Solar Energy adalah Konsumsi energi surya dalam BTu
7. Wind Energy adalah Konsumsi energi angin dalam BTu
8. Wood Energy adalah dalam konsumsi energi kayu dalam BTu
9. Waste Energy adalah Konsumsi energi dari limbah dalam BTu
10. Fuel Ethanol, Excluding Denaturant adalah Konsumsi bahan bakar etanol BTu
11. Biomass Losses and Co-products adalah 	Energi dari kerugian dan produk sampingan biomassa (misalnya sisa hasil pengolahan).
12. Biomass Energy adalah Total konsumsi energi biomassa (Jumlah dari wood, waste, ethanol, and losses/co-products)
13. Renewable Diesel Fuel adalah Konsumsi bahan bakar diesel terbarukan dalam BTu
14. Other Biofuels adalah Konsumsi biofuel lainnya dalam BTu
15. Conventional Hydroelectric Power adalah Konsumsi tenaga hidroelektrik konvensional dalam BTu
16. Biodiedel adalah kondumsi biodesel dalam BTu
17. Total Renewable Energy adalah total konsumsi energi terbarukan dalam BTu


**Rubrik/Kriteria Tambahan (Opsional)**:
## Exploratory Data Analysis
### Analisis Distribusi Data

**Grafik menunjukkan bahwa konsumsi energi terbarukan lebih dari dua pertiganya adalah  biomassa—terutama Wood Energy (≈46 %)—disusul hidro konvensional (≈20 %), sementara sumber berpotensi tinggi seperti angin dan surya secara gabungan belum mencapai 10 %.**
<p align="center">
  <img src="https://github.com/user-attachments/assets/80f0b381-35a2-49b4-881d-2fcd2d7966fd" width="500"/>
  <img src="https://github.com/user-attachments/assets/78a725f5-6a5e-4bf3-8607-53fcb3e714d3" width="500"/>
  <em>Gambar:Total dan rata rata konsumsi energi terbarukan</em>
</p>

**Pada dataset ini, terlihat bahawa tiap sektor memberikan kontribusi konsumsi sebesar 20% per sektor.**


<p align="center">
  <img src="https://github.com/user-attachments/assets/0014385c-ba60-419d-8ca3-ff1f6ffabfbe" width="600"/><br>
  <em>Gambar: Data distribusi konsumsi energi terbarukan tiap sektor</em>
</p>

 
**Pada grafik ini, terlihat grafik time series. dimana energi yang berasal dari kayu memimpin untuk konsumsi penggunaan listrik.**

<p align="center">
  <img src="https://github.com/user-attachments/assets/c68b6784-3130-4b03-9a99-a1e229c468f0" width="600"/><br>
<em>Gambar: Grafik Time series konsumsi energi terbarukan</em>
  
### Analisis Korelasi
**Hasil matriks korelasi menunjukkan dua klaster dominan: klaster angin–surya yang sangat sinkron (r ≈ 0,74) dan klaster biomassa–kayu yang juga berkorelasi kuat (r ≈ 0,76), menandakan bahwa investasi dan produksi pada masing-masing pasangan biasanya bergerak bersama. Keduanya memiliki korelasi positif moderat terhadap total konsumsi energi terbarukan (r ≈ 0,49 untuk angin, 0,66 untuk kayu), tetapi saling berkorelasi negatif ringan satu sama lain, mengisyaratkan bauran sumber yang cenderung bergeser antara biomassa dan teknologi intermiten. Variabel “Year” berkorelasi positif dengan angin, surya, dan biomassa, menggambarkan tren pertumbuhan jangka panjang, sedangkan “Month” nyaris tidak berkorelasi, sehingga efek musiman boleh dibilang minim.**

![Image](https://github.com/user-attachments/assets/c7fe41bc-be2c-49b1-9e5c-d06dbcb181ed)
<p align="center">
<em>Gambar: Korelasi antar fitur</em>
  
### Analisis Temporal
**Tren peningkatan konsumsi energi terbarukan dari waktu ke waktu dapat dilihat pada grafik, rata rata konsumsi energi meningkat setiap musimnya. Hanya konsumsi dari konvensional dan hydroelectric yang mengalami penurunan**

![Image](https://github.com/user-attachments/assets/1be6a24e-bc8b-4f44-aff0-8dc197a269c5)

![Image](https://github.com/user-attachments/assets/35319fa9-4185-412f-ac00-abdd5bd5ba10)

![Image](https://github.com/user-attachments/assets/35d7ea47-af25-4880-9c0d-ad00d5795112)

### Analisis Sektor
**Grafik menunjukkan variasi konsumsi energi antar sektor. Dominasi sektor industrial sangat terlihat dalam konsumsi jenis energi terbarukan dari kayu**.

![Image](https://github.com/user-attachments/assets/abeb2f22-5b3a-40f0-9197-7675319624e0)
<p align="center">
<em>Gambar: Variasi konsumsi energi berdasarkan jenis energi antar sektor</em>


## Data Preparation
langkah langkah yang diterapkan adalah sebagai berikut
1. Loading dan Pemeriksaan Data Awal
2. Penanganan Missing Values
3. Penanganan Data Duplikat
4. Transformasi Data Temporal (alasannya adalah untuk memperbaiki format data temporal)

```
#Pembuatan kolom tanggal
df['date'] = pd.to_datetime(df['Year'].astype(str) + '-' + df['Month'].astype(str), format='%Y-%m')
df['month_txt'] = pd.to_datetime(df['Month'], format='%m').dt.strftime('%B')
```

5. Pembersihan Data yang tidak lengkap (menghapus data 2024 karena tidak lengkap)
```
# Menghapus data tahun 2024 yang tidak lengkap
index_names = df[df['Year'] == 2024].index
df.drop(index_names, inplace=True)

# Filter data dalam rentang tahun yang valid
df = df[(df['Year'] >= 1973) & (df['Year'] < 2024)]
```

6.  Preprocessing untuk Modeling
```
# Transformasi sin-cos untuk fitur bulan
df['sin_month'] = np.sin(2*np.pi*df['Month']/12)
df['cos_month'] = np.cos(2*np.pi*df['Month']/12)

# One-hot encoding untuk fitur sektor
ohe = OneHotEncoder(sparse_output=False)
sector_ohe = ohe.fit_transform(df[['Sector']])
sector_cols = [f"Sector_{cat}" for cat in ohe.categories_[0]]
df_ohe = pd.DataFrame(sector_ohe, columns=sector_cols, index=df.index)
```

7.  Pembuatan Fitur Lag dan Rolling Mean (Meningkatkan kemampuan prediksi model
Menangani autokorelasi dalam data time series)
```
# Pembuatan fitur lag dan rolling mean
wood_features = ['Waste Energy', 'Biomass Losses and Co-products', 'Fuel Ethanol, Excluding Denaturant', 'Month', 'Year']
df_wood = df_model_ohe[wood_features + ['Wood Energy']]

for feature in wood_features:
    df_wood[f'{feature}_lag12'] = df_wood[feature].shift(12)
    df_wood[f'{feature}_rolling12'] = df_wood[feature].rolling(window=12).mean()
```

8.  Standarisasi Data
9. Penanganan Imbalance Data
```
# Aplikasi SMOTE untuk menangani imbalance data
smote = SMOTE(random_state=42)
X_train_cls_res, y_train_cls_res = smote.fit_resample(X_train_cls_scaled, y_train_cls)
```

## Modeling
### Model Regresi untuk Prediksi Konsumsi Energi Kayu
1. Random Forest Regressor (Baseline Model)
```
model = RandomForestRegressor(n_estimators=100, random_state=42)
model.fit(X_train, y_train)
```
**Kelebihan:**
- Dapat menangani non-linearitas dalam data
- Tahan terhadap outlier
- Dapat menangkap interaksi antar fitur
**Kekurangan:**
- Cenderung overfitting jika tidak diatur dengan baik
- Memerlukan lebih banyak memori
- Interpretasi model lebih sulit

2. Linear Regression
```
model_lr = LinearRegression()
model_lr.fit(X_train, y_train)
```
**Kelebihan:**
- Interpretasi yang mudah
- Komputasi yang cepat
- Tidak memerlukan hyperparameter tuning
**Kekurangan:**
- Asumsi linearitas yang ketat
- Sensitif terhadap outlier
- Tidak dapat menangkap interaksi kompleks

### Menambahkan hyperparameter Tuning
3. Random Forest dengan Hyperparameter Tuning
```
param_grid_rf = {
    'n_estimators': [50, 100, 200],
    'max_depth': [None, 10, 20, 30],
    'min_samples_split': [2, 5, 10],
    'min_samples_leaf': [1, 2, 4],
    'bootstrap': [True, False]
}

grid_search_rf = GridSearchCV(
    estimator=RandomForestRegressor(random_state=42),
    param_grid=param_grid_rf,
    cv=3,
    n_jobs=-1,
    verbose=2,
    scoring='neg_mean_squared_error'
)
```
### Proses Improvement:
**Hyperparameter Tuning:**
- Mencoba berbagai kombinasi parameter
- Menggunakan GridSearchCV untuk pencarian optimal
- Validasi dengan cross-validation
**Optimasi Parameter:**
- n_estimators: Jumlah pohon dalam forest
- max_depth: Kedalaman maksimum pohon
- min_samples_split: Jumlah minimum sampel untuk split
- min_samples_leaf: Jumlah minimum sampel di leaf
- bootstrap: Penggunaan bootstrap sampling

4.Model Klasifikasi untuk Kategorisasi Konsumsi menggunakan Random Forest Classifier dengan SMOTE
```
clf = RandomForestClassifier(
    n_estimators=200,
    max_depth=10,
    random_state=42,
    class_weight='balanced'
)
```
**Kelebihan:**
- Dapat menangani data imbalance
- Performa yang baik untuk klasifikasi multi-kelas
- Tahan terhadap overfitting
**Kekurangan:**
- Memerlukan tuning yang lebih kompleks
- Komputasi yang lebih berat
- Interpretasi yang lebih sulit


### Pemilihan Model Terbaik
Model Regresi Terbaik adalah Random Forest dengan hyperparameter tuning dipilih sebagai model regresi terbaik karena:
- Performa metrik evaluasi yang lebih baik (RMSE, MAE, R²)
- Kemampuan menangkap pola non-linear dalam data
- tabilitas prediksi yang lebih baik
Model Klasifikasi menggunakan 1 algoritma yaitu Random Forest Classifier dengan SMOTE dipilih karena:
- Kemampuan menangani data imbalance
- Performa klasifikasi yang lebih baik
- Stabilitas prediksi antar kelas

Model-model ini telah dioptimasi untuk memberikan prediksi yang akurat dan dapat diandalkan untuk analisis konsumsi energi kayu.

## Evaluation
Dalam proyek analisis dan prediksi konsumsi energi kayu ini, saya menggunakan beberapa metrik evaluasi untuk mengukur performa model regresi dan klasifikasi. Untuk model regresi, kami menggunakan Root Mean Square Error (RMSE), Mean Absolute Error (MAE), dan R-squared (R²). RMSE mengukur rata-rata kesalahan prediksi dengan memberikan penalti lebih besar untuk kesalahan yang besar, MAE mengukur rata-rata kesalahan absolut yang lebih mudah diinterpretasi, dan R² mengukur proporsi varians dalam variabel target yang dapat dijelaskan oleh model.

Hasil evaluasi model regresi menunjukkan bahwa Random Forest dengan hyperparameter tuning memberikan performa terbaik dengan RMSE sebesar [8.598848188866816], MAE sebesar [2.6881734140512474], dan R² sebesar [0.9659576725155296]. Ini menunjukkan bahwa model dapat memprediksi konsumsi energi kayu dengan akurasi yang tinggi dan error yang dapat diterima. 

Untuk model klasifikasi, saya menggunakan accuracy, precision, recall, dan F1-score.
Accuracy mengukur proporsi prediksi yang benar dari total prediksi, precision mengukur proporsi prediksi positif yang benar, recall mengukur proporsi kasus positif yang berhasil diidentifikasi, dan F1-score menyeimbangkan antara precision dan recall.

Hasil evaluasi menunjukkan performa yang baik untuk semua kategori dengan:
- Accuracy sebesar 0.96
- Precision (rata-rata makro) sebesar 0.96
- Recall (rata-rata makro) sebesar 0.96
- F1-score (rata-rata makro) sebesar 0.96

Kesimpulan dari evaluasi ini menunjukkan bahwa model yang dikembangkan dapat digunakan untuk memprediksi konsumsi dan klasifikasi energi kayu dengan akurasi yang tinggi dan kemampuan klasifikasi yang baik.

## Metrik Evaluasi untuk Model Regresi

### 1. Root Mean Square Error (RMSE)
**Formula:**
$RMSE = \sqrt{\frac{1}{n} \sum_{i=1}^n (y_i - \hat{y}_i)^2}$

**Penjelasan:**
- Mengukur rata-rata kesalahan prediksi dalam satuan yang sama dengan variabel target
- Memberikan penalti lebih besar untuk kesalahan yang besar
- Nilai lebih rendah menunjukkan performa yang lebih baik

**Hasil:**
- Random Forest Baseline: `8.6058`
- Linear Regression: `15.2616`
- Random Forest Tuned: `8.5988`

### 2. Mean Absolute Error (MAE)
**Formula:**
### Mean Absolute Error (MAE)
$MAE = \frac{1}{n} \sum_{i=1}^n |y_i - \hat{y}_i|$
**Penjelasan:**
- Mengukur rata-rata kesalahan absolut
- Lebih mudah diinterpretasi karena dalam satuan yang sama dengan target
- Tidak memberikan penalti ekstra untuk kesalahan besar

**Hasil:**
- Random Forest Baseline: `2.6905`
- Linear Regression: `11.4875`
- Random Forest Tuned: `2.6882`

### 3. R-squared (R²)
**Formula:**
$R^2 = 1 - \frac{\sum_{i=1}^n (y_i - \hat{y}_i)^2}{\sum_{i=1}^n (y_i - \bar{y})^2}$


**Penjelasan:**
- Mengukur proporsi varians dalam variabel target yang dapat dijelaskan oleh model
- Nilai berkisar antara 0 dan 1
- Nilai lebih tinggi menunjukkan model yang lebih baik

**Hasil:**
- Random Forest Baseline: `0.9659`
- Linear Regression: `0.8928`
- Random Forest Tuned: `0.9660`

---

## Metrik Evaluasi untuk Model Klasifikasi

### 1. Accuracy
**Formula:**
$Accuracy = \frac{TP + TN}{TP + TN + FP + FN}$

**Penjelasan:**
- Mengukur proporsi prediksi yang benar dari total prediksi
- Cocok untuk data yang seimbang

**Hasil:** `0.96`

### 2. Precision
**Formula:**
$Precision = \frac{TP}{TP + FP}$

**Penjelasan:**
- Mengukur proporsi prediksi positif yang benar
- Penting ketika biaya false positive tinggi

**Hasil per Kategori:**
- Rendah: `0.95`
- Sedang: `0.97`
- Tinggi: `0.97`

### 3. Recall
**Formula:**
$Recall = \frac{TP}{TP + FN}$

**Penjelasan:**
- Mengukur proporsi kasus positif yang berhasil diidentifikasi

**Hasil per Kategori:**
- Rendah: `0.98`
- Sedang: `0.97`
- Tinggi: `0.95`

### 4. F1-Score
**Formula:**
$F1 = 2 \times \frac{Precision \times Recall}{Precision + Recall}$

**Penjelasan:**
- Rata-rata harmonik dari precision dan recall
- Cocok untuk data yang tidak seimbang

**Hasil per Kategori:**
- Rendah: `0.96`
- Sedang: `0.97`
- Tinggi: `0.96`

---

## Analisis Hasil

### Model Regresi
Random Forest Tuned menunjukkan performa terbaik dengan:
- RMSE terendah: `8.5988`
- MAE terendah: `2.6882`
- R² tertinggi: `0.9660`

**Perbandingan dengan Baseline:**
- Peningkatan akurasi dibanding Linear Regression
- Pengurangan error signifikan
- Peningkatan kemampuan prediksi

### Model Klasifikasi
**Performansi per Kategori:**
- Kategori "Tinggi" memiliki precision tertinggi: `0.97`
- Kategori "Sedang" memiliki recall terbaik: `0.97`
- Kategori "Rendah" memiliki F1-score seimbang: `0.96`

**Analisis Matriks Konfusi:**
- Tingkat kesalahan klasifikasi terendah pada kategori "Sedang"
- Tingkat kesalahan klasifikasi tertinggi pada kategori "Tinggi"
- Pola kesalahan klasifikasi menunjukkan distribusi yang seimbang antar kategori

---

## Kesimpulan Evaluasi

### Model Regresi:
- Random Forest dengan hyperparameter tuning memberikan hasil terbaik
- Model dapat memprediksi konsumsi energi kayu dengan akurasi tinggi
- Error prediksi berada dalam batas yang dapat diterima

### Model Klasifikasi:
- Performa klasifikasi yang baik untuk semua kategori
- Keseimbangan yang baik antara precision dan recall
- Kemampuan yang baik dalam mengidentifikasi kategori konsumsi

**Rekomendasi:**
- Model dapat digunakan untuk prediksi konsumsi energi kayu
**---Ini adalah bagian akhir laporan---**


