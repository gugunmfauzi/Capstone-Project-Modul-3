# Capstone-Project-Modul-3

**Business Problem**

**A. Context**

Bike-sharing systems adalah generasi baru dari penyewaan sepeda tradisional di mana seluruh proses, mulai dari keanggotaan, penyewaan, hingga pengembalian, telah menjadi otomatis. Sistem ini memungkinkan pengguna untuk menyewa sepeda dari satu lokasi dan mengembalikannya di lokasi lain. Dengan lebih dari 500 program di seluruh dunia yang terdiri dari lebih dari 500 ribu sepeda, sistem ini memainkan peran penting dalam masalah lalu lintas, lingkungan, dan kesehatan. Data yang dihasilkan oleh sistem ini, seperti durasi perjalanan, posisi keberangkatan, dan kedatangan, menjadikannya alat yang berguna untuk memantau mobilitas kota.

**B. Problem Statement**

Tantangan utama dalam sistem berbagi sepeda adalah memastikan ketersediaan sepeda yang memadai di setiap situasi. Kekurangan sepeda dapat mengakibatkan ketidakpuasan pelanggan dan hilangnya kepercayaan, sementara kelebihan stok menyebabkan pemborosan sumber daya dan biaya tinggi untuk manajemen, logistik, dan perawatan. Operator seperti Capital Bikeshare menghadapi tantangan ini dalam menjaga efisiensi operasional dan kepuasan pelanggan.

**C. Goals**

Untuk mengatasi masalah ini, Capital Bikeshare memerlukan alat prediksi yang efektif untuk menentukan jumlah sepeda yang tepat berdasarkan kondisi seperti cuaca, musim, kelembaban, dan suhu. Prediksi yang akurat akan meningkatkan profitabilitas, menjaga efisiensi biaya operasional, dan memastikan kebutuhan pelanggan terpenuhi dengan baik.nsi biaya operasional bagi Capital Bikeshare, serta memastikan kebutuhan pelanggan terpenuhi dengan baik.

**Data Cleaning, Feature Selection, & Feature Engineering**

**A. Data Cleaning**

1. **Mengatasi Nilai Hilang (Missing Values):**
   - Nilai hilang dapat menyebabkan bias dan kesalahan dalam model prediksi.
   - **Metode:** Mengisi nilai hilang dengan mean/median untuk fitur numerik atau mode untuk fitur kategorikal, atau menghapus baris yang memiliki banyak nilai hilang.

2. **Mengatasi Outliers:**
   - Outliers dapat mengganggu distribusi data dan mempengaruhi kinerja model.
   - **Metode:** Identifikasi outliers menggunakan metode seperti IQR atau Z-score dan pertimbangkan untuk menghapus atau mentransformasikannya.

3. **Standardisasi dan Normalisasi:**
   - Fitur dengan skala yang berbeda dapat mempengaruhi kinerja algoritma ML tertentu.
   - **Metode:** Menggunakan metode seperti StandardScaler atau MinMaxScaler dari pustaka seperti scikit-learn.

**B. Feature Selection**

1. **Analisis Korelasi:**
   - Mengidentifikasi fitur yang memiliki korelasi tinggi dengan target (``cnt``) dan menghapus fitur yang memiliki korelasi tinggi antar fitur (multikolinieritas).
   - **Metode:** Menggunakan matriks korelasi atau heatmap.

2. **Pemilihan Fitur Berdasarkan Kepentingan (Feature Importance):**
   - Beberapa fitur mungkin lebih penting daripada yang lain untuk model prediksi.
   - **Metode:** Menggunakan algoritma seperti Random Forest atau Gradient Boosting untuk menentukan pentingnya fitur.

**Feature Engineering**

1. **Pembuatan Fitur Baru (Feature Creation):**
   - Fitur baru dapat membantu model menangkap hubungan yang lebih kompleks dalam data.
   - **Metode:** Membuat fitur-fitur seperti "rush hour" berdasarkan kolom ``hr``, atau "hot day" berdasarkan ``temp``.

2. **Transformasi Fitur:**
   - Beberapa fitur mungkin tidak bersifat linear dan memerlukan transformasi agar model dapat memahaminya dengan lebih baik.
   - **Metode:** Log transformation, polynomial features, atau binning untuk fitur-fitur numerik.

**Analytics (Algorithm & Evaluation Metrics)**

**A. Pemodelan**

1. **Algoritma Model Machine Learning:**
   - **Algoritma yang digunakan:** Linear Regression, K-Nearest Neighbors (KNN), Decision Tree, Random Forest, AdaBoost, dan XGBoost.
   - **Cara kerja:** 
     - **Linear Regression** : Menemukan garis terbaik yang menggambarkan hubungan linear antara fitur input dan target.
     - **K-Nearest Neighbors (KNN)** : Membuat prediksi berdasarkan rata-rata nilai target dari k tetangga terdekat.
     - **Decision Tree** : Membagi data secara iteratif berdasarkan fitur untuk membuat pohon keputusan yang memprediksi nilai target.
     - **Random Forest** : Menggunakan banyak pohon keputusan untuk meningkatkan akurasi dan mengurangi overfitting
     - **AdaBoost** : Membangun model bertahap dengan menambahkan model sederhana yang memperbaiki kesalahan dari model sebelumnya.
     - **XGBoost** : Algoritma boosting yang cepat dan kuat, menggunakan gradient boosting untuk membangun model bertahap dan menangani data kompleks.
     

2. **Limitasi Model:**
   - **Kapan model dapat dipercaya:** Ketika data terdistribusi dengan baik, tidak ada outliers yang signifikan, dan fitur yang relevan telah dipilih.
   - **Kapan model tidak dapat dipercaya:** Ketika data memiliki banyak outliers, ada missing values yang signifikan, atau data tidak terdistribusi dengan baik.

**B. Evaluation Metrics**

1. **Regresi Metrics:**
   - **MAE (Mean Absolute Error):** Rata-rata dari absolut nilai error.
   - **MSE (Mean Squared Error):** Rata-rata dari kuadrat nilai error, lebih sensitif terhadap outliers.
   - **RMSE (Root Mean Squared Error):** Akar kuadrat dari MSE, interpretasi lebih intuitif karena dalam satuan yang sama dengan target.
   - **MAPE (Mean Absolute Percentage Error):** Rata-rata persentase error, berguna untuk memahami kesalahan relatif terhadap ukuran data.
   - **R-squared:** Mengukur seberapa baik model menjelaskan variabilitas dari data.

2. **Pemilihan Metrics:**
   - **MAE:** Baik untuk data dengan sedikit outliers.
   - **MSE/RMSE:** Berguna ketika outliers penting untuk diperhatikan.
   - **MAPE:** Baik untuk pemahaman persentase kesalahan relatif.
   - **R-squared:** Baik untuk mengetahui seberapa baik model menjelaskan variabilitas data.

**Hubungan dengan Aspek Bisnis:**

- **Akurasi Prediksi:** Memastikan bahwa jumlah sepeda yang tersedia sesuai dengan kebutuhan pengguna.
- **Efisiensi Operasional:** Mengurangi biaya terkait dengan pengelolaan sepeda yang tidak terpakai.
- **Kepuasan Pelanggan:** Menyediakan jumlah sepeda yang memadai sehingga meningkatkan kepercayaan dan kepuasan pelanggan terhadap layanan.

Dengan pendekatan ini, model machine learning dapat digunakan untuk meningkatkan efisiensi operasional dan kepuasan pelanggan dalam sistem berbagi sepeda.
