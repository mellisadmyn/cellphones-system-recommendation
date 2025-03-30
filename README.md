# Cellphone Recommendation System

Proyek ini merupakan bagian dari submission akhir pada **Machine Learning Terapan** di Dicoding. Tujuan utama adalah membangun sistem rekomendasi ponsel berdasarkan spesifikasi perangkat dan interaksi pengguna. Model ini akan memberikan rekomendasi **top 5 ponsel terbaik** untuk setiap pengguna berdasarkan preferensi mereka.

Pendekatan utama yang digunakan:
- **Content-Based Filtering**: Merekomendasikan ponsel berdasarkan kesamaan spesifikasi seperti harga, prosesor, kapasitas baterai, dan fitur lainnya.
- **Collaborative Filtering**: Menggunakan data interaksi pengguna seperti rating dan ulasan untuk mempelajari pola preferensi dan memberikan rekomendasi berdasarkan perilaku pengguna lain.


## 🎯 Objectives
1. **Membangun Content-Based Filtering**:
   - Menggunakan algoritma **cosine similarity** atau **TF-IDF** untuk mengukur kesamaan antar ponsel.
   - Merekomendasikan ponsel berdasarkan atribut spesifikasi seperti harga, prosesor, kapasitas baterai, dan fitur lainnya.

2. **Membangun Collaborative Filtering**:
   - Menggunakan interaksi pengguna seperti rating dan ulasan untuk membangun sistem rekomendasi.
   - Menerapkan metode **Matrix Factorization** (misalnya, SVD) atau model deep learning berbasis embedding.


## 📑 Methodology

### 1️⃣ Data Collection
Dataset yang digunakan berasal dari **Kaggle - Cellphones Recommendations Dataset**. Dataset ini diunduh dalam format ZIP dan diekstrak untuk diproses lebih lanjut.

### 2️⃣ Data Understanding
Analisis awal dataset meliputi:
- Pemuatan tiga dataset utama.
- Menampilkan dimensi dan struktur dataset menggunakan `.info()`.
- Identifikasi nilai yang hilang, seperti kolom `occupation` pada `cellphones_users` yang memiliki missing values.

### 3️⃣ Exploratory Data Analysis (EDA)
Dilakukan untuk memahami pola dan distribusi data melalui:
- Analisis distribusi brand ponsel.
- Korelasi antar fitur utama.
- Visualisasi data menggunakan `seaborn` dan `matplotlib` untuk mendapatkan insight lebih lanjut.

### 4️⃣ Data Preparation
Tahap persiapan data meliputi:
- Pembersihan data yang tidak relevan.
- Transformasi fitur untuk memastikan format sesuai.
- Normalisasi data jika diperlukan untuk meningkatkan akurasi model.

### 5️⃣ Modeling
Model rekomendasi dibangun dengan dua metode utama:
- **Content-Based Filtering**
  - Menggunakan **TF-IDF Vectorizer** untuk representasi teks.
  - Menghitung kesamaan antar produk dengan **Cosine Similarity**.

- **Collaborative Filtering**
  - Menggunakan **Deep Learning** dengan **TensorFlow dan Keras**.
  - Membangun **embedding layer** untuk memahami hubungan antar produk dan pengguna.
  - Menerapkan regularisasi untuk menghindari overfitting.

### 6️⃣ Evaluation
Evaluasi model menggunakan beberapa metrik utama:
- **Akurasi prediksi kesamaan produk**.
- Validasi silang untuk mengukur performa model.
- Perbandingan performa antara Content-Based Filtering dan Collaborative Filtering.

### 7️⃣ Deployment
Setelah model diuji dan dievaluasi, model ini siap digunakan dalam sistem rekomendasi ponsel berbasis teks.



## 📊 Submission Review
<img width="936" alt="score-submission-akhir" src="https://github.com/user-attachments/assets/3e9bfbdf-a1e7-4a9f-83db-b63a95709b89" />

## 📌 Conclusion
Proyek ini berhasil membangun sistem rekomendasi ponsel menggunakan Content-Based Filtering dan Collaborative Filtering. Model yang dikembangkan untuk memberikan rekomendasi ponsel berdasarkan spesifikasi produk maupun interaksi pengguna dengan tingkat akurasi yang cukup baik. Ke depan, model ini dapat ditingkatkan dengan data yang lebih besar serta optimasi algoritma untuk meningkatkan performa dan relevansi rekomendasi.


📌 **Author:** Mellisa  
📅 **Date:** 24-11-2024  
🛠 **Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, TensorFlow, Keras, TF-IDF Vectorizer, Cosine Similarity, SVD