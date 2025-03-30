# Cellphones Recommendations

## Project Overview

**Latar Belakang**

Seiring dengan perkembangan teknologi, jumlah pilihan ponsel di pasar semakin bertambah dengan berbagai spesifikasi, fitur, dan harga. Bagi konsumen, memilih ponsel yang sesuai dengan kebutuhan dan preferensi mereka dapat menjadi tantangan yang membingungkan. Sistem rekomendasi berbasis teknologi dapat membantu konsumen menemukan ponsel yang paling sesuai dengan preferensi mereka, baik berdasarkan spesifikasi teknis maupun pengalaman pengguna lain.

Dua pendekatan utama yang dapat digunakan untuk membangun sistem rekomendasi ini adalah Content-based Filtering dan Collaborative Filtering. Content-based Filtering merekomendasikan ponsel berdasarkan atribut atau fitur seperti harga, prosesor, ukuran layar, dan kapasitas baterai yang sesuai dengan kebutuhan pengguna. Sementara itu, Collaborative Filtering menggunakan data interaksi pengguna seperti rating, ulasan, atau preferensi pembelian untuk memberikan rekomendasi berdasarkan pola perilaku pengguna lain.

Sehingga, proyek ini bertujuan untuk membuat model rekomendasi ponsel dengan menggunakan data spesifikasi ponsel dan data interaksi pengguna. Model ini akan memperkirakan top 5 ponsel terbaik untuk setiap pengguna berdasarkan preferensi mereka. Ini diharapkan dapat berperan dalam meningkatkan pengalaman pengguna dan membantu konsumen membuat keputusan pembelian yang lebih baik.


**Mengapa dan Bagaimana Masalah Ini Harus Diselesaikan?**

Dengan semakin kompleksnya pilihan ponsel, banyak konsumen yang kesulitan menemukan produk yang benar-benar sesuai dengan kebutuhan mereka. Sistem rekomendasi berbasis Content-based Filtering dapat memberikan rekomendasi yang lebih personal berdasarkan preferensi fitur tertentu. Di sisi lain, Collaborative Filtering dapat membantu pengguna menemukan ponsel yang mungkin tidak mereka pertimbangkan sebelumnya, tetapi relevan berdasarkan pengalaman pengguna lain.

Proyek ini penting karena:
1. **Menghemat Waktu**: Sistem menyaring ribuan pilihan menjadi top 5 ponsel yang sesuai, mempermudah pengguna dalam membuat keputusan.  
2. **Rekomendasi Personal**: Memberikan rekomendasi yang relevan berdasarkan preferensi spesifikasi atau ulasan pengguna lain.  
3. **Meningkatkan Kepuasan**: Membantu pengguna menemukan ponsel terbaik sesuai kebutuhan, bahkan untuk pilihan yang tidak terpikirkan sebelumnya.


**Hasil Riset Terkait**

Beberapa penelitian mendukung pendekatan ini, di antaranya:

