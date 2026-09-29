# 📊 Data Analyst Portfolio: Fraud Detection pada Data Transaksi 🕵️‍♂️💳

Proyek ini berangkat dari satu pertanyaan: **Seberapa efektif sistem dalam mendeteksi transaksi fraud, dan apa yang bisa kita pelajari dari data untuk meningkatkannya?**

Dengan menganalisis lebih dari 6,3 juta transaksi keuangan, proyek ini mengeksplorasi pola transaksi, mengukur efektivitas sistem deteksi yang sudah ada, serta mengembangkan pendekatan berbasis data untuk mengidentifikasi aktivitas mencurigakan.

Tidak hanya berfokus pada pemodelan *machine learning*, proyek ini juga menekankan bagaimana hasil analisis dapat diterjemahkan menjadi wawasan yang relevan bagi bisnis.

## 🔍 Business Understanding

Analisis awal mengungkap beberapa temuan yang menjadi dasar pengembangan sistem deteksi fraud:

* **Potensi kerugian finansial:** Total nilai transaksi fraud mencapai sekitar **$12,06 miliar**, menunjukkan besarnya risiko yang perlu mendapat perhatian.
* **Keterbatasan sistem deteksi saat ini:** Dari 8.213 transaksi fraud yang terjadi, sistem bawaan hanya berhasil mengidentifikasi 16 transaksi, dengan *recall* sebesar **0,1948%**.
* **Ketimpangan data:** Transaksi fraud hanya mencakup **0,129%** dari keseluruhan data. Kondisi ini menjadi tantangan tersendiri karena model berpotensi lebih banyak mengenali transaksi normal dibandingkan transaksi fraud.

Temuan tersebut menjadi landasan untuk mengeksplorasi pendekatan deteksi yang lebih efektif, dengan tetap mempertimbangkan keseimbangan antara kemampuan mendeteksi fraud dan risiko kesalahan prediksi.

## 📈 Exploratory Data Analysis (EDA)

Tahap eksplorasi dilakukan untuk memahami karakteristik transaksi dan menemukan pola yang dapat membantu proses deteksi fraud.

Beberapa temuan utama meliputi:

* **Distribusi transaksi:** Penggunaan visualisasi dengan skala logaritmik membantu memperlihatkan ketimpangan yang sangat besar antara transaksi normal dan fraud.
* **Pola berdasarkan tipe transaksi:** Seluruh kasus fraud dalam dataset ditemukan pada dua tipe transaksi, yaitu `CASH_OUT` dan `TRANSFER`. Temuan ini memberikan gambaran mengenai jenis transaksi yang perlu mendapat perhatian lebih dalam proses pemantauan.

## ⚙️ Feature Engineering

Untuk memperkaya informasi yang digunakan model, dilakukan pembuatan fitur baru berdasarkan hubungan antara nominal transaksi dan perubahan saldo rekening.

* **`errorBalanceOrig`** — Mengukur selisih antara saldo akhir pengirim yang tercatat dan saldo yang seharusnya berdasarkan nominal transaksi. Selisih ini dapat membantu mengidentifikasi ketidaksesuaian pada aliran dana.
* **`errorBalanceDest`** — Mengukur selisih antara saldo akhir penerima yang tercatat dan saldo yang diperkirakan setelah transaksi. Fitur ini digunakan untuk menangkap anomali pada sisi penerima.

Kedua fitur tersebut diharapkan dapat memberikan konteks tambahan bagi model dalam membedakan transaksi normal dan transaksi yang mencurigakan.

## 🤖 Model Development

Setelah proses pembersihan data dan penanganan *class imbalance*, beberapa algoritma *machine learning* diuji untuk membandingkan kemampuannya dalam mendeteksi fraud.

Eksperimen mencakup Random Forest, LightGBM, XGBoost, Gradient Boosting, dan Logistic Regression. Evaluasi dilakukan dengan mempertimbangkan metrik seperti Precision, Recall, dan F1-Score, mengingat keberhasilan deteksi fraud tidak cukup diukur hanya dari akurasi keseluruhan.

## 📁 Struktur Repositori

| File / Direktori                    | Deskripsi                                                                                                                                                                 |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Dataset/`                          | Direktori untuk menyimpan dataset yang digunakan dalam analisis. File `AIML Dataset.csv` tidak disertakan dalam repository karena ukurannya melebihi batas unggah GitHub. |
| `fraud-detection-project.ipynb`     | Notebook utama yang mencakup seluruh proses, mulai dari EDA, preprocessing, feature engineering, penanganan class imbalance, hingga pemodelan dan evaluasi.               |
| `random_forest_fraud_detection.pkl` | Model Random Forest yang telah dilatih dan disimpan agar dapat digunakan kembali untuk prediksi.                                                                          |
| `visualisasi_afsmote.png`           | Visualisasi distribusi kelas setelah penerapan teknik AFS-MOTE.                                                                                                           |

## 🛠️ Tools & Technologies

* **Programming Language:** Python
* **Data Analysis:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-learn
* **Imbalanced Data Handling:** Imbalanced-learn (undersampling dan SMOTE)

## 🚀 Getting Started

Untuk menjalankan proyek ini secara lokal:

1. Clone repository:

   ```bash
   git clone https://github.com/Iwannnwn/FraudDetection.git
   ```

2. Pastikan dataset tersedia pada direktori yang sesuai atau sesuaikan path dataset di dalam notebook.

3. Instal library yang dibutuhkan:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn lightgbm xgboost jupyter
   ```

4. Jalankan Jupyter Notebook:

   ```bash
   jupyter notebook fraud-detection-project.ipynb
   ```

---

*Proyek ini merupakan bagian dari portofolio Data Analyst yang mengeksplorasi bagaimana analisis data, pemahaman proses bisnis, dan machine learning dapat digunakan bersama untuk mengidentifikasi risiko serta mendukung pengambilan keputusan berbasis data.*
