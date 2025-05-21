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

Permasalahan bisnis utama yang ingin diselesaikan dalam proyek ini adalah bagaimana membantu pengambil keputusan di sektor energi (pemerintah, perusahaan utilitas, dan pemangku kepentingan lainnya) dalam merencanakan dan mengelola konsumsi energi terbarukan, khususnya energi kayu, secara lebih efisien dan strategis. Tantangan bisnis yang dihadapi meliputi:

1. **Ketidakpastian dalam Perencanaan Pasokan Energi Kayu**
   - Konsumsi energi kayu sangat fluktuatif dan dipengaruhi oleh faktor musiman serta tren jangka panjang, sehingga sulit diprediksi secara akurat.
   - Ketidakakuratan prediksi dapat menyebabkan kelebihan atau kekurangan pasokan, yang berdampak pada biaya operasional, efisiensi distribusi, dan potensi kerugian finansial.

2. **Kurangnya Sistem Klasifikasi Konsumsi untuk Pengambilan Keputusan**
   - Tidak adanya sistem kategorisasi konsumsi energi kayu (rendah, sedang, tinggi) yang terstruktur menyulitkan perumusan kebijakan, penentuan prioritas investasi, dan strategi pengelolaan sumber daya.
   - Pengelompokan konsumsi yang jelas sangat dibutuhkan untuk mendukung perencanaan strategis, pengelolaan risiko, dan optimalisasi penggunaan energi terbarukan.

### Goals

Tujuan bisnis yang ingin dicapai melalui proyek ini adalah:

1. **Meningkatkan Akurasi Perencanaan dan Efisiensi Operasional**
   - Menghasilkan model prediksi konsumsi energi kayu yang akurat untuk mendukung perencanaan pasokan, pengelolaan inventori, dan pengambilan keputusan berbasis data.
   - Target keberhasilan: model prediksi dengan nilai RMSE dan MAE serendah mungkin, serta nilai R² mendekati 1, sehingga dapat diandalkan dalam perencanaan bisnis.

2. **Menyediakan Sistem Klasifikasi Konsumsi untuk Mendukung Strategi Bisnis**
   - Mengembangkan sistem klasifikasi konsumsi energi kayu ke dalam kategori Rendah, Sedang, dan Tinggi, sehingga memudahkan identifikasi periode kritis dan perumusan kebijakan yang tepat.
   - Target keberhasilan: sistem klasifikasi dengan akurasi dan F1-score tinggi pada setiap kategori, sehingga dapat digunakan sebagai dasar pengambilan keputusan strategis.

### Solution Statements (Opsional)

Untuk menjawab kebutuhan bisnis di atas, solusi yang diusulkan adalah:

1. **Implementasi Model Prediksi Konsumsi Energi Kayu**
   - Menggunakan algoritma Random Forest Regressor sebagai baseline untuk memprediksi konsumsi energi kayu, serta membandingkannya dengan model Linear Regression.
   - Melakukan optimasi model melalui hyperparameter tuning untuk mendapatkan performa terbaik.
   - Evaluasi model dilakukan menggunakan metrik bisnis yang relevan: RMSE, MAE, dan R².

2. **Pengembangan Sistem Klasifikasi Konsumsi**
   - Membangun model klasifikasi (misal: Random Forest Classifier) untuk mengelompokkan konsumsi energi kayu ke dalam kategori bisnis yang actionable (Rendah, Sedang, Tinggi).
   - Mengatasi masalah imbalance data dengan teknik SMOTE dan melakukan normalisasi menggunakan StandardScaler.
   - Melakukan grid search untuk optimasi hyperparameter, serta mengevaluasi performa model menggunakan metrik bisnis: Accuracy, Precision, Recall, dan F1-score.

Dengan solusi ini, diharapkan pengelolaan energi terbarukan, khususnya energi kayu, dapat dilakukan secara lebih efisien, terukur, dan mendukung pencapaian tujuan bisnis jangka panjang.


## Data Understanding

