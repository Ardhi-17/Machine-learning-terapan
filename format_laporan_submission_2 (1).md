# Laporan Proyek Machine Learning - Ahcmad Ardhi Arridho

## Project Overview
Dalam beberapa tahun terakhir, pertumbuhan platform digital seperti Netflix, Disney+, dan Amazon Prime telah mengubah cara masyarakat mengakses hiburan. Ribuan judul film tersedia dalam berbagai genre, namun ironi justru muncul ketika pengguna merasa kesulitan memilih tontonan yang sesuai karena terlalu banyak pilihan. Fenomena ini dikenal sebagai information overload, yang dapat mengurangi pengalaman pengguna dalam menikmati layanan tersebut [[1]](https://www.nowpublishers.com/article/Details/INR-066).

Untuk mengatasi masalah ini, dibutuhkan sistem yang mampu memberikan rekomendasi film secara otomatis dan relevan sesuai dengan minat masing-masing pengguna. Salah satu solusi yang efektif adalah penerapan sistem rekomendasi berbasis machine learning, yang memanfaatkan data pengguna seperti riwayat tontonan, rating, dan preferensi genre untuk menyarankan film yang sesuai. Dengan pendekatan ini, pengalaman pengguna dapat dipersonalisasi, waktu pencarian dapat ditekan, dan retensi pengguna pada platform dapat meningkat secara signifikan [[2]](https://link.springer.com/book/10.1007/978-3-319-29659-3).

Proyek ini penting untuk diselesaikan karena sistem rekomendasi bukan hanya alat bantu teknis, tetapi juga strategi penting dalam meningkatkan kepuasan pengguna dan nilai bisnis platform digital. Metode content-based filtering dan collaborative filtering menjadi pendekatan utama dalam proyek ini, di mana content-based akan menilai kesamaan antara film berdasarkan fitur seperti genre atau sutradara, sedangkan collaborative filtering akan memanfaatkan pola perilaku pengguna lain yang serupa untuk memberi saran [[3]](https://arxiv.org/abs/2010.03240).

Hasil riset juga menunjukkan bahwa sistem rekomendasi berbasis pembelajaran mesin telah berhasil diterapkan secara luas dalam dunia industri dan akademik. Zhang dan Chen [[1]](https://www.nowpublishers.com/article/Details/INR-066) menyoroti pentingnya aspek explainability dalam sistem rekomendasi, sedangkan Aggarwal [[2]](https://link.springer.com/book/10.1007/978-3-319-29659-3) menyusun kerangka teoritis dan praktis dalam pengembangan sistem rekomendasi modern. Selain itu, Sari et al. [[4]](https://ejournal.umm.ac.id/index.php/repositor/article/view/30715) telah membuktikan efektivitas metode item-based collaborative filtering dalam studi kasus di platform film lokal. Dengan latar belakang tersebut, proyek ini diharapkan tidak hanya menjadi solusi praktis, tetapi juga kontribusi ilmiah dalam pengembangan sistem cerdas untuk rekomendasi film.

#### **Pentingnya Proyek Ini**
1. Mengatasi Overload Informasi: Dengan banyaknya pilihan film, pengguna sering kali merasa kewalahan dan kesulitan dalam menemukan film yang sesuai dengan selera mereka.
2. Personalisasi Pengalaman: Sistem rekomendasi memungkinkan personalisasi, yang dapat meningkatkan kepuasan dan loyalitas pengguna terhadap platform.
3. Efisiensi Waktu: Dengan rekomendasi yang tepat, pengguna dapat menghemat waktu dalam mencari film yang ingin ditonton.
4. Pemanfaatan Data: Data rating dan metadata film yang tersedia dalam jumlah besar memberikan peluang untuk penerapan machien learning secara optimal.

#### **Metodologi yang digunakan**
Proyek ini akan menggabungkan metode content-based filtering dan collaborative filtering untuk membangun sistem rekomendasi yang efektif. Content-based filtering menyarankan film berdasarkan kemiripan konten (seperti genre), sedangkan collaborative filtering mempertimbangkan perilaku pengguna lain yang mirip. Kombinasi kedua metode ini diharapkan dapat meningkatkan akurasi dan relevansi rekomendasi yang diberikan kepada pengguna.

## Business Understanding
Dalam konteks bisnis platform digital seperti layanan streaming film, salah satu tantangan utama adalah mempertahankan kepuasan dan keterlibatan pengguna. Banyak pengguna merasa kewalahan dalam memilih film karena terlalu banyak pilihan dan tidak adanya panduan atau rekomendasi yang relevan. Hal ini berdampak pada menurunnya waktu tonton, kepuasan pengguna, dan potensi churn (kehilangan pelanggan). Tantangan bisnis yang dihadapi meliputi :
### Problem Statements
**1. Pengguna kesulitan memilih film karena terlalu banyak pilihan (choice overload)**
Hal ini menyebabkan pengguna kehilangan minat, menghabiskan waktu tanpa menonton, dan berpotensi meninggalkan platform tanpa melakukan aktivitas berarti.
**2. Kurangnya sistem rekomendasi personal yang berdampak pada loyalitas pengguna.** 
Tanpa pengalaman personalisasi, pengguna merasa kurang dihargai dan cenderung beralih ke platform pesaing yang lebih relevan dengan kebutuhan mereka. 
**3. Data pengguna tidak dimanfaatkan secara optimal untuk meningkatkan engagement dan monetisasi.**
Banyak platform memiliki data seperti riwayat tontonan dan rating, namun belum diolah untuk menghasilkan rekomendasi yang bisa mendorong peningkatan waktu tonton atau konversi ke pelanggan berbayar.
### Goals
**1. Meningkatkan efisiensi dan kenyamanan pengguna dalam memilih film**
Dengan sistem rekomendasi, pengguna akan langsung diarahkan pada film yang kemungkinan besar disukai, sehingga menghemat waktu dan meningkatkan kepuasan.

**2. Meningkatkan loyalitas dan retensi pengguna melalui pengalaman yang dipersonalisasi**
Pengguna yang merasakan manfaat dari saran yang relevan akan lebih mungkin bertahan dan terus menggunakan layanan.

**3. Mengubah data perilaku pengguna menjadi nilai bisnis nyata**
Dengan memanfaatkan data historis (rating, genre, waktu tonton), sistem dapat membantu tim pemasaran, pengembang konten, dan manajemen dalam mengambil keputusan strategis yang berdampak langsung pada performa bisnis.

### Solution Approach
Untuk mengatasi berbagai permasalahan yang telah diuraikan sebelumnya serta mencapai tujuan yang telah ditetapkan, maka solusi yang ditawarkan adalah sebagai berikut 

**1. Content-Based Filtering (CBF)**
Menggunakan informasi seperti genre, rating, title untuk menemukan film yang mirip dengan yang pernah ditonton atau disukai pengguna. Cocok untuk pengguna baru yang belum banyak memberi rating.

**2. Collaborative Filtering (CF) berbasis Neural Network Embedding**
 Menggunakan data rating pengguna dan menerapkan embedding untuk user ID dan movie ID, lalu melatih model neural network untuk memprediksi rating antar pasangan user–movie yang belum pernah terjadi.

**3. Evaluasi dan Tuning Model**
Mengukur performa sistem rekomendasi menggunakan metrik RMSE dan MAE. Model yang paling optimal akan dipilih berdasarkan performa pada data validasi dan stabilitas hasil.
    
## Data Understanding
Dataset yang digunakan dalam proyek ini adalah data yang berisikan variabel variabel tentang rating pengguna terhadapat sebuah film dan juga metadata film seperti judul, genre, rating, bahasa, tahun rili dan lainnya. Data Bersumber dari [Kaggle - Movie Recommendation Data](https://www.kaggle.com/datasets/rohan4050/movie-recommendation-data)

| Nama Dataset         | Jumlah Baris     | Jumlah Kolom | Tipe Data | Deskripsi                                                                 |
|----------------------|------------------|---------------|--------------|---------------------------------------------------------------------------|
| movies_metadata.csv  | 45.466 baris     | 24 kolom      | Object & float64      | Berisi informasi deskriptif tentang film seperti judul, genre, dan rilis |
| ratings.csv          | 100836 baris     | 4 kolom       | int64 & float64       | Berisi interaksi pengguna berupa rating terhadap film                    |


Variabel-variabel pada dataset Movie Recommendation ini adalah sebagai berikut:
**1. Dataset Rating Penggunan (rating.csv)**
| Variabel   | Deskripsi                                                  |
|------------|-------------------------------------------------------------|
| userId     | ID unik yang merepresentasikan pengguna                     |
| movieId    | ID unik yang merepresentasikan film                         |
| rating     | Skor yang diberikan oleh pengguna terhadap film (1–5)       |
| timestamp  | Waktu ketika pengguna memberikan rating (format UNIX time) |

**2. Dataset Metadata Film (movies_metadata.csv)**
| Kolom                  | Deskripsi                                                  |
|------------------------|------------------------------------------------------------|
| adult                 | Menunjukkan apakah film untuk dewasa (True/False)           |
| belongs_to_collection | Informasi tentang koleksi atau seri film                    |
| budget                | Anggaran produksi film (dalam USD)                          |
| genres                | Daftar genre film                                           |
| homepage              | URL website resmi film                                      |
| id                    | ID unik film                                                |
| imdb_id               | ID film di IMDb (contoh: tt1234567)                         |
| original_language     | Bahasa asli film                                            |
| original_title        | Judul asli film                                             |
| overview              | Sinopsis atau deskripsi singkat film                        |
| popularity            | Skor popularitas film                                       |
| poster_path           | Path/link poster film                                       |
| production_companies  | Daftar perusahaan produksi                                  |
| production_countries  | Negara tempat produksi dilakukan                            |
| release_date          | Tanggal rilis film (format YYYY-MM-DD)                      |
| revenue               | Pendapatan kotor film (dalam USD)                           |
| runtime               | Durasi film dalam satuan menit                              |
| spoken_languages      | Bahasa yang digunakan dalam film                            |
| status                | Status rilis film (misalnya: Released)                      |
| tagline               | Slogan promosi film                                         |
| title                 | Judul utama film                                            |
| video                 | Menunjukkan apakah ada video terkait (True/False)           |
| vote_average          | Rata-rata skor rating pengguna (skala 1–10)                 |
| vote_count            | Jumlah total vote atau ulasan pengguna                      |

**Missing Value pada dataset movies_metadata.csv**
| Kolom                  | Jumlah Missing Value |
|------------------------|----------------------|
| adult                  | 0                    |
| belongs_to_collection  | 40.972               |
| budget                 | 0                    |
| genres                 | 0                    |
| homepage               | 37.684               |
| id                     | 0                    |
| imdb_id                | 17                   |
| original_language      | 11                   |
| original_title         | 0                    |
| overview               | 954                  |
| popularity             | 5                    |
| poster_path            | 386                  |
| production_companies   | 3                    |
| production_countries   | 3                    |
| release_date           | 87                   |
| revenue                | 6                    |
| runtime                | 263                  |
| spoken_languages       | 6                    |
| status                 | 87                   |
| tagline                | 25.054               |
| title                  | 6                    |
| video                  | 6                    |
| vote_average           | 6                    |
| vote_count             | 6                    |

*Pada dataset rating.csv, tidak ditemukan missing value.*

###  Exploratory Data Analysis
#### Analisis Distribusi Data
pada bagian ini, kita akan melakukan explorasi pada dataset untuk mendapatkan insight yang dibutuhkan dalam pembuatan model nantinya.

<p align="center">
    <img src="https://github.com/user-attachments/assets/86c90c65-4e06-492c-9b56-26bac3a6c33f" width="700"/>
</p>    
<p align="center"><em>Gambar:Presentasi Distribusi Rating</em></p>

**Gambar ini menunjukkan bahwa Rating 4.0 adalah yang paling umum diberikan, mencakup 26.6% dari total rating, Rating 3.0 di posisi kedua dengan 19.9% dari total rating dan Mayoritas rating (>75%) berada di range 3.0-5.0, menunjukkan kecenderungan rating positif**





<p align="center">
  <img src="https://github.com/user-attachments/assets/79f2bca7-95d4-4f1d-b20a-d5d5cbfcbfdb" width="700"/><br>
  <em>Gambar: Distribusi Rating Pengguna</em>
</p>

**Berdasarkan visualisasi distribusi rating di bawah, terlihat distribusi yang tidak merata (timpang), Hal ini menunjukkan bahwa pengguna cenderung memberikan rating yang lebih tinggi (3.0-5.0), Rating 0.5 memiliki frekuensi terendah (sekitar 1,500 rating), Rating 1.5 dan 2.5 juga relatif rendah (masing-masing sekitar 2,000 dan 5,000 rating), Rating 3.0 memiliki frekuensi tinggi (sekitar 20,000 rating), Rating 4.0 memiliki frekuensi tertinggi (sekitar 25,000 rating) dan Rating 5.0 memiliki frekuensi moderat (sekitar 13,000 rating)**


<p align="center">
  <img src="https://github.com/user-attachments/assets/c0230764-4f84-4f7a-bc28-8c2654d31df2" width="700"/><br>
  <em>Gambar: Distribusi Genre Film</em>
</p>

**Berdasarkan visualisasi distribusi genre film di bawah, dapat dilihat beberapa insight penting dimana. Dimana genre Drama mendominasi dengan jumlah film terbanyak (sekitar 20,000 film), Comedy dan Action menempati posisi kedua dan ketiga dengan masing-masing sekitar 12,500 dan 7,000 film, Genre-genre seperti Thriller, Romance, dan Horror memiliki jumlah film yang moderat (sekitar 5,000-7,000 film), Genre Documentary, Adventure, dan Mystery memiliki jumlah film yang relatif sedikit (2,500-4,000 film) dan Genre-genre khusus seperti War, Western, dan TV Movie memiliki jumlah film yang sangat sedikit (di bawah 2,000 film)**

### Pemberian Skor pada film (Weighted Score)

**Weighted score** merupakan metode penilaian yang digunakan untuk menentukan skor akhir sebuah film dengan mempertimbangkan dua aspek utama, yaitu rata-rata rating film (`vote_average`) dan jumlah rating yang diterima (`vote_count`). Pendekatan ini bertujuan agar film dengan jumlah rating yang sedikit namun memiliki rating tinggi tidak secara otomatis menempati peringkat teratas, sehingga hasil rekomendasi menjadi lebih adil dan merepresentasikan preferensi pengguna secara lebih akurat.

Rumus weighted score yang umum digunakan (sering disebut juga sebagai IMDB weighted rating) adalah sebagai berikut:

`Weighted Score = (v / (v + m)) * R + (m / (v + m)) * C`

dengan keterangan:
- `R` = rata-rata rating film (`vote_average`)
- `v` = jumlah rating film (`vote_count`)
- `m` = ambang minimum jumlah rating agar film layak dipertimbangkan (misal: persentil ke-90 dari `vote_count`)
- `C` = rata-rata rating dari seluruh film dalam dataset

Dengan menggunakan rumus ini, film yang memiliki banyak rating dan rating rata-rata yang tinggi akan mendapatkan skor lebih baik, sementara film dengan rating tinggi namun jumlah rating sedikit tidak langsung mendominasi peringkat teratas.

Berikut ini adalah hasilnya :

<p align="center">
  <img src="https://github.com/user-attachments/assets/4ff00c82-c8db-4dc9-b195-b23f8c256649" width="700"/><br>
  <em>Gambar: 10 Film Dengan Skor Tertinggi (Weighted Score)</em>
</p>


**10 Film dengan Jumlah Rating Terbanyak:**

| No. | Judul Film                         | Rata-rata Rating (`mean_ratings`) | Total Rating (`total_ratings`) |
|-----|------------------------------------|-----------------------------------|---------------------------------|
| 1   | The Million Dollar Hotel           | 4.429                             | 317                             |
| 2   | Terminator 3: Rise of the Machines | 4.197                             | 307                             |
| 3   | Solaris                            | 4.144                             | 282                             |
| 4   | The 39 Steps                        | 4.231                             | 251                             |
| 5   | Monsoon Wedding                    | 3.750                             | 238                             |
| 6   | Three Colors: Red                  | 4.032                             | 237                             |
| 7   | Once Were Warriors                 | 4.225                             | 220                             |
| 8   | License to Wed                     | 4.273                             | 218                             |
| 9   | The Passion of Joan of Arc         | 3.446                             | 202                             |
| 10  | 48 Hrs.                            | 3.846                             | 201                             |


Setelah melakukan explorasi data. didapatkan insight dari Eksplorasi Data sebagai berikut:
**Distribusi Genre dan Rating:**
1. Drama dan Comedy mendominasi dengan total >33,000 film
2. Rating 4.0 paling umum (26.6% dari total)
3. 75% rating berada di range 3.0-5.0
4. Genre khusus seperti War dan Western memiliki jumlah film terbatas
5. Terdapat bias positif yang kuat dalam pemberian ratin

**Analisis 10 Film dengan Rating Terbanyak:**
1. "The Million Dollar Hotel" memiliki rating rata-rata tertinggi (4.43) dengan 317 rating
2. "Terminator 3" di posisi kedua dengan rating 4.20 dari 307 rating
3. "Solaris" di posisi ketiga dengan rating 4.14 dari 282 rating
4. Mayoritas film dalam top 10 memiliki rating di atas 4.0
5. Total rating untuk film-film top 10 berkisar antara 200-320 rating

**Analisis Film dengan Skor Tertinggi:**
1. "Planet Earth II" memperoleh skor tertinggi (9.08) dengan vote_average 9.5
2. Film dokumenter dan series mendominasi top 10 (Planet Earth, Cosmos)
3. Film klasik seperti "The Shawshank Redemption" dan "The Godfather" konsisten di top 10
4. Film-film Asia seperti "Your Name" dan "Dilwale Dulhania Le Jayenge" menunjukkan kualitas tinggi
5. Weighted score mempertimbangkan jumlah vote, menghasilkan ranking yang lebih representatif

## Data Preparation

1. Memilih fitur yang relevan pada dataset yang sudah digabung untuk memudahkan proses preprocessing data dan juga training model. Fitur yang dipilih adalah `movieId`, `genres`,`title`, `vote_average`,`vote_count`
2. Menangani Missing Value pada fitur yang dipilih 

| Index  | movieId | genres                                                                                   | title | vote_average | vote_count |
|--------|---------|------------------------------------------------------------------------------------------|-------|--------------|------------|
| 19729  | 82663   | [{'id': 28, 'name': 'Action'}, {'id': 53, 'name': 'Thriller'}]                           | NaN   | NaN          | NaN        |
| 29502  | 122662  | [{'id': 16, 'name': 'Animation'}, {'id': 878, 'name': 'Science Fiction'}]               | NaN   | NaN          | NaN        |
| 35586  | 249260  | [{'id': 10770, 'name': 'TV Movie'}, {'id': 28, 'name': 'Action'}]                        | NaN   | NaN          | NaN        |

4. Menangani Data Duplikat pada kolom `moveId`, data duplikat berjumlah 30 data dan di hapus lalu disisakan baris pertama dari setiap duplikatnya.
5. Mengurutkan data pengguna berdasarkan ID untuk memudahkan analisa data rating dan movie ID.
6. 
| Index | userId | movieId | rating | timestamp  |
|-------|--------|---------|--------|------------|
| 180   | 1      | 2716    | 5.0    | 964983414  |
| 181   | 1      | 2761    | 5.0    | 964982703  |
| 182   | 1      | 2797    | 4.0    | 964981710  |
| 183   | 1      | 2826    | 4.0    | 964980523  |
| 184   | 1      | 2858    | 5.0    | 964980868  |

6. Mengubah fitur `genres` pada dataset movies ke dalam bentuk list untuk memudahkan proses ekstraksi fitur dan juga vektorisasi.
7. Gabungkan Dataset movies yang sudah di preprocessing dengan dataset ratings dan hapus kolom yang tidak diperlukan seperti `timestamp`, `vote_average`, `vote_count`
**Tujuan: menghubungkan metadata film seperti genre dan title film dengan perilaku pengguna (rating) agar model dapat melakukan personalisasi.**
8. Ambil 30.000 dataset secara acak dari total kesuluruhan dataset dengan teknik sampling shuffle. 
9. Menggunakan TfidfVectorizer untuk melakukan pembobotan.

## Modeling
Sistem rekomendasi dikembangkan untuk menjawab permasalahan utama yaitu bagaimana membantu pengguna menemukan film yang relevan dan meningkatkan engagement pada platform digital. Dalam proyek ini, dua pendekatan sistem rekomendasi diterapkan:
Tujuan:

-  Memberikan Top-N rekomendasi film untuk setiap pengguna.

- Membandingkan dua pendekatan yang berbeda untuk melihat efektivitas dan keakuratannya dalam memberikan rekomendasi.

### 1. Model Content Based Filtering
Content-Based Filtering (CBF) merupakan metode rekomendasi yang menyarankan film kepada pengguna berdasarkan atribut konten film itu sendiri, seperti genre, sutradara, atau aktor. Pada implementasi ini, sistem menggunakan genre sebagai satu-satunya fitur utama, tanpa melibatkan sinopsis atau teks deskriptif lain seperti overview.

Model akan mencari film-film dengan genre yang mirip dengan film yang disukai pengguna sebelumnya, lalu menyarankan film-film tersebut menggunakan perhitungan cosine similarity terhadap vektor genre.
##### **Langkah-langkah Pengerjaan**
1. Persiapan Data
-  Menghapus entri film yang duplikat berdasarkan movieId agar setiap film hanya muncul satu kali.
- Mengonversi kolom genres yang sebelumnya berbentuk list menjadi string (dipisahkan koma) agar dapat diproses dengan TF-IDF.
2. Ekstraksi Fitur: TF-IDF pada Genre
- Menggunakan TfidfVectorizer dari sklearn untuk mengubah data genres menjadi matriks numerik.
- Matriks hasil ekstraksi memiliki dimensi (2542, 22), artinya terdapat 2542 film dan 22 genre unik yang terekstrak.
3. Perhitungan Kemiripan
- Menggunakan cosine similarity untuk menghitung kemiripan antar film berdasarkan genre.
- Hasil perhitungan disimpan dalam bentuk DataFrame, dengan nama film sebagai index dan kolom.
4. Fungsi Rekomendasi
- Membuat fungsi film_recommendations() yang Menerima input judul film dan mengembalikan daftar Top-10 film lain yang paling mirip berdasarkan genre
#### **Parameter yang Digunakan**
1. TfidfVectorizer(): default parameter
2. cosine_similarity(): perhitungan tanpa parameter tambahan (standard sklearn)

| Parameter                     | Nilai / Penjelasan                                                         |
|-------------------------------|----------------------------------------------------------------------------|
| Metode Similarity             | `cosine_similarity(tfidf_matrix)`                                         |
| Output Similarity Matrix      | DataFrame berukuran (2542 x 2542) – antar semua kombinasi film            |
| Fungsi Rekomendasi            | `film_recommendations(nama_film, similarity_data, k=10)`                  |
| Jumlah Top-N Rekomendasi      | 10 film teratas berdasarkan kemiripan genre                               |
| Index & Kolom Similarity DF   | `title` sebagai indeks dan kolom                                          |


##### **Top-N Recommendation Sebagai Output**
Berikut adalah tabel rekomendasi film "Pulp Fiction" yang sudah dilengkapi dengan nomor urutan (Top-10):
| No. | Judul Film                     | Genre            |
|-----|--------------------------------|------------------|
| 1   | Incognito                      | Crime, Thriller  |
| 2   | Snatch                         | Thriller, Crime  |
| 3   | Payment Deferred               | Crime, Thriller  |
| 4   | The Key to Reserva             | Crime, Thriller  |
| 5   | Ocean's Twelve                 | Thriller, Crime  |
| 6   | Swimming Pool                  | Thriller, Crime  |
| 7   | Bloodline                      | Crime, Thriller  |
| 8   | Pacific Heights                | Crime, Thriller  |
| 9   | Sin City: A Dame to Kill For   | Crime, Thriller  |
| 10  | Get Carter                     | Crime, Thriller  |

##### **Kelebihan dan Kekurangan**
**Kelebihan:**
- Cocok untuk sistem rekomendasi awal atau saat data rating tidak tersedia.
- Rekomendasi konsisten untuk genre yang disukai pengguna.
- Mudah diinterpretasikan dan cepat diolah (genre = fitur yang ringkas).

**Kekurangan:**
- Tidak mempertimbangkan rating pengguna atau kualitas film (bisa saja merekomendasikan film dengan rating rendah).
- Tidak mampu mengidentifikasi preferensi non-genre seperti gaya penyutradaraan atau sinematografi.
- Film dengan genre unik atau langka memiliki potensi minim untuk direkomendasikan.
- 
## Evaluation Model Content Based Filtering
Dalam proyek ini, evaluasi terhadap model Content-Based Filtering (CBF) dilakukan menggunakan metrik precision, yaitu rasio antara jumlah rekomendasi yang relevan dengan jumlah total rekomendasi yang diberikan.
Formula Precision:

    Precision = (Jumlah Rekomendasi Relevan / Total Rekomendasi) × 100%

**Langkah Evaluasi:**
1. Film yang dijadikan referensi: Pulp Fiction.
2. Genre target (relevan): Crime dan Thriller.
3. Fungsi evaluasi memeriksa apakah setiap film yang direkomendasikan mengandung kedua genre tersebut.
4. Hasil evaluasi: dari 10 film yang direkomendasikan, semuanya mengandung genre Crime dan Thriller.

**Hasil Evaluasi:**
| Jumlah Rekomendasi Relevan | Total Rekomendasi | Precision |
| -------------------------- | ----------------- | --------- |
| 10                         | 10                | 100.00%   |
### Hubungan dengan Business Understanding

Evaluasi ini secara langsung menjawab dan mendukung Business Understanding dari proyek, sebagai berikut:
1. Apakah sudah menjawab setiap problem statement?
Ya. Salah satu permasalahan utama adalah bagaimana memberikan rekomendasi yang relevan dan sesuai preferensi pengguna. Dengan precision 100%, model CBF membuktikan bahwa ia mampu menangkap esensi dari film referensi dan menggunakannya untuk menyarankan film serupa.
2. Apakah berhasil mencapai setiap goals?
Ya. Tujuan dari pendekatan Content-Based Filtering adalah memberikan rekomendasi berbasis konten yang mirip dengan film favorit pengguna. Model berhasil menyarankan film dengan genre yang sangat mirip, memenuhi ekspektasi dari sisi kualitas konten yang disarankan.
3. Apakah solusi yang dirancang berdampak?
Ya. Model ini berguna dalam situasi cold-start, yaitu ketika data interaksi pengguna sangat terbatas. Model mampu memberikan saran yang konsisten tanpa perlu mengetahui riwayat rating pengguna. Dalam konteks bisnis, pendekatan ini:
- Meningkatkan engagement pengguna baru.
- Meningkatkan retensi awal karena pengguna cepat mendapat rekomendasi relevan.
- Menurunkan risiko bounce rate akibat saran yang tidak cocok.

### 2. Model Collaborative Filtering
Collaborative Filtering adalah teknik sistem rekomendasi yang menyarankan film berdasarkan kesamaan perilaku atau preferensi pengguna lain. Pendekatan ini berasumsi bahwa pengguna yang menyukai film yang sama kemungkinan besar akan menyukai film serupa lainnya. Model ini tidak menggunakan konten film secara langsung, melainkan mengandalkan pola interaksi antara pengguna dan item (dalam hal ini: rating film).

Model dikembangkan dengan pendekatan embedding-based neural network, yaitu memetakan userId dan movieId ke dalam ruang vektor berdimensi rendah, dan menggunakan hasil interaksinya untuk memprediksi rating yang diberikan.
##### **Langkah-langkah Pengerjaan**
1. Persiapan dan Encoding Data
- Dataset df_movies_ratings telah melalui tahap preprocessing sebelumnya.
- userId dan movieId di-encode menjadi integer menggunakan mapping dictionary agar bisa digunakan dalam embedding layer.
- Kolom ratings dinormalisasi ke skala 0–1 agar sesuai dengan output sigmoid model.
2. Pembagian Data
Dataset diacak dan dibagi menjadi 80% data pelatihan dan 20% data validasi.
3. Arsitektur Model Neural Network
Model dibangun dengan class RecommenderNet yang merupakan turunan dari tf.keras.Model. Arsitektur terdiri dari:
- User Embedding Layer dan Movie Embedding Layer
- User Bias dan Movie Bias (untuk menangkap kecenderungan masing-masing)
- Dot Product antara user dan movie vector
- Aktivasi Sigmoid di output
4. Pelatihan Model
Model dilatih selama 50 epoch dengan batch size = 64, menggunakan:
- Loss function: Mean Squared Error (MSE)
- Optimizer: Adam
##### **Parameter yang digunakan**
**Parameter Arsitektur Model (RecommenderNet)**
| Parameter              | Nilai / Penjelasan                                                           |
|------------------------|------------------------------------------------------------------------------|
| `embedding_size`       | 50 – Dimensi vektor embedding                                                |
| `user_embedding`       | Embedding(user: 610 x 50)                                                    |
| `movie_embedding`      | Embedding(movie: 2790 x 50)                                                  |
| `user_bias`            | Embedding(user: 610 x 1) – untuk menangkap kecenderungan pengguna            |
| `movie_bias`           | Embedding(movie: 2790 x 1) – untuk menangkap kecenderungan film              |
| `regularization`       | L2 regularization (`keras.regularizers.l2(1e-6)`)                            |
| `activation`           | Sigmoid – menjaga output dalam skala 0–1                                     |
**Parameter Pelatihan Model**
| Parameter              | Nilai / Penjelasan                                                           |
|------------------------|------------------------------------------------------------------------------|
| `loss`                 | Mean Squared Error (MSE)                                                     |
| `optimizer`            | Adam (`learning_rate=0.001`)                                                 |
| `metrics`              | RMSE (`RootMeanSquaredError`), MAE (`MeanAbsoluteError`)                     |
| `epochs`               | 50                                                                           |
| `batch_size`           | 64                                                                           |
| `validation_data`      | 20% dari dataset                                                              |
| `verbose`              | 1 – Menampilkan log selama pelatihan                                         |
| `shuffle`              | Data diacak (`sample(frac=1, random_state=42)`) sebelum split train/val      |

Hasil Training Model
| Metrik | Data Train | Data Validasi |
|--------|------------|----------------|
| RMSE   | 0.1862     | 0.1987         |
| MAE    | 0.1435     | 0.1542         |

 ##### **Modeling dengan Tuning Hyperparameter**
 
 Tuning hyperparameter bertujuan untuk meningkatkan performa model dengan menemukan kombinasi parameter terbaik. Pada tahap ini dilakukan grid search manual terhadap beberapa kombinasi hyperparameter utama yang mempengaruhi kinerja model embedding neural network untuk sistem rekomendasi.
 
 Berikut adalah daftar hyperparameter yang diuji dalam grid search:
 | Hyperparameter   | Nilai yang Diuji |
| ---------------- | ---------------- |
| `embedding_size` | 64, 128          |
| `learning_rate`  | 0.001, 0.0005    |
| `regularization` | 1e-2, 1e-3       |
| `batch_size`     | 64, 128          |
Sebanyak 16 kombinasi total diuji (4 parameter × 2 nilai masing-masing).
##### Prosedur Tuning
1. Model dibangun dengan kombinasi parameter tertentu menggunakan class RecommenderNet.
2. Model dikompilasi dengan:
- Loss function: MeanSquaredError
- Optimizer: Adam dengan learning_rate tertentu
- Metrics: RootMeanSquaredError (rmse) dan MeanAbsoluteError (mae)
3. Callbacks digunakan untuk meningkatkan efisiensi pelatihan:
- EarlyStopping: menghentikan pelatihan jika tidak ada perbaikan pada val_loss dalam 5 epoch.
- ReduceLROnPlateau: menurunkan learning rate secara otomatis jika val_loss stagnan.
4. Model dilatih selama maksimal 20 epoch (namun dihentikan lebih awal jika memenuhi kondisi early stop).
5. Nilai minimum dari val_mae, val_rmse, dan val_loss selama pelatihan disimpan untuk setiap kombinasi.

Hasil 5 Kombinasi Terbaik Berdasarkan val_mae
| No. | embedding_size | learning_rate | regularization | batch_size | val_loss | val_mae  | val_rmse |
|-----|----------------|---------------|----------------|------------|----------|----------|----------|
| 1   | 128            | 0.001         | 0.010          | 64         | 0.036462 | 0.146889 | 0.190952 |
| 2   | 64             | 0.001         | 0.010          | 64         | 0.036487 | 0.146912 | 0.191015 |
| 3   | 128            | 0.001         | 0.001          | 64         | 0.036517 | 0.147039 | 0.191094 |
| 4   | 64             | 0.001         | 0.001          | 64         | 0.036513 | 0.147070 | 0.191082 |
| 5   | 128            | 0.001         | 0.010          | 128        | 0.036829 | 0.148200 | 0.191908 |

Hasil 5 Kombinasi Terbaik Berdasarkan val_rmse
| No. | embedding_size | learning_rate | regularization | batch_size | val_loss | val_mae  | val_rmse |
|-----|----------------|---------------|----------------|------------|----------|----------|----------|
| 1   | 128            | 0.001         | 0.010          | 64         | 0.036462 | 0.146889 | 0.190952 |
| 2   | 64             | 0.001         | 0.010          | 64         | 0.036487 | 0.146912 | 0.191015 |
| 3   | 64             | 0.001         | 0.001          | 64         | 0.036513 | 0.147070 | 0.191082 |
| 4   | 128            | 0.001         | 0.001          | 64         | 0.036517 | 0.147039 | 0.191094 |
| 5   | 128            | 0.001         | 0.010          | 128        | 0.036829 | 0.148200 | 0.191908 |

Berikut adalah kesimpulan hasil tuning hyperparameter
| Hyperparameter   | Nilai Terbaik |
|------------------|---------------|
| embedding_size   | 128           |
| learning_rate    | 0.001         |
| regularization   | 0.01          |
| batch_size       | 64            |

Perbandingan Sebelum dan Sesudah Tuning
| Metrik | Sebelum Tuning | Setelah Tuning |
| ------ | -------------- | -------------- |
| RMSE   | 0.1987         | **0.1909**     |
| MAE    | 0.1542         | **0.1469**     |
Setelah dilakukan tuning hyperparameter, nilai MAE pada data validasi turun dari 0.1542 menjadi 0.1469, dan nilai RMSE turun dari 0.1987 menjadi 0.1909.

Maka, untuk Top-N recommendation akan digunakan model setelah tuning hyperparameter.
##### **Top-N Recommendation**
Berikut adalah daftar 10 rekomendasi film untuk user ID 20
| No. | movieId | Judul Film                                  | Prediksi Rating |
|-----|---------|----------------------------------------------|-----------------|
| 1   | 318     | The Million Dollar Hotel                     | 4.107           |
| 2   | 858     | Sleepless in Seattle                         | 3.921           |
| 3   | 58559   | Confession of a Child of the Century         | 3.909           |
| 4   | 296     | Terminator 3: Rise of the Machines           | 3.909           |
| 5   | 260     | The 39 Steps                                 | 3.907           |
| 6   | 2959    | License to Wed                               | 3.904           |
| 7   | 1213    | The Talented Mr. Ripley                      | 3.901           |
| 8   | 593     | Solaris                                      | 3.867           |
| 9   | 527     | Once Were Warriors                           | 3.866           |
| 10  | 750     | Murder She Said                              | 3.848           |
## Evaluation Collaborative Filtering
##### **Metrik Evaluasi yang Digunakan**
Pada model Collaborative Filtering berbasis neural network, digunakan dua metrik evaluasi utama:
1.  Mean Absolute Error (MAE)
- Mengukur rata-rata selisih absolut antara nilai rating prediksi dan rating aktual dan lebih stabil terhadap outlier.
- Formula:

        MAE = (1/n) × ∑ᵢ₌₁ⁿ |yᵢ − ŷᵢ
        
2.Root Mean Squared Error (RMSE)
- Mengukur akar dari rata-rata kuadrat selisih antara nilai aktual dan prediksi dan lebih sensitif terhadap kesalahan besar.
Formula:
        
        RMSE = √[(1/n) × ∑ᵢ₌₁ⁿ (yᵢ − ŷᵢ)²]
#### Hasil Evaluasi Model
| Metrik | Sebelum Tuning | Setelah Tuning |
| ------ | -------------- | -------------- |
| MAE    | 0.1542         | **0.1469**     |
| RMSE   | 0.1987         | **0.1909**     |

#### Keterkaitan dengan Business Understanding

**1. apakah model menjawab problem statement?**
Ya. Salah satu pernyataan masalah utama adalah bagaimana memberikan rekomendasi yang personal dan relevan bagi pengguna. Collaborative Filtering menyelesaikan ini dengan mempelajari pola interaksi antar pengguna, dan memberikan rekomendasi berdasarkan preferensi pengguna serupa.
**2. Apakah goals proyek tercapai?**
Ya. Tujuan proyek adalah memberikan Top-N rekomendasi film yang akurat berdasarkan perilaku pengguna. Hasil evaluasi metrik membuktikan bahwa model dapat memprediksi rating dengan presisi tinggi, sehingga mampu merekomendasikan film yang sangat relevan.
**3. APakah solusi yang dirancang berdampak?**
Sangat berdampak. Model ini mampu memberikan rekomendasi bahkan untuk film yang tidak memiliki banyak metadata, selama cukup interaksi pengguna tersedia.
Dalam konteks bisnis, model ini:
- Meningkatkan kepuasan pengguna dengan menyarankan film sesuai selera.
- Meningkatkan retensi pengguna karena pengalaman personalisasi yang lebih kuat.
- Membantu platform layanan film untuk menargetkan konten yang tepat secara otomatis.
## Kesimpulan akhir
Berdasarkan evaluasi kedua model, strategi implementasi yang disarankan adalah menggunakan Content-Based Filtering (CBF) untuk pengguna baru karena cepat dan tetap relevan tanpa perlu data interaksi, serta menggunakan Collaborative Filtering (CF) untuk pengguna aktif dengan riwayat rating yang cukup agar rekomendasi lebih personal. Kombinasi keduanya dalam pendekatan hybrid akan meningkatkan fleksibilitas dan akurasi sistem, sementara retraining model CF secara berkala dan memperkaya fitur CBF dapat menjaga performa dan relevansi rekomendasi seiring waktu.
- CBF unggul dalam efisiensi dan cold-start.
- CF unggul dalam personalisasi dan akurasi rekomendasi.
- Kombinasi keduanya akan memberikan sistem rekomendasi yang kuat, fleksibel, dan siap digunakan di dunia nyata.

![Image](https://github.com/user-attachments/assets/8a99ef59-a01b-46c3-a027-f9a90319749e)

![Image](https://github.com/user-attachments/assets/bed2a555-6d0a-4967-ae71-d00e52f8143f)

![Image](https://github.com/user-attachments/assets/453dd499-40c8-4929-b676-baa76416bca8)

![Image](https://github.com/user-attachments/assets/ff401109-875a-45dc-9329-d5f3473011fa)

![Image](https://github.com/user-attachments/assets/a1a03637-4b94-4013-b886-ead4c6330b87)

## Referensi
[1] Y. Zhang and X. Chen, "Explainable Recommendation: A Survey and New Perspectives," *Foundations and Trends® in Information Retrieval*, vol. 14, no. 1, pp. 1–101, 2020. [Online]. Available: https://doi.org/10.1561/1500000066

[2] C. C. Aggarwal, *Recommender Systems: The Textbook*, Springer, 2016. [Online]. Available: https://doi.org/10.1007/978-3-319-29659-3

[3] J. Chen, H. Dong, X. Wang, F. Feng, M. Wang, and X. He, "Bias and Debias in Recommender System: A Survey and Future Directions," *arXiv preprint*, arXiv:2010.03240, 2020. [Online]. Available: https://arxiv.org/abs/2010.03240

[4] K. R. Sari, W. Suharso, and Y. Azhar, "Pembuatan Sistem Rekomendasi Film dengan Menggunakan Metode Item-Based Collaborative Filtering pada Apache Mahout," *Repositor*, vol. 2, no. 6, pp. 767–774, 2020. [Online]. Available: https://ejournal.umm.ac.id/index.php/repositor/article/view/30715.
**---Ini adalah bagian akhir laporan---**

