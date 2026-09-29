# 📊 Data Analyst Portfolio: Fraud Detection pada Data Transaksi 🕵️‍♂️💳

Repositori ini berisi portofolio Data Analytics yang berfokus pada deteksi anomali dan kecurangan (*fraud*) pada data transaksi keuangan. Proyek ini bertujuan untuk menggali wawasan (*insights*) dari jutaan data transaksi, mengevaluasi efektivitas sistem deteksi bawaan, serta mempersiapkan data untuk pemodelan prediktif tingkat lanjut.

## 📌 Latar Belakang & Problem Statement
Berdasarkan analisis awal terhadap lebih dari 6,3 juta data transaksi, ditemukan beberapa permasalahan bisnis yang kritikal:
1. **Kerugian Finansial Masif:** Total kerugian akibat transaksi *fraud* mencapai angka yang sangat fantastis, yakni sekitar **$12,056,415,427.84**. Kasus penipuan ini secara spesifik hanya terjadi pada dua tipe transaksi: `CASH_OUT` dan `TRANSFER`.
2. **Sistem Lama Tidak Efektif:** Perusahaan memiliki sistem deteksi bawaan (kolom `isFlaggedFraud`), namun kinerjanya sangat buruk. Dari 8.213 transaksi *fraud* aktual, sistem lama hanya berhasil mendeteksi 16 transaksi (**Recall hanya mencapai 0.1948%**).
3. **Ketidakseimbangan Data (Class Imbalance):** Penipuan adalah kejadian langka. Persentase *fraud* hanya sebesar **0.129%** (8.213 transaksi) berbanding transaksi normal yang mencapai lebih dari 6,3 juta transaksi. Hal ini menjadi tantangan besar dalam mendesain sistem deteksi baru.

## 💡 Exploratory Data Analysis (EDA) & Key Insights
Dalam proyek ini, dilakukan eksplorasi mendalam untuk memahami karakteristik transaksi:
* **Distribusi Kelas:** Visualisasi log-scale digunakan untuk menyoroti rasio ketimpangan yang ekstrem antara transaksi Normal dan Fraud.
* **Tipe Transaksi:** Identifikasi secara presisi bahwa *fraudster* (pelaku penipuan) hanya memanfaatkan metode `CASH_OUT` dan `TRANSFER` untuk memindahkan dan mencairkan dana.

## ⚙️ Feature Engineering (Pendekatan Logika Analitik)
Sebagai seorang Data Analyst, saya merancang variabel baru berdasarkan logika perbankan untuk mendeteksi manipulasi saldo:
* **`errorBalanceOrig` (Anomali Saldo Pengirim):** Secara logika, Saldo Baru Pengirim = Saldo Lama - Nominal Transaksi. Jika hasil perhitungannya bukan 0, hal ini menjadi indikator kuat adanya manipulasi aliran dana di sisi pengirim.
* **`errorBalanceDest` (Anomali Saldo Penerima):** Saldo Baru Penerima haruslah sama dengan Saldo Lama + Nominal Masuk. Selisih dari perhitungan ini digunakan sebagai bendera merah (*red flag*) untuk indikasi *fraud*.

## 📁 Struktur Repositori
* **`Dataset/`** : Direktori untuk menyimpan data mentah. (Karena ukuran file > 500MB, file `AIML Dataset.csv` tidak diunggah ke GitHub).
* **`fraud-detection-project.ipynb`** : *Jupyter Notebook* utama yang berisi seluruh alur kerja (EDA, pembersihan data, pembuatan fitur baru, evaluasi metrik bisnis, hingga *machine learning*).
* **`random_forest_fraud_detection.pkl`** : Model *Machine Learning* yang berhasil dilatih untuk memprediksi *fraud* pada data baru.
* **`visualisasi_afsmote.png`** : Hasil visualisasi distribusi data setelah penanganan kasus *imbalanced data*.

## 🛠️ Alat & Teknologi
* **Bahasa Pemrograman:** Python
* **Data Manipulation & Analysis:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn
* **Predictive Analytics:** Scikit-Learn, Imbalanced-learn (Undersampling/SMOTE)

## 🚀 Cara Menjalankan Notebook
1. *Clone* repositori ini: `git clone https://github.com/Iwannnwn/FraudDetection.git`
2. Pastikan *dataset* berada di path yang tepat atau ubah path di dalam *notebook*.
3. Instal pustaka yang dibutuhkan: `pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn`
4. Buka dengan Jupyter Notebook atau JupyterLab: `jupyter notebook fraud-detection-project.ipynb`

---
*Bagi perekrut atau profesional, silakan tinjau notebook utama untuk melihat secara detail bagaimana pendekatan logika bisnis diubah menjadi kode analitik.*