Dataset yang digunakan dalam proyek ini adalah data konsumsi energi terbarukan di Amerika Serikat dari Januari 1973 hingga Desember 2024. Sumber data: [Kaggle - Renewable Energy Consumption in the U.S.](https://www.kaggle.com/datasets/alistairking/renewable-energy-consumption-in-the-u-s/data).

**Jumlah Data:**
- Jumlah baris: 3065
- Jumlah kolom: 17

**Kondisi Data:**
- Missing value: Tidak ditemukan nilai yang hilang pada kolom utama (semua kolom memiliki jumlah data non-null penuh).
- Duplikat: Tidak ditemukan data duplikat berdasarkan kombinasi Year, Month, dan Sector.
- Outlier: Terdapat beberapa nilai ekstrim pada fitur konsumsi energi (misal: Wood Energy, Wind Energy), namun masih dalam rentang yang wajar sesuai tren historis.
- Tipe data: 14 kolom bertipe float64 (numerik), 2 kolom bertipe int64 (Year, Month), dan 1 kolom bertipe object (Sector/kategorikal).

**Tautan Sumber Data:**
- [https://www.kaggle.com/datasets/alistairking/renewable-energy-consumption-in-the-u-s/data](https://www.kaggle.com/datasets/alistairking/renewable-energy-consumption-in-the-u-s/data)


**Uraian Fitur pada Dataset:**
1. **Year**: Tahun kalender data (1973-2024)
2. **Month**: Nomor bulan (1-12)
3. **Sector**: Sektor konsumsi energi (Commerical, Electric Power, Industrial, Residential, Transportation)
4. **Hydroelectric Power**: Konsumsi tenaga hidroelektrik (BTu)
5. **Geothermal Energy**: Konsumsi energi panas bumi (BTu)
6. **Solar Energy**: Konsumsi energi surya (BTu)
7. **Wind Energy**: Konsumsi energi angin (BTu)
8. **Wood Energy**: Konsumsi energi kayu (BTu)
9. **Waste Energy**: Konsumsi energi dari limbah (BTu)
10. **Fuel Ethanol, Excluding Denaturant**: Konsumsi bahan bakar etanol (BTu)
11. **Biomass Losses and Co-products**: Energi dari kerugian dan produk sampingan biomassa (BTu)
12. **Biomass Energy**: Total konsumsi energi biomassa (jumlah dari wood, waste, ethanol, dan losses/co-products) (BTu)
13. **Total Renewable Energy**: Total konsumsi energi terbarukan (BTu)
14. **Renewable Diesel Fuel**: Konsumsi bahan bakar diesel terbarukan (BTu)
15. **Other Biofuels**: Konsumsi biofuel lainnya (BTu)
16. **Conventional Hydroelectric Power**: Konsumsi tenaga hidroelektrik konvensional (BTu)
17. **Biodiesel**: Konsumsi biodiesel (BTu)


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

Berikut adalah tahapan lengkap data preparation yang dilakukan pada proyek ini, disusun secara urut dan sesuai dengan proses pada notebook:

1. **Loading dan Pemeriksaan Data Awal**  
   - Dataset energi terbarukan dimuat ke dalam DataFrame.
   - Dilakukan pengecekan struktur data (`df.info()`), tipe data setiap kolom, serta menampilkan beberapa baris awal untuk memastikan data terbaca dengan benar.
   - Identifikasi missing values dan data duplikat.

2. **Penanganan Missing Values dan Duplikasi**  
   - Data yang memiliki nilai hilang (missing values) diidentifikasi dan diatasi, misal dengan menghapus baris/kolom yang tidak lengkap atau mengisi dengan metode tertentu.
   - Data duplikat dihapus agar tidak mempengaruhi analisis dan pemodelan.

3. **Transformasi Data Temporal**  
   - Kolom `Year` dan `Month` digabungkan menjadi kolom tanggal (`datetime`) untuk memudahkan analisis time series.
   - Nama bulan ditambahkan sebagai fitur baru untuk keperluan visualisasi.

4. **Pembersihan Data Tidak Lengkap**  
   - Data tahun 2024 yang tidak lengkap dihapus.
   - Data difilter hanya pada rentang tahun yang valid, yaitu 1973–2023.

5. **Transformasi Fitur Bulan dengan Sin-Cos**  
   - Fitur `Month` ditransformasikan menggunakan fungsi sinus dan cosinus:
     - `sin_month = np.sin(2 * np.pi * Month / 12)`
     - `cos_month = np.cos(2 * np.pi * Month / 12)`
   - Transformasi ini bertujuan untuk menangkap pola musiman (seasonality) pada data bulanan.

6. **Encoding Fitur Kategorikal (One-Hot Encoding)**  
   - Fitur kategorikal seperti `Sector` diubah menjadi bentuk numerik menggunakan OneHotEncoder dari sklearn.
   - Hasil encoding digabungkan kembali ke DataFrame utama dan kolom asli dihapus.

7. **Pembuatan Fitur Lag dan Rolling Mean**  
   - Untuk fitur-fitur utama (misal: Wood Energy, Waste Energy, Biomass Losses, Fuel Ethanol, dsb), dibuat fitur lag (nilai pada 12 bulan sebelumnya) dan rolling mean (rata-rata 12 bulan).
   - Tujuannya agar model dapat menangkap pola temporal dan autokorelasi pada data time series.

8. **Pembuatan Fitur Kategori Konsumsi Energi**  
   - Target (misal: konsumsi energi kayu) dikategorikan menjadi beberapa kelas (Rendah, Sedang, Tinggi) menggunakan metode seperti quantile atau aturan domain, untuk keperluan klasifikasi.

9. **Split Data (Training dan Testing)**  
   - Data dipisahkan menjadi data latih (train) dan data uji (test) menggunakan `train_test_split` dari sklearn, baik untuk regresi maupun klasifikasi.

10. **Standarisasi Data**  
    - Fitur numerik distandarisasi menggunakan StandardScaler agar model lebih stabil dan hasil prediksi lebih akurat.

11. **Penanganan Imbalance Data**  
    - Untuk data klasifikasi yang tidak seimbang, dilakukan penyeimbangan kelas menggunakan teknik SMOTE (Synthetic Minority Over-sampling Technique).

Dengan tahapan-tahapan di atas, data telah diproses secara menyeluruh dan sistematis sehingga siap digunakan untuk proses pemodelan baik regresi maupun klasifikasi. Penjelasan detail beserta kode untuk setiap tahapan dapat dilihat pada notebook.

## Model Development

### Model Regresi untuk Prediksi Konsumsi Energi Kayu

#### 1. Random Forest Regressor (Baseline Model)

**Cara Kerja Random Forest Regressor:**

Random Forest Regressor adalah algoritma ensemble berbasis decision tree yang digunakan untuk tugas regresi. Cara kerjanya sebagai berikut:
- Algoritma membangun banyak pohon keputusan (decision tree) secara paralel.
- Setiap pohon dilatih menggunakan subset data yang diambil secara acak dari data pelatihan (teknik bootstrap sampling).
- Pada setiap node dalam pohon, pemilihan fitur yang digunakan untuk split juga dilakukan secara acak dari subset fitur yang tersedia.
- Setiap pohon menghasilkan prediksi sendiri, lalu hasil akhir regresi diambil sebagai rata-rata dari seluruh prediksi pohon (average voting).
- Proses ini membantu mengurangi overfitting dan meningkatkan generalisasi model.

**Parameter yang Digunakan pada Baseline Model:**
- `n_estimators=100`: Jumlah pohon yang dibangun dalam forest adalah 100.
- `random_state=42`: Seed random untuk memastikan hasil yang konsisten/reproducible.
- Parameter lain menggunakan nilai default dari library sklearn.

**Catatan:**  
Pada baseline model ini, tidak dilakukan tuning hyperparameter lebih lanjut. Model dilatih menggunakan fitur-fitur utama (Waste Energy, Biomass Losses and Co-products, Fuel Ethanol, Month, Year) beserta fitur lag dan rolling mean (lag12 dan rolling12) untuk menangkap pola musiman dan tren jangka panjang pada data time series.

Jika ingin menambahkan kelebihan/kekurangan:
- *Kelebihan:* Mampu menangani data non-linear, robust terhadap outlier, dan mengurangi risiko overfitting.
- *Kekurangan:* Interpretasi model lebih sulit dibandingkan model linear, dan waktu komputasi lebih tinggi untuk dataset besar.

#### 2. Linear Regression

**Penjelasan Berdasarkan Kode:**

Pada model kedua ini digunakan algoritma Linear Regression dari library `sklearn.linear_model`. Dataset yang digunakan adalah data konsumsi energi kayu (Wood Energy) beserta fitur-fitur utama hasil preprocessing, seperti fitur lag, rolling mean, encoding sektor, dan fitur numerik lainnya. Data dibagi menjadi data latih (train) dan data uji (test) dengan proporsi 80:20 menggunakan fungsi `train_test_split` dari sklearn. Artinya, 80% data digunakan untuk melatih model dan 20% sisanya digunakan untuk menguji performa model.

Langkah-langkah pada kode:
- Membuat objek model LinearRegression.
- Melatih model menggunakan data latih (`model_lr.fit(X_train, y_train)`).
- Melakukan prediksi pada data uji (`y_pred_lr = model_lr.predict(X_test)`).
- Menghitung metrik evaluasi: RMSE, MAE, dan R².
- Menampilkan hasil evaluasi dan visualisasi perbandingan antara nilai aktual dan prediksi.

**Cara Kerja Linear Regression:**

Linear Regression bekerja dengan mencari garis lurus terbaik yang meminimalkan jumlah kuadrat selisih antara nilai aktual dan nilai prediksi (least squares). Model ini mempelajari koefisien (slope dan intercept) dari data pelatihan, lalu menggunakan koefisien tersebut untuk memprediksi nilai target pada data uji. Model ini sangat mudah diinterpretasikan dan cocok sebagai baseline.

**Parameter yang Digunakan:**
- Semua parameter menggunakan default dari `LinearRegression` sklearn.

**Kelebihan dan Kekurangan:**
- *Kelebihan:* Mudah diinterpretasikan, proses training cepat, dan cocok untuk data dengan hubungan linier.
- *Kekurangan:* Tidak mampu menangkap hubungan non-linear dan sensitif terhadap outlier.

**Hasil Evaluasi Model Linear Regression:**
- RMSE: `15.2616`
- MAE: `11.4875`
- R²: `0.8922`

Nilai RMSE dan MAE pada model Linear Regression lebih tinggi dibandingkan Random Forest, menandakan bahwa model ini kurang mampu menangkap pola kompleks pada data. Namun, nilai R² yang cukup tinggi menunjukkan model ini masih dapat menjelaskan sebagian besar variasi data target dan layak dijadikan baseline awal sebelum menggunakan model yang lebih kompleks.

#### 3. Random Forest Regressor dengan Tuning Hyperparameter

**Penjelasan Cara Kerja Model:**

Random Forest Regressor adalah algoritma ensemble berbasis decision tree yang bekerja dengan membangun banyak pohon keputusan (decision tree) secara paralel. Setiap pohon dilatih menggunakan subset data yang diambil secara acak dari data pelatihan (bootstrap sampling). Pada setiap node dalam pohon, pemilihan fitur yang digunakan untuk split juga dilakukan secara acak dari subset fitur yang tersedia. Setiap pohon menghasilkan prediksi sendiri, lalu hasil akhir regresi diambil sebagai rata-rata dari seluruh prediksi pohon (average voting). Proses ini membantu mengurangi overfitting dan meningkatkan generalisasi model.

Pada model ketiga ini, Random Forest Regressor dioptimasi menggunakan teknik tuning hyperparameter dengan `GridSearchCV` dari sklearn. Tuning hyperparameter bertujuan untuk mencari kombinasi parameter terbaik agar model dapat memprediksi konsumsi Wood Energy dengan akurasi yang lebih tinggi. Proses tuning dilakukan dengan cross-validation, sehingga model diuji pada beberapa subset data untuk memastikan performa yang stabil dan tidak overfitting.

**Parameter yang Dituning dan Value-nya:**
- `n_estimators`: [50, 100, 200]  
  Jumlah pohon dalam hutan. Semakin banyak pohon, biasanya model lebih stabil namun waktu komputasi bertambah.
- `max_depth`: [None, 10, 20, 30]  
  Kedalaman maksimum setiap pohon. None berarti tidak dibatasi.
- `min_samples_split`: [2, 5, 10]  
  Jumlah minimum sampel yang dibutuhkan untuk membagi node.
- `min_samples_leaf`: [1, 2, 4]  
  Jumlah minimum sampel pada setiap daun (leaf).
- `bootstrap`: [True, False]  
  Apakah menggunakan bootstrap samples saat membangun pohon.

Parameter lain menggunakan default dari library sklearn.

**Langkah-langkah pada kode:**
1. Menentukan grid parameter yang akan diuji.
2. Membuat objek `RandomForestRegressor` dan `GridSearchCV` untuk melakukan pencarian parameter terbaik.
3. Melatih model pada data latih menggunakan cross-validation.
4. Mengambil model dengan parameter terbaik (`best_estimator_`) dan melakukan prediksi pada data uji.
5. Menghitung metrik evaluasi: RMSE, MAE, dan R².
6. Menampilkan hasil evaluasi dan visualisasi perbandingan antara nilai aktual dan prediksi.

**Hasil Evaluasi Model Random Forest dengan Tuning:**
- RMSE: `8.5988`
- MAE: `2.6882`
- R²: `0.9660`

Nilai RMSE dan MAE yang lebih rendah dibandingkan model baseline dan Linear Regression menunjukkan bahwa tuning hyperparameter berhasil meningkatkan akurasi model secara signifikan. Model ini sangat direkomendasikan untuk deployment karena mampu menangkap pola kompleks pada data time series konsumsi energi kayu.

**(Opsional) Kelebihan dan Kekurangan:**
- *Kelebihan:* Dengan tuning hyperparameter, model dapat mencapai performa optimal, mengurangi error prediksi, dan lebih robust terhadap variasi data.
- *Kekurangan:* Proses tuning membutuhkan waktu komputasi yang lebih lama karena harus mencoba banyak kombinasi parameter.

#### 4. Model Klasifikasi Random Forest Classifier

**Penjelasan Cara Kerja Model:**

Random Forest Classifier adalah algoritma ensemble berbasis decision tree yang digunakan untuk tugas klasifikasi. Model ini membangun banyak pohon keputusan (decision tree) secara paralel, di mana setiap pohon dilatih menggunakan subset data yang diambil secara acak (bootstrap sampling) dan subset fitur yang juga dipilih secara acak pada setiap node. Untuk prediksi klasifikasi, setiap pohon memberikan "vote" untuk kelas tertentu, dan hasil akhir ditentukan berdasarkan mayoritas suara (majority voting) dari seluruh pohon.

Pada proyek ini, Random Forest Classifier digunakan untuk mengklasifikasikan konsumsi energi kayu ke dalam tiga kategori: 'Rendah', 'Sedang', dan 'Tinggi'. Kategori ini dibuat menggunakan metode quantile (`pd.qcut`) agar distribusi kelas seimbang.

Sebelum pelatihan model, dilakukan **standarisasi fitur numerik menggunakan `StandardScaler`**. Standarisasi ini penting karena banyak algoritma machine learning, termasuk Random Forest, dapat bekerja lebih optimal jika fitur berada pada skala yang seragam, terutama ketika data memiliki rentang nilai yang sangat berbeda. Dengan standarisasi, proses pelatihan menjadi lebih stabil dan konvergen lebih cepat.

Selanjutnya, untuk **mengatasi data imbalance digunakan teknik SMOTE (Synthetic Minority Over-sampling Technique)**. SMOTE digunakan karena pada data klasifikasi sering kali terjadi ketidakseimbangan jumlah sampel antar kelas (misal: kelas 'Rendah' jauh lebih sedikit dari 'Tinggi'). Jika tidak diatasi, model cenderung bias ke kelas mayoritas. SMOTE bekerja dengan membuat sampel sintetis pada kelas minoritas sehingga distribusi kelas menjadi seimbang, yang pada akhirnya meningkatkan kemampuan model dalam mengenali semua kelas secara adil.

**Parameter yang Digunakan:**
- `n_estimators`: 200  
  Jumlah pohon dalam hutan. Semakin banyak pohon, model biasanya lebih stabil.
- `max_depth`: 10  
  Kedalaman maksimum setiap pohon. Membatasi kompleksitas pohon agar tidak overfitting.
- `random_state`: 42  
  Untuk memastikan hasil yang reproducible.
- `class_weight`: 'balanced'  
  Menyeimbangkan bobot kelas secara otomatis berdasarkan frekuensi kelas pada data pelatihan.

Parameter lain menggunakan default dari library sklearn.

**Langkah-langkah pada kode:**
1. Membuat label kategori konsumsi energi kayu menggunakan quantile (`pd.qcut`).
2. Memisahkan fitur (X) dan target (y) untuk klasifikasi.
3. Membagi data menjadi data latih dan data uji dengan stratifikasi agar proporsi kelas tetap seimbang.
4. Melakukan standarisasi fitur numerik menggunakan `StandardScaler` agar fitur berada pada skala yang sama dan model lebih stabil.
5. Mengatasi data imbalance dengan SMOTE untuk menyeimbangkan jumlah sampel pada setiap kelas sehingga model tidak bias terhadap kelas mayoritas.
6. Membuat dan melatih model Random Forest Classifier.
7. Melakukan prediksi pada data uji.
8. Mengevaluasi performa model menggunakan classification report (accuracy, precision, recall, F1-score).

**Hasil Evaluasi Model Klasifikasi:**
- Accuracy: `0.96`
- Precision (macro): `0.96`
- Recall (macro): `0.96`
- F1-score (macro): `0.96`

Model klasifikasi ini mampu mengklasifikasikan konsumsi energi kayu ke dalam tiga kategori dengan akurasi dan metrik evaluasi yang sangat baik, menandakan model dapat digunakan untuk segmentasi atau pengambilan keputusan berbasis kategori konsumsi energi kayu.

**(Opsional) Kelebihan dan Kekurangan:**
- *Kelebihan:* Mampu menangani data dengan banyak fitur, robust terhadap outlier, dan dapat mengatasi data imbalance dengan baik (berkat penggunaan SMOTE).
- *Kekurangan:* Interpretasi model lebih sulit dibandingkan model sederhana seperti decision tree tunggal, dan waktu komputasi lebih lama jika jumlah pohon sangat banyak.


## Evaluasi Model
**Keterkaitan dan Dampak terhadap Business Understanding**

Pada bagian ini, evaluasi model tidak hanya berfokus pada pencapaian metrik statistik, tetapi juga secara eksplisit menghubungkan hasil model dengan kebutuhan bisnis yang telah dirumuskan pada tahap Business Understanding. Evaluasi dilakukan untuk memastikan bahwa setiap solusi yang diusulkan benar-benar menjawab problem statement, mencapai goals, dan memberikan dampak nyata sesuai harapan.

### 1. Apakah Model Sudah Menjawab Problem Statement?

Problem statement utama dalam proyek ini adalah:
- Bagaimana memprediksi konsumsi energi kayu di masa mendatang secara akurat.
- Bagaimana mengelompokkan konsumsi energi kayu ke dalam kategori bisnis yang actionable (Rendah, Sedang, Tinggi).

**Hasil evaluasi model menunjukkan:**
- Model regresi Random Forest dengan hyperparameter tuning mampu memprediksi konsumsi energi kayu dengan RMSE 8.60, MAE 2.69, dan R² 0.97. Nilai R² yang sangat tinggi membuktikan model dapat menjelaskan hampir seluruh variasi konsumsi energi kayu, sehingga sangat relevan untuk perencanaan dan pengambilan keputusan.
- Model klasifikasi Random Forest Classifier menghasilkan akurasi, precision, recall, dan F1-score rata-rata makro sebesar 0.96. Ini membuktikan model mampu mengelompokkan konsumsi energi kayu ke dalam kategori yang tepat secara konsisten.

**Kesimpulan:**  
Kedua model telah secara langsung menjawab problem statement yang diajukan, baik dari sisi prediksi kuantitatif maupun kategorisasi konsumsi.

### 2. Apakah Model Berhasil Mencapai Goals yang Diharapkan?

Goals utama proyek ini adalah:
- Menyediakan alat prediksi yang akurat untuk mendukung perencanaan dan efisiensi operasional.
- Menyediakan sistem klasifikasi konsumsi untuk mendukung strategi bisnis dan pengambilan keputusan.

**Pencapaian model:**
- Model regresi memberikan error prediksi yang sangat rendah dan R² mendekati 1, memenuhi target akurasi yang diharapkan.
- Model klasifikasi memberikan akurasi dan F1-score tinggi pada semua kelas, membuktikan sistem klasifikasi siap digunakan untuk segmentasi, monitoring, dan penetapan prioritas intervensi.

**Kesimpulan:**  
Seluruh goals yang ditetapkan pada tahap Business Understanding telah tercapai dengan baik oleh model yang dikembangkan.

### 3. Apakah Solusi yang Dirancang Memberikan Dampak Nyata?

**Dampak nyata dari solusi model terhadap kebutuhan bisnis:**
- **Perencanaan & Efisiensi:** Prediksi yang akurat membantu perusahaan/instansi dalam mengoptimalkan rantai pasok, mengurangi biaya akibat prediksi yang meleset, dan meningkatkan efisiensi operasional.
- **Segmentasi & Monitoring:** Klasifikasi konsumsi energi kayu ke dalam kategori bisnis memudahkan monitoring, pelaporan, dan penetapan prioritas intervensi, sehingga strategi dapat lebih terarah.
- **Implementasi Nyata:** Model yang robust dan dapat diandalkan ini dapat langsung diintegrasikan ke dalam sistem perencanaan energi kayu, dashboard monitoring, atau sistem peringatan dini, sehingga memberikan nilai tambah nyata bagi pengambilan keputusan.

### Ringkasan Metrik Utama

**Regresi (Prediksi Konsumsi Energi Kayu):**
- **RMSE:**  
  - Random Forest Tuned: `8.60` (terendah, terbaik)
  - Linear Regression: `15.26`
- **MAE:**  
  - Random Forest Tuned: `2.69` (terendah)
  - Linear Regression: `11.49`
- **R²:**  
  - Random Forest Tuned: `0.97` (tertinggi)
  - Linear Regression: `0.89`

**Klasifikasi (Kategori Konsumsi):**
- **Akurasi:** `0.96`
- **Precision/Recall/F1-score (rata-rata):** `0.96`  
  (Stabil di semua kategori: Rendah, Sedang, Tinggi)

---

### Kesimpulan Akhir

Seluruh solusi yang dirancang telah:
- Menjawab setiap problem statement secara langsung,
- Mencapai semua goals yang diharapkan,
- Memberikan dampak nyata dan terukur pada proses pengambilan keputusan bisnis terkait konsumsi energi kayu.

**Rekomendasi:**  
Model dapat segera diimplementasikan untuk mendukung perencanaan, monitoring, dan pengambilan keputusan strategis di sektor energi kayu, serta menjadi dasar pengembangan sistem peringatan dini dan dashboard operasional yang lebih cerdas.

**---Akhir laporan---**