**1. Sistem Rekomendasi Menggunakan Metode Content-Based Filtering**
- **Judul**: "Penerapan Metode Content-Based Filtering pada Sistem Rekomendasi"
- **Abstrak**: Penelitian ini membahas penggunaan content-based filtering dalam sistem rekomendasi yang memberikan saran berdasarkan kesamaan atribut atau fitur item yang disukai oleh pengguna. Metode ini efektif dalam menghasilkan rekomendasi yang sederhana dan efisien, serta dapat meningkatkan kepuasan pengguna dan pendapatan bisnis.
- **Sumber**: [Online Journal Universitas Jambi](https://online-journal.unja.ac.id/msa/article/view/32136)

---

**2. Sistem Rekomendasi Menggunakan Metode Collaborative Filtering**
- **Judul**: "Penggunaan Algoritma Collaborative Filtering pada Sistem Rekomendasi Aplikasi E-Commerce berbasis Website pada Toko Pakaian Biostuff.Id"
- **Abstrak**: Penelitian ini menjelaskan implementasi algoritma collaborative filtering untuk memprediksi preferensi pengguna berdasarkan data penjualan yang tersedia. Hasil menunjukkan bahwa metode ini dapat memberikan rekomendasi berbasis pola pembelian pengguna lain dengan efektif.
- **Sumber**: [Jurnal Universitas Muria Kudus (UMK)](https://jurnal.umk.ac.id/index.php/simet/article/download/10719/pdf)


## Business Understanding

Pada bagian ini, akan menjelaskan proses klarifikasi masalah terkait sistem rekomendasi ponsel berbasis Content-based Filtering dan Collaborative Filtering.

### Problem Statements

Berikut adalah pernyataan masalah yang mendasari proyek ini:

- Pernyataan Masalah 1: Bagaimana memberikan rekomendasi ponsel yang relevan dan personal kepada pengguna berdasarkan spesifikasi teknis seperti harga, prosesor, dan kapasitas baterai?
- Pernyataan Masalah 2: Bagaimana memanfaatkan pola interaksi pengguna untuk memberikan rekomendasi yang akurat?

### Goals

Berikut adalah tujuan yang ingin dicapai berdasarkan pernyataan masalah di atas:

- Tujuan 1: Mengembangkan model rekomendasi berbasis **Content-based Filtering** yang mampu memberikan rekomendasi berdasarkan atribut atau spesifikasi ponsel.
- Tujuan 2: Membuat model berbasis **Collaborative Filtering** untuk memanfaatkan data interaksi pengguna dan memberikan rekomendasi berdasarkan pola perilaku pengguna serupa.


### Solution statements

Untuk mencapai tujuan yang diinginkan, berikut adalah beberapa solusi yang diajukan:


1. **Menggunakan Content-based Filtering**:
   - Membuat model yang merekomendasikan ponsel berdasarkan kesamaan atribut spesifikasi seperti harga, prosesor, kapasitas baterai, dan fitur tambahan lainnya.
   - Menggunakan algoritma berbasis **cosine similarity** atau **TF-IDF** untuk menghitung kesamaan antarproduk.

2. **Menggunakan Collaborative Filtering**:
   - Membuat model berbasis interaksi pengguna seperti rating dan ulasan untuk menemukan pola rekomendasi.
   - Menerapkan pendekatan **Matrix Factorization** (contoh: SVD) atau model deep learning berbasis embedding.



Solusi ini diharapkan dapat memberikan hasil yang terukur dan sesuai dengan tujuan proyek.

## Data Understanding

Dataset yang digunakan dalam proyek ini diambil dari [Kaggle](https://www.kaggle.com/datasets/meirnizri/cellphones-recommendations/data), yang berisi informasi tentang ponsel, data rating pengguna, dan detail pengguna terkait. Dataset ini dirancang untuk mendukung pengembangan sistem rekomendasi ponsel menggunakan **Content-based Filtering** dan **Collaborative Filtering**.

### Informasi Dataset

Dataset terdiri dari tiga file utama:

1. **`cellphones_data.csv`**:
   - Berisi metadata ponsel yang dapat digunakan untuk **Content-based Filtering**.
   - **Dimensi**: 33 baris × 14 kolom.
   - **Kolom Utama**:
     - `cellphone_id`: ID unik untuk setiap ponsel.
     - `brand`: Merek ponsel (contoh: Samsung, Apple, Xiaomi).
     - `model`: Model ponsel (contoh: Galaxy S22, iPhone 14).
     - `operating system`: Sistem operasi ponsel.
     - `internal memory`: Kapasitas penyimpanan internal (GB).
     - `RAM`: Kapasitas RAM (GB).
     - `performance`: Skor kinerja ponsel.
     - `main camera`: Resolusi kamera utama (MP).
     - `selfie camera`: Resolusi kamera selfie (MP).
     - `battery size`: Kapasitas baterai (mAh).
     - `screen size`: Ukuran layar (inch).
     - `weight`: Berat ponsel (gram).
     - `price`: Harga ponsel.
     - `release date`: Tanggal rilis ponsel.

2. **`cellphones_ratings.csv`**:
   - Berisi data rating yang diberikan pengguna untuk ponsel tertentu, yang dapat digunakan untuk **Collaborative Filtering**.
   - **Dimensi**: 990 baris × 3 kolom.
   - **Kolom Utama**:
     - `user_id`: ID unik untuk setiap pengguna.
     - `cellphone_id`: ID unik untuk setiap ponsel.
     - `rating`: Rating yang diberikan pengguna (skala 1-5).

3. **`cellphones_users.csv`**:
   - Berisi informasi demografi pengguna yang dapat digunakan untuk analisis tambahan.
   - **Dimensi**: 99 baris × 4 kolom.
   - **Kolom Utama**:
     - `user_id`: ID unik pengguna.
     - `age`: Usia pengguna.
     - `gender`: Jenis kelamin pengguna.
     - `occupation`: Pekerjaan pengguna.


### Kondisi Data

1. **Jumlah Baris dan Kolom**:
   - `cellphones_data`: 33 baris dan 14 kolom.
   - `cellphones_ratings`: 990 baris dan 3 kolom.
   - `cellphones_users`: 99 baris dan 4 kolom.

2. **Kondisi Data**:
   - **Missing Values**:
     - Tidak ada missing values di `cellphones_data` dan `cellphones_ratings`.
     - Terdapat 1 nilai kosong di kolom `occupation` pada `cellphones_users`.
   - **Tipe Data**:
     - `cellphones_data` memiliki kombinasi tipe data: integer, float, dan object.
     - `cellphones_ratings` seluruhnya bertipe integer.
     - `cellphones_users` memiliki kombinasi integer dan object.

---

### Exploratory Data Analysis (EDA)

Pada tahap ini, akan dilakuakn analisis pada dataset pertama yaitu `Dataset: cellphones_data`

**1. Distribusi Brand**

Pertama, dilakukan analisis jumlah brand, jumlah ponsel per brand, dan visualisasi distribusinya untuk memahami persebaran data ponsel berdasarkan brand.

<img src="https://github.com/user-attachments/assets/5c381735-b6b7-4e31-b14a-e6ca85f70d6e" alt="brand_distribution" style="width:70%">


**Result:**
Samsung adalah brand dengan jumlah ponsel terbanyak (8 ponsel), diikuti oleh Apple (6 ponsel), sedangkan Asus, Oppo, Vivo, dan Sony masing-masing hanya memiliki 1 ponsel. Total ada 10 brand.

**2. Distribusi Tipe Setiap Brand**

Selanjutnya, dilakukan identifikasi jumlah model ponsel unik dan menampilkan daftar lengkap model tersebut untuk memahami keragaman data. 

Jumlah Model Cellphone: 33

Daftar Model Berdasarkan Brand

| **Brand**   | **Model**                                                                                           |
|-------------|-----------------------------------------------------------------------------------------------------|
| **Apple**   | iPhone SE (2022), iPhone 13 Mini, iPhone 13, iPhone 13 Pro, iPhone 13 Pro Max, iPhone XR             |
| **Asus**    | Zenfone 8                                                                                           |
| **Google**  | Pixel 6, Pixel 6a, Pixel 6 Pro                                                                      |
| **Motorola**| Moto G Stylus (2022), Moto G Play (2021), Moto G Pure, Moto G Power (2022)                          |
| **OnePlus** | Nord N20, Nord 2T, 10 Pro, 10T                                                                      |
| **Oppo**    | Find X5 Pro                                                                                         |
| **Samsung** | Galaxy A13, Galaxy A32, Galaxy A53, Galaxy S22, Galaxy S22 Plus, Galaxy S22 Ultra, Galaxy Z Flip 3, Galaxy Z Fold 3 |
| **Sony**    | Xperia Pro                                                                                          |
| **Vivo**    | X80 Pro                                                                                             |
| **Xiaomi**  | Redmi Note 11, 11T Pro, 12 Pro, Poco F4                                                             |

**3. Distribusi Sistem Operasi**

Tahap ini melakukan analisis distribusi sistem operasi untuk mengetahui jumlah perangkat berdasarkan sistem operasi yang digunakan.

<img src="https://github.com/user-attachments/assets/0fa33989-8295-435a-b0b4-6e2fb7c5a7e4" alt="operating_system_distribution" style="width:60%">

**Result:**
Sebagian besar ponsel menggunakan sistem operasi Android (27 perangkat), sementara sisanya menggunakan iOS (6 perangkat).

**4. Distribusi Memory dan RAM**

Pada tahap ini, dilakukan analisis distribusi kapasitas memori internal dan RAM untuk memahami karakteristik perangkat dalam dataset.

<img src="https://github.com/user-attachments/assets/13196b21-acb7-4b1b-b2ce-8184fc89a4a8" alt="memory_and_ram_distribution" style="width:90%">

**Result:**
Sebagian besar perangkat memiliki memori internal 128 GB (20 perangkat) dan RAM 8 GB (13 perangkat).

**5. Distribusi Performance**

Pada tahap ini, dilakukan analisis distribusi nilai performance, termasuk melihat rentang nilai performance dan mengelompokkan data menjadi dua kategori berdasarkan nilai 5.

<img src="https://github.com/user-attachments/assets/9dbaf437-5a6a-4e57-ad37-28ce2ad5dd7f" alt="performance_distribution" style="width:70%">

**Result:** Rentang nilai performance adalah 1.02 hingga 11.0, dengan 23 data memiliki nilai performance > 5 dan 10 data memiliki nilai performance ≤ 5.

**6. Distribusi Price**

Pada tahap ini, dilakukan analisis distribusi harga ponsel dengan melihat rentang nilai harga secara keseluruhan dan mengelompokkan data ke dalam lima kategori harga.

<img src="https://github.com/user-attachments/assets/2f37f987-0646-4237-a70e-57bf23f0bbd9" alt="price_distribution" style="width:70%">

**Result:** Rentang harga ponsel adalah 129 hingga 1998 USD, dengan jumlah ponsel terbanyak dalam kategori 300-600 USD (10 ponsel) dan jumlah paling sedikit dalam kategori >1200 USD (2 ponsel).


**7. Distribusi Rating**

Pada tahap ini, dilakukan analisis terhadap jumlah review yang diberikan oleh user, distribusi jumlah review per tipe ponsel, dan distribusi nilai rating.

![cellphone_review_distribution_named](https://github.com/user-attachments/assets/28625077-3f22-4f38-b6b7-cb393ca8e724)

<img src="https://github.com/user-attachments/assets/03ad7890-9bc7-4d1c-8187-2d7e11cbd648" alt="rating_distribution" style="width:50%">

**Result:**  

1. **User Review Analysis:**  
   Setiap user memberikan jumlah review yang sama, yaitu 10 review.

2. **Cellphone Review Analysis:**  
   - Ponsel yang paling banyak direview adalah **Moto G Play (2021)** dengan 41 review.  
   - Ponsel yang paling sedikit direview adalah **iPhone SE (2022)** dan **10T**, masing-masing dengan 20 review.  

3. **Rating Distribution Analysis:**  
   - Nilai rating memiliki rentang dari 1 hingga 18.  
   - Rating terbanyak adalah **8** dengan 195 kemunculan, sedangkan rating paling sedikit adalah **3** dengan 30 kemunculan.  
   - Terdapat outlier pada nilai rating, yaitu **18**.  


**8. Distribusi Users**

Pada athap ini, dilakukan analisis data pengguna berdasarkan usia, gender, dan pekerjaan untuk memahami karakteristik demografis pengguna.

![user_age_distribution](https://github.com/user-attachments/assets/09cb5bf0-a769-4028-97e2-474e890bc580)

<img src="https://github.com/user-attachments/assets/2f36a92d-6589-4efa-9bb9-8d9d8ea7e1a0" alt="user_gender_distributionn" style="width:50%">

### User Occupation Analysis

Jumlah occupation: **45**

| **Occupation**                       | **Count** |
|--------------------------------------|-----------|
| accountant                           | 2         |
| administrative officer               | 5         |
| administrator                        | 1         |
| banking                              | 1         |
| business                             | 1         |
| computer technician                  | 1         |
| construction                         | 2         |
| data analyst                         | 2         |
| education                            | 2         |
| executive                            | 1         |
| executive manager                    | 1         |
| finance                              | 2         |
| healthare                            | 1         |
| healthcare                           | 2         |
| homemaker                            | 1         |
| ict officer                          | 1         |
| information                          | 1         |
| information technology               | 12        |
| it                                   | 6         |
| manager                              | 18        |
| marketing                            | 1         |
| master degree                        | 1         |
| nurse                                | 1         |
| ops manager                          | 1         |
| president transportation company     | 1         |
| purchase manager                     | 1         |
| qa software manager                  | 1         |
| registered                           | 1         |
| retail                               | 1         |
| sales                                | 3         |
| sales manager                        | 2         |
| security                             | 3         |
| self employed                        | 1         |
| software developer                   | 4         |
| system administrator                 | 1         |
| teacher                              | 1         |
| team leader                          | 2         |
| team worker in it                    | 1         |
| technical engineer                   | 1         |
| technician                           | 1         |
| transportation                       | 1         |
| warehousing                          | 1         |
| web design                           | 1         |
| worker                               | 2         |
| writer                               | 1         |

---

**Result:**  

1. **User Age Analysis:**  
   - Rentang usia pengguna adalah 21 hingga 61 tahun.  
   - Usia yang paling banyak muncul adalah 25 tahun dengan jumlah 12 pengguna.  

2. **User Gender Analysis:**  
   - Terdapat 50 pengguna berjenis kelamin male dan 46 pengguna female.  
   - Ditemukan outliers pada gender dengan label `-Select Gender-` (3 pengguna).  

3. **User Occupation Analysis:**  
   - Terdapat 45 jenis pekerjaan unik di dataset.  
   - Kesalahan penulisan ditemukan pada pekerjaan `healthare`, yang seharusnya `healthcare`.  
   - Pekerjaan `information technology` (12 pengguna) dan `it` (6 pengguna) dapat digabung menjadi satu kategori karena memiliki arti yang sama.  


## **Data Preparation**

Pada bagian ini, dilakukan beberapa langkah untuk mempersiapkan data agar siap digunakan dalam analisis dan pemodelan. Setiap langkah bertujuan untuk memastikan kualitas data serta kelengkapan informasi yang diperlukan. Berikut adalah teknik yang digunakan:

### **Teknik Data Preparation**

1. **Penggabungan Dataset**: Menggabungkan berbagai dataset yang relevan untuk mendapatkan informasi yang komprehensif.
2. **Pembersihan Data**: Melakukan pengecekan dan penghapusan data yang tidak valid, termasuk missing value, outlier, dan data duplikat.
3. **Normalisasi dan Encoding**: Menormalisasi data rating dan melakukan encoding pada kolom `user_id` dan `cellphone_id` agar kompatibel dengan model machine learning.
4. **Persiapan untuk Pemodelan**: Menyiapkan dataset dalam bentuk yang optimal untuk pelatihan model, seperti pasangan key-value untuk user dan ponsel.


### **Proses Data Preparation**

**1. Merged all datasets**

Pada tahap ini, dataset `cellphones_data`, `cellphones_ratings`, dan `cellphones_users` digabungkan menjadi satu dataset komprehensif untuk analisis lanjutan. Dataset hasil gabungan mencakup metadata ponsel, rating dari pengguna, dan informasi demografi pengguna, yang akan memudahkan proses eksplorasi dan analisis lebih lanjut.

**2. Check and drop missing value**

Cek apakah ada missing value pada merged dataframe. Ditemukan 10 missing data pada 'occupation' dan di drop.

**3. Drop invalid gender data**

Pada analisis sebelumnya, kita menemukan data gender dengan isi "-Select Gender-", akan dicek untuk memastikan bahwa data tersebut tidak ada lagi.

**4. Drop outlier pada rating dan occupation**

Pada analisis sebelumnya juga, kita menemukan data outlier pada rating yaitu 18, terdapat kesalahan tulis pada kolom occupation yaitu pada healthcare, dan terdapat perbedaan kategori pada nama pekerjaan yang sama pada kolom occupation.

**5. Check and drop duplicate data**

Pada tahap ini, cek dan penghapusan data duplikat dilakukan untuk memastikan dataset bersih dari entri yang berulang, sehingga analisis lebih akurat dan efisien.

**6. Prepare the dataset for modelling**

Dataset telah dipersiapkan dengan menghapus duplikat berdasarkan kolom `cellphone_id`, memastikan setiap ponsel hanya muncul satu kali. Data kemudian dikonversi menjadi list untuk mempermudah manipulasi, dan akhirnya disusun menjadi DataFrame baru yang menyerupai pasangan key-value untuk analisis lanjutan.

Pada **Content Based Filtering**

1. **Membangun Representasi Metadata**
   Metadata seperti `brand` digunakan untuk membangun representasi numerik menggunakan **TF-IDF (Term Frequency-Inverse Document Frequency)**. Teknik ini mengonversi teks menjadi vektor yang dapat dihitung dalam ruang multidimensi.

   **Potongan Kode (Code 1):**
   ```python
   def build_recommendation_system(dataframe):
       data = dataframe
       tf = TfidfVectorizer()
       tf.fit(data['brand'])
       feature_names = tf.get_feature_names_out()
       return data, tf, feature_names
   ```

2. **Membangun Matriks TF-IDF**
   TF-IDF digunakan untuk menghitung tingkat relevansi setiap fitur dalam dataset. Kolom `brand` diubah menjadi matriks TF-IDF, di mana setiap elemen menunjukkan bobot relevansi dari setiap brand.

   **Potongan Kode (Code 2):**
   ```python
   def generate_tfidf_matrix(data, column):
       tf = TfidfVectorizer()
       tfidf_matrix = tf.fit_transform(data[column])
       dense_matrix = tfidf_matrix.todense()
       return tfidf_matrix, dense_matrix
   ```

3. **Visualisasi Matriks TF-IDF**
   Untuk memahami hasil transformasi TF-IDF, matriks diekstraksi sebagian (10 baris x 10 kolom). Setiap baris mewakili model, dan setiap kolom mewakili fitur (brand).

   **Potongan Kode (Code 3):**
   ```python
   def display_tfidf_matrix_sample(tfidf_matrix, feature_names, index_labels, row_sample=10, col_sample=10):
       tfidf_df = pd.DataFrame(tfidf_matrix.todense(), columns=feature_names, index=index_labels)
       sampled_df = tfidf_df.sample(row_sample, axis=0).sample(col_sample, axis=1)
       return sampled_df
   ```

Pada **Collaborative Filtering**

1. **Encoding User dan Item**
   - User ID (`user_id`) dan Item ID (`cellphone_id`) di-encode menjadi nilai integer unik untuk memudahkan pemrosesan dalam model machine learning.
   - Encoding ini dilakukan menggunakan fungsi `encode_features`.

   **Potongan Kode (Code 1):**
   ```python
   def encode_features(df, user_col='user_id', item_col='cellphone_id'):
       # Encode user dan item
       user_ids = df[user_col].unique().tolist()
       item_ids = df[item_col].unique().tolist()
       user_to_user_encoded = {x: i for i, x in enumerate(user_ids)}
       item_to_item_encoded = {x: i for i, x in enumerate(item_ids)}
       df_encoded = df.copy()
       df_encoded[user_col] = df_encoded[user_col].map(user_to_user_encoded)
       df_encoded[item_col] = df_encoded[item_col].map(item_to_item_encoded)
       return df_encoded, user_to_user_encoded, item_to_item_encoded
   ```

2. **Mempersiapkan Data untuk Pelatihan**
   - Dataset diacak dan dibagi menjadi data training (80%) dan validasi (20%).
   - Rating dinormalisasi ke dalam skala antara 0 dan 1 untuk membantu model memahami distribusi nilai rating.

   **Potongan Kode (Code 2):**
   ```python
   def prepare_train_validation_data(df, user_col='user_id', cellphone_col='cellphone_id', rating_col='rating'):
       df = df.sample(frac=1, random_state=42).reset_index(drop=True)
       x = df[[user_col, cellphone_col]].values
       y = df[rating_col].apply(lambda x: (x - df[rating_col].min()) / (df[rating_col].max() - df[rating_col].min())).values
       train_indices = int(0.8 * df.shape[0])
       return x[:train_indices], x[train_indices:], y[:train_indices], y[train_indices:]
   ```


### **Alasan Tahapan Data Preparation Dilakukan**

**1. Merged all datasets**
- **Alasan**: Penggabungan dataset diperlukan untuk menciptakan satu dataset komprehensif yang mencakup metadata ponsel, interaksi pengguna (rating), dan informasi demografi pengguna. Ini penting untuk memungkinkan analisis yang lebih mendalam dan menghubungkan berbagai fitur yang mendukung pemodelan.

**2. Check and drop missing value**
- **Alasan**: Data yang memiliki missing value dapat mengganggu hasil analisis dan model prediksi. Dengan menghapus nilai yang hilang pada kolom `occupation`, dataset menjadi lebih bersih dan siap digunakan tanpa informasi yang hilang.

**3. Drop invalid gender data**
- **Alasan**: Data tidak valid seperti "-Select Gender-" dapat menyebabkan bias dan hasil analisis yang tidak akurat. Dengan menghapus nilai yang tidak relevan, dataset menjadi lebih konsisten dan merepresentasikan informasi yang sebenarnya.

**4. Drop outlier pada rating dan occupation**
- **Alasan**: Outlier dapat merusak hasil analisis dan pemodelan, terutama dalam dataset yang berbasis rating. Rating dengan nilai 18 berada di luar rentang yang valid (1-10), sehingga harus dihapus. Selain itu, kesalahan penulisan pada kolom `occupation` harus diperbaiki untuk memastikan konsistensi dan akurasi kategori.

**5. Check and drop duplicate data**
- **Alasan**: Data duplikat dapat menyebabkan bias dalam analisis dan pelatihan model, seperti memberikan bobot lebih pada informasi yang sama. Dengan menghapus duplikat, dataset menjadi lebih akurat dan representatif.

**6. Prepare the dataset for modelling**
- **Alasan**: Tahap ini bertujuan untuk memastikan dataset dalam format yang optimal untuk pemodelan. Dengan menghapus duplikat berdasarkan `cellphone_id`, memastikan setiap ponsel hanya muncul satu kali, dan mempersiapkan data dalam format pasangan key-value, proses analisis dan pelatihan model dapat dilakukan secara efisien.


## Modeling

Pada bagian ini, sistem rekomendasi dirancang dan diimplementasikan menggunakan dua pendekatan utama: Content-Based Filtering dan Collaborative Filtering. Tujuan dari model adalah untuk memberikan rekomendasi top-N kepada pengguna berdasarkan preferensi mereka terhadap ponsel yang ada dalam dataset. Berikut adalah penjelasan lebih lanjut mengenai parameter yang digunakan, kelebihan, dan kekurangan dari masing-masing pendekatan, serta beberapa potongan kode yang relevan.

### **Content Based Filtering**

Content-Based Filtering adalah pendekatan sistem rekomendasi yang memanfaatkan metadata atau informasi deskriptif dari item yang akan direkomendasikan. Dalam proyek ini, pendekatan ini digunakan untuk merekomendasikan ponsel berdasarkan atribut seperti `brand`, `model`, dan `operating_system`.

**Cara Kerja Content-Based Filtering**

1. **Menghitung Kesamaan Antar Model**
   Derajat kesamaan antar model dihitung menggunakan **Cosine Similarity**, yang mengukur kesamaan sudut antar vektor TF-IDF. Hasilnya adalah matriks kesamaan ukuran `(33 x 33)`.

   **Potongan Kode (Code 4):**
   ```python
   def calculate_cosine_similarity(tfidf_matrix, index_labels, row_sample=10, col_sample=33):
       cosine_sim = cosine_similarity(tfidf_matrix)
       cosine_sim_df = pd.DataFrame(cosine_sim, index=index_labels, columns=index_labels)
       return cosine_sim, cosine_sim_df
   ```

2. **Membangun Sistem Rekomendasi**
   Dengan memanfaatkan matriks kesamaan, model dapat merekomendasikan ponsel yang paling mirip berdasarkan atribut metadata. Fungsi `model_recommendations` menghasilkan daftar rekomendasi dengan menampilkan ponsel yang memiliki nilai kesamaan tertinggi.

   **Potongan Kode (Code 5):**
   ```python
   def model_recommendations(model, similarity_data, items, k=5):
       similarity_scores = similarity_data.loc[:, model].to_numpy()
       top_indices = similarity_scores.argsort()[-(k+2):-1][::-1]
       closest_models = similarity_data.columns[top_indices]
       closest_models = [m for m in closest_models if m != model]
       recommendations = pd.DataFrame(closest_models, columns=['model']).merge(items, on='model', how='left')
       return recommendations.head(k)
   ```

3. **Hasil Rekomendasi**
   Model menghasilkan rekomendasi untuk pengguna berdasarkan ponsel yang mereka pilih. Misalnya:
   - Untuk `Galaxy S22`, rekomendasi adalah ponsel dari brand yang sama atau brand lain dengan fitur serupa.
   - Untuk `Zenfone 8`, rekomendasi berfokus pada ponsel dengan spesifikasi dan brand serupa.

   **Potongan Kode (Code 6 dan Code 7):**
   ```python
   recommendations = model_recommendations(
       model='Galaxy S22',
       similarity_data=cosine_sim_df,
       items=phone_new[['model', 'brand', 'operating_system']],
       k=5
   )
   print(recommendations)

   recommendations = model_recommendations(
       model='Zenfone 8',
       similarity_data=cosine_sim_df,
       items=phone_new[['model', 'brand', 'operating_system']],
       k=5
   )
   print(recommendations)
   ```

**Parameter yang Digunakan**

1. **TF-IDF Vectorizer:**
   - Parameter default digunakan.
   - Menyandikan teks `brand` menjadi vektor berbobot.

2. **Cosine Similarity:**
   - Menghitung kesamaan antar model.
   - Matriks simetris menunjukkan nilai kesamaan di antara setiap pasangan model.

3. **Top-K Recommendations:**
   - `k=5` digunakan untuk menampilkan 5 rekomendasi teratas.

**Kelebihan Pendekatan**

1. Tidak memerlukan data interaksi pengguna (rating).
2. Mampu memberikan rekomendasi yang relevan berdasarkan metadata item.
3. Efisien untuk dataset kecil atau sedang dengan atribut terbatas.

**Kekurangan Pendekatan**

1. Bergantung sepenuhnya pada metadata (`brand`, `model`, dll.), sehingga rekomendasi bisa bias terhadap atribut tertentu.
2. Tidak dapat menangani hubungan antar pengguna dan ponsel (misalnya, preferensi pengguna tidak diperhitungkan).
3. Kurang efektif jika metadata tidak relevan atau kurang representatif.

**Kesimpulan:**
Pendekatan Content-Based Filtering ini sangat cocok untuk dataset dengan metadata yang kuat. Namun, untuk memberikan rekomendasi yang lebih personal, pendekatan berbasis Collaborative Filtering dapat digunakan sebagai pelengkap.


**Collaborative Filtering**

Collaborative Filtering adalah pendekatan sistem rekomendasi yang memanfaatkan pola interaksi antara pengguna dan item (cellphone) untuk memberikan rekomendasi. Dalam proyek ini, pendekatan ini digunakan untuk mempelajari preferensi pengguna berdasarkan data rating.

**Cara Kerja Collaborative Filtering**

1. **Membangun Model Collaborative Filtering**
   - Model dibuat menggunakan arsitektur **Neural Collaborative Filtering** (NCF), di mana embedding digunakan untuk merepresentasikan pengguna dan item.
   - Fungsi dot product menghitung interaksi antara user embedding dan item embedding untuk memprediksi rating.

   **Potongan Kode (Code 3):**
   ```python
   class RecommenderNet(tf.keras.Model):
       def __init__(self, num_users, num_items, embedding_size):
           super(RecommenderNet, self).__init__()
           self.user_embedding = layers.Embedding(num_users, embedding_size)
           self.item_embedding = layers.Embedding(num_items, embedding_size)
           self.user_bias = layers.Embedding(num_users, 1)
           self.item_bias = layers.Embedding(num_items, 1)

       def call(self, inputs):
           user_vector = self.user_embedding(inputs[:, 0])
           item_vector = self.item_embedding(inputs[:, 1])
           dot_user_item = tf.tensordot(user_vector, item_vector, axes=2)
           return tf.nn.sigmoid(dot_user_item + self.user_bias(inputs[:, 0]) + self.item_bias(inputs[:, 1]))
   ```

2. **Melatih Model**
   - Model dilatih dengan **Binary Crossentropy Loss** untuk mempelajari distribusi rating.
   - Metrik evaluasi yang digunakan adalah **Root Mean Squared Error (RMSE)**.

   **Potongan Kode (Code 4):**
   ```python
   model.compile(
       loss=tf.keras.losses.BinaryCrossentropy(),
       optimizer=tf.keras.optimizers.Adam(learning_rate=0.001),
       metrics=[tf.keras.metrics.RootMeanSquaredError()]
   )
   history = model.fit(x_train, y_train, batch_size=8, epochs=100, validation_data=(x_val, y_val))
   ```

3. **Visualisasi Proses Training**
   - Grafik `RMSE` digunakan untuk memantau kinerja model selama proses pelatihan.

   **Potongan Kode (Code 5):**
   ```python
   plt.plot(history.history['root_mean_squared_error'])
   plt.plot(history.history['val_root_mean_squared_error'])
   plt.title('Model Metrics')
   plt.ylabel('RMSE')
   plt.xlabel('Epoch')
   plt.legend(['Train', 'Validation'], loc='upper left')
   plt.show()
   ```

4. **Menyiapkan Data Rekomendasi**
   - Cellphone yang belum direview oleh pengguna tertentu diidentifikasi, dan pasangan (user, cellphone) dibuat untuk prediksi.

   **Potongan Kode (Code 6):**
   ```python
   def prepare_recommendation_data(df, phone_df, user_id, user_to_user_encoded, cellphone_to_cellphone_encoded):
       cellphone_reviewed_by_user = df[df['user_id'] == user_id]
       cellphone_not_reviewed = phone_df[~phone_df['cellphone_id'].isin(cellphone_reviewed_by_user['cellphone_id'].values)]['cellphone_id']
       cellphone_not_reviewed = [[cellphone_to_cellphone_encoded.get(x)] for x in cellphone_not_reviewed]
       user_encoder = user_to_user_encoded.get(user_id)
       user_cellphone_array = np.hstack(([[user_encoder]] * len(cellphone_not_reviewed), cellphone_not_reviewed))
       return user_cellphone_array, cellphone_not_reviewed
   ```

5. **Menghasilkan Rekomendasi**
   - Model menghasilkan rekomendasi berdasarkan skor tertinggi dari prediksi rating untuk cellphones yang belum direview oleh pengguna.

   **Potongan Kode (Code 7):**
   ```python
   def get_user_recommendations(df, phone_df, model, user_to_user_encoded, cellphone_to_cellphone_encoded, cellphone_encoded_to_cellphone, top_n=10):
       user_id = df['user_id'].sample(1).iloc[0]
       cellphone_reviewed_by_user = df[df['user_id'] == user_id]
       cellphone_not_reviewed = phone_df[~phone_df['cellphone_id'].isin(cellphone_reviewed_by_user['cellphone_id'].values)]['cellphone_id']
       cellphone_not_reviewed = [[cellphone_to_cellphone_encoded.get(x)] for x in cellphone_not_reviewed]
       user_encoder = user_to_user_encoded.get(user_id)
       user_cellphone_array = np.hstack(([[user_encoder]] * len(cellphone_not_reviewed), cellphone_not_reviewed))
       ratings = model.predict(user_cellphone_array).flatten()
       top_ratings_indices = ratings.argsort()[-top_n:][::-1]
       recommended_cellphone_ids = [cellphone_encoded_to_cellphone.get(cellphone_not_reviewed[x][0]) for x in top_ratings_indices]
       return recommended_cellphone_ids
   ```

**Parameter yang Digunakan**

1. **Embedding Size:** `50` (ukuran representasi vektor embedding).
2. **Batch Size:** `8` (jumlah sampel per batch saat training).
3. **Learning Rate:** `0.001` (kecepatan pembaruan bobot).
4. **Epochs:** `100` (jumlah iterasi penuh melalui dataset).

**Kelebihan Pendekatan**

1. Tidak bergantung pada metadata; mempelajari preferensi pengguna langsung dari data interaksi.
2. Dapat menangkap hubungan kompleks antara pengguna dan item menggunakan embedding.

**Kekurangan Pendekatan**

1. Membutuhkan data interaksi yang cukup besar untuk menghasilkan rekomendasi yang andal.
2. Sulit memberikan rekomendasi untuk item atau pengguna baru (cold start problem).

**Menyajikan top-N Recommendation sebagai Output**

Pada bagian ini, hasil rekomendasi dari pendekatan Content-Based Filtering dan Collaborative Filtering disajikan dalam bentuk daftar top-N item yang paling relevan untuk pengguna atau model tertentu. Kedua pendekatan memiliki cara kerja berbeda dalam menghasilkan rekomendasi, yang akan dijelaskan di bawah ini dengan contoh hasilnya.

#### **Pendekatan 1: Content-Based Filtering**

**Contoh Kode dan Hasil**
```python
recommendations = model_recommendations(
    model='Galaxy S22', 
    similarity_data=cosine_sim_df, 
    items=phone_new[['model', 'brand', 'operating_system']], 
    k=5
)

print(recommendations)
```

**Output**
```plaintext
              model    brand operating_system
0       Galaxy A53  Samsung          Android
1  Galaxy Z Flip 3  Samsung          Android
2       Galaxy A13  Samsung          Android
3       Galaxy A32  Samsung          Android
4  Galaxy S22 Plus  Samsung          Android
```

**Penjelasan**
- **Cara Kerja:**
  - Content-Based Filtering menghasilkan rekomendasi berdasarkan kesamaan fitur, dalam hal ini fitur-fitur seperti brand dan operating system.
  - Menggunakan **TF-IDF Vectorizer** untuk merepresentasikan fitur sebagai vektor, dan kesamaan antar model dihitung menggunakan **Cosine Similarity**.
- **Hasil:**
  - Untuk model `Galaxy S22`, sistem merekomendasikan 5 model yang memiliki kesamaan tertinggi, yaitu model dari brand Samsung yang menggunakan sistem operasi Android.

#### **Pendekatan 2: Collaborative Filtering**

**Contoh Kode dan Hasil**
```python
get_user_recommendations(
    df=df,
    phone_df=phone_df,
    model=model,
    user_to_user_encoded=user_to_user_encoded,
    cellphone_to_cellphone_encoded=cellphone_to_cellphone_encoded,
    cellphone_encoded_to_cellphone=cellphone_encoded_to_cellphone,
    top_n=5
)
```

**Output**
```plaintext
=== High Ratings by User ===
Samsung: Galaxy A32
Google: Pixel 6a
Apple: iPhone 13 Mini
OnePlus: Nord N20
Motorola: Moto G Pure

=== Top Cellphone Recommendations ===
Samsung: Galaxy S22
Samsung: Galaxy A53
Google: Pixel 6 Pro
Xiaomi: 11T Pro
Samsung: Galaxy Z Fold 3
```

**Penjelasan**
- **Cara Kerja:**
  - Collaborative Filtering memberikan rekomendasi berdasarkan pola interaksi antara pengguna lain dengan item tertentu (e.g., rating).
  - Sistem memprediksi rating pengguna untuk item yang belum direview menggunakan model **Neural Collaborative Filtering (NCF)**.
  - Item dengan prediksi rating tertinggi dipilih sebagai rekomendasi.
- **Hasil:**
  - Untuk pengguna tertentu, sistem menghasilkan rekomendasi berdasarkan preferensi historis pengguna serupa.
  - Contoh di atas menunjukkan bahwa sistem merekomendasikan `Galaxy S22`, `Galaxy A53`, dan model relevan lainnya.


**Kesimpulan:**
Pendekatan Collaborative Filtering memungkinkan rekomendasi yang lebih personal dibandingkan Content-Based Filtering, tetapi memerlukan data interaksi yang lebih besar. Kombinasi keduanya dapat menghasilkan rekomendasi yang lebih komprehensif.


## Evaluation

Pada bagian ini, dilakukan evaluasi terhadap model yang telah dilatih, menggunakan data pengujian. Evaluasi dilakukan berdasarkan satu metrik utama: **RMSE (Root Mean Squared Error)**. Berikut adalah penjelasan dan hasil dari evaluasi:

### **Metrik Evaluasi yang Digunakan**

1. **Root Mean Squared Error (RMSE)**:

   - Mengukur akar rata-rata kuadrat dari selisih antara nilai aktual dan prediksi. Semakin kecil nilai RMSE, semakin baik prediksi model.
   - **Formula**:
     ![RMSE](https://github.com/user-attachments/assets/e4b3719d-7193-4344-adc6-6d578f967d6b)

   - **Interpretasi**:
     RMSE sangat sensitif terhadap kesalahan besar, sehingga memberikan gambaran seberapa jauh prediksi dari nilai aktual.


### **Hasil Evaluasi**

Dari evaluasi terhadap kedua model, berikut adalah hasil metrik evaluasi:

**Content-Based Filtering**
- **Metode Evaluasi**: Tidak menggunakan metrik numerik, karena evaluasi lebih difokuskan pada relevansi rekomendasi berdasarkan fitur metadata.
- **Kelebihan**: 
  - Mampu memberikan rekomendasi serupa dengan model input.
  - Tidak membutuhkan data interaksi pengguna.
- **Kekurangan**:
  - Bergantung pada kelengkapan dan kualitas metadata.
  - Tidak mempertimbangkan preferensi pengguna secara langsung.

**Collaborative Filtering**
- **Metode Evaluasi**:
  - **Root Mean Squared Error (RMSE)**:
    - RMSE Training: *0.1990*
    - RMSE Validation: *0.2840*
  - Metrik ini digunakan untuk mengukur perbedaan antara rating prediksi dan rating aktual.
  
   <img src="https://github.com/user-attachments/assets/ee09878a-b6a9-4e31-9927-ad32f4c2593a" alt="rmse" style="width:60%">

- **Kelebihan**:
  - Memberikan rekomendasi yang personal berdasarkan pola interaksi pengguna lain.
  - Tidak membutuhkan metadata yang lengkap.
- **Kekurangan**:
  - Membutuhkan data interaksi yang cukup besar.
  - Tidak dapat merekomendasikan item baru yang belum pernah dirating oleh pengguna lain (cold-start problem).

**Analisis Hasil**

1. **Content-Based Filtering** memberikan rekomendasi yang relevan untuk model tertentu berdasarkan metadata. Namun, pendekatan ini tidak mempertimbangkan pola preferensi pengguna secara personal.
2. **Collaborative Filtering** menunjukkan performa yang baik dalam menghasilkan rekomendasi personal untuk pengguna, dengan hasil RMSE yang menunjukkan kemampuan model dalam memprediksi rating mendekati nilai aktual.

**Kesimpulan dan Dampak**

**1. Performance Kedua Model**
- **Content-Based Filtering**:
  - Cocok untuk rekomendasi berbasis metadata yang seragam dan jelas.
  - Terbatas pada konteks metadata, sehingga tidak optimal untuk menangkap preferensi personal.
- **Collaborative Filtering**:
  - Lebih unggul dalam menangkap preferensi personal pengguna.
  - Membutuhkan data interaksi yang lebih besar dan sensitif terhadap masalah cold-start.

**2. Dampak pada Business Understanding**
- Rekomendasi dari **Content-Based Filtering** membantu pengguna menemukan produk serupa dalam kategori tertentu (e.g., brand, operating system).
- Rekomendasi dari **Collaborative Filtering** meningkatkan kepuasan pengguna dengan memberikan saran personal, meningkatkan potensi pembelian dan loyalitas pelanggan.

**3. Kesimpulan Akhir**
- Proyek ini berhasil menjawab problem statement dan mencapai goals yang telah ditentukan.
- Kombinasi kedua pendekatan (hybrid approach) dapat memberikan solusi rekomendasi yang lebih optimal, menggabungkan keunggulan metadata dan preferensi personal.

**4. Solusi Statement**
Solusi statement yang saya rencanakan berdampak pada:
- Meningkatkan pengalaman pengguna dalam menemukan produk yang relevan dan sesuai kebutuhan.
- Membantu bisnis meningkatkan engagement dan konversi melalui sistem rekomendasi yang efektif dan personal.