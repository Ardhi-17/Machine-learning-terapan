## Data Preparation

Tahapan **Data Preparation** dilakukan secara sistematis agar data siap digunakan untuk membangun sistem rekomendasi yang akurat dan dapat direproduksi. Berikut adalah penjelasan lengkap setiap langkah yang dilakukan:

### 1. Pemilihan Fitur yang Relevan
- Dari dataset `movies_metadata.csv`, dipilih fitur penting: `movieId`, `title`, `genres`, `vote_average`, dan `vote_count`.
- Pemilihan fitur ini dilakukan untuk memfokuskan proses analisis dan modeling pada atribut yang relevan terhadap sistem rekomendasi.

### 2. Penanganan Missing Value
- Diperiksa missing value pada kolom `title`, `vote_average`, dan `vote_count`.
- Baris dengan nilai kosong pada kolom-kolom tersebut dihapus untuk menghindari gangguan saat pemodelan.
- Contoh baris yang dihapus:

| Index  | movieId | genres                                      | title | vote_average | vote_count |
|--------|---------|---------------------------------------------|-------|--------------|------------|
| 19729  | 82663   | [{'id': 28, 'name': 'Action'}, ...]         | NaN   | NaN          | NaN        |

### 3. Penanganan Data Duplikat
- Pemeriksaan duplikasi dilakukan berdasarkan kolom `movieId`.
- Sebanyak 30 data duplikat ditemukan dan hanya satu yang dipertahankan untuk memastikan setiap film unik.

### 4. Pengurutan Data
- Dataset `ratings` diurutkan berdasarkan `userId`.
- Dataset `movies_selected` diurutkan berdasarkan `movieId`.
- Tujuan pengurutan ini adalah untuk mempermudah transformasi data dan pembacaan model.

### 5. Konversi Format Genre
- Kolom `genres` awalnya dalam bentuk list of dictionary seperti:

```python
"[{'id': 28, 'name': 'Action'}, {'id': 53, 'name': 'Thriller'}]"
```

- Diubah menjadi list of string seperti:

```python
['Action', 'Thriller']
```

- Proses ini menggunakan `literal_eval` dan sangat penting untuk vektorisasi dalam metode content-based filtering.

### 6. Penggabungan Dataset
- Dataset `ratings` digabung dengan dataset `movies_selected` berdasarkan `movieId`.
- Setelah penggabungan, fitur yang tidak relevan seperti `timestamp`, `vote_average`, dan `vote_count` dihapus.

### 7. Shuffling Dataset
- Dataset akhir diacak menggunakan `shuffle()` dari `sklearn.utils` untuk menghindari urutan data yang bias.
- Diambil 30.000 baris secara acak sebagai dataset akhir (`df_final`) yang akan digunakan dalam modeling.

### 8. Encoding Fitur Kategorikal
- Encoding dilakukan pada kolom `userId` dan `movieId` menggunakan teknik `LabelEncoder` untuk keperluan *neural network* atau *embedding-based recommendation*.

```python
from sklearn.preprocessing import LabelEncoder

user_encoder = LabelEncoder()
movie_encoder = LabelEncoder()

df_final['user_encoded'] = user_encoder.fit_transform(df_final['userId'])
df_final['movie_encoded'] = movie_encoder.fit_transform(df_final['movieId'])
```

### 9. Normalisasi Rating
- Kolom `rating` diperiksa untuk memastikan berada dalam rentang 0.5 hingga 5.0.
- Data yang berada di luar rentang ini (jika ada) dihapus.
- Normalisasi dapat dilakukan (misal ke skala 0–1) bila digunakan model yang sensitif terhadap skala input, namun dalam laporan ini normalisasi eksplisit belum dilakukan.

### 10. Split Dataset
- Dataset `df_final` dibagi menjadi data latih dan data uji untuk validasi model.
- Teknik pembagian data menggunakan `train_test_split()` dari `sklearn.model_selection`.

```python
from sklearn.model_selection import train_test_split

X = df_final[['user_encoded', 'movie_encoded']]
y = df_final['rating']

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

---
