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
| ratings.csv          | 26.024.289 baris | 4 kolom       | int64 & float64     | Berisi interaksi pengguna berupa rating terhadap film                    |


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





**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data beserta insight atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi yang Anda buat untuk menyelesaikan permasalahan. Sajikan top-N recommendation sebagai output.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menyajikan dua solusi rekomendasi dengan algoritma yang berbeda.
- Menjelaskan kelebihan dan kekurangan dari solusi/pendekatan yang dipilih.

## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**
[1] Y. Zhang and X. Chen, "Explainable Recommendation: A Survey and New Perspectives," *Foundations and Trends® in Information Retrieval*, vol. 14, no. 1, pp. 1–101, 2020. [Online]. Available: https://doi.org/10.1561/1500000066

[2] C. C. Aggarwal, *Recommender Systems: The Textbook*, Springer, 2016. [Online]. Available: https://doi.org/10.1007/978-3-319-29659-3

[3] J. Chen, H. Dong, X. Wang, F. Feng, M. Wang, and X. He, "Bias and Debias in Recommender System: A Survey and Future Directions," *arXiv preprint*, arXiv:2010.03240, 2020. [Online]. Available: https://arxiv.org/abs/2010.03240

[4] K. R. Sari, W. Suharso, and Y. Azhar, "Pembuatan Sistem Rekomendasi Film dengan Menggunakan Metode Item-Based Collaborative Filtering pada Apache Mahout," *Repositor*, vol. 2, no. 6, pp. 767–774, 2020. [Online]. Available: https://ejournal.umm.ac.id/index.php/repositor/article/view/30715

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
