# Laporan Proyek Machine Learning - Nama Anda

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
Exploratory Data Analysis
Analisis Distribusi Data
Sebagian besar variabel energi menunjukkan distribusi yang tidak normal
Terdapat beberapa outlier yang menunjukkan periode konsumsi ekstrem
Pola musiman terlihat jelas dalam data bulanan
Analisis Korelasi
Korelasi positif yang kuat antara beberapa jenis energi terbarukan
Hubungan yang signifikan antara sektor dan jenis energi yang dikonsumsi
Pola korelasi yang berbeda untuk setiap sektor
Analisis Temporal
Tren peningkatan konsumsi energi terbarukan dari waktu ke waktu
Pola musiman yang konsisten dalam konsumsi energi
Perubahan signifikan dalam komposisi energi terbarukan selama beberapa dekade
Analisis Sektor
Variasi konsumsi energi antar sektor
Dominasi sektor tertentu dalam konsumsi jenis energi tertentu
Perubahan pola konsumsi sektor dari waktu ke waktu
Catatan Penting:
Nilai 0 dalam dataset menunjukkan "Not Available", "No Data Reported", atau "Not Meaningful"
Kolom Total Renewable Energy merupakan penjumlahan dari kolom lainnya
Data tahun 2024 tidak lengkap dan perlu diperhatikan dalam analisis


## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

