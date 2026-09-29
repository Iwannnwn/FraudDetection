# Fraud Detection Project 🕵️‍♂️💳

Repositori ini berisi proyek *machine learning* untuk mendeteksi kasus penipuan (*fraud detection*). Mengingat kasus *fraud* umumnya memiliki jumlah data yang sangat tidak seimbang (*imbalanced dataset*), proyek ini mengeksplorasi teknik penanganan ketidakseimbangan kelas (seperti SMOTE/undersampling) dan pemodelan prediktif untuk mengklasifikasikan transaksi atau aktivitas penipuan.

## 📁 Struktur Repositori

Berikut adalah penjelasan mengenai file dan direktori yang ada di dalam repositori ini:

*   **`Dataset/`** : Direktori yang berisi dataset mentah atau yang sudah diproses untuk digunakan dalam pelatihan model.
*   **`fraud-detection-project.ipynb`** : File *Jupyter Notebook* utama yang merangkum seluruh alur kerja proyek. Mulai dari Eksplorasi Data (EDA), *Data Preprocessing*, penanganan *imbalanced data*, hingga pelatihan dan evaluasi model klasifikasi.
*   **`random_forest_fraud_detection.pkl`** : Model *Machine Learning* (Random Forest) yang telah dilatih dan diekspor dalam format *pickle*. Model ini siap digunakan untuk inferensi atau *deployment* pada data baru tanpa perlu melatih ulang.
*   **`visualisasi_afsmote.png`** : Hasil visualisasi distribusi data setelah diterapkannya teknik *handling imbalanced* (berkaitan dengan algoritma AFS-MOTE).

## 🛠️ Teknologi & Library yang Digunakan

Proyek ini dibangun menggunakan bahasa pemrograman **Python** dengan bantuan beberapa library *data science* populer, antara lain:
*   **Pandas & NumPy** (Manipulasi data)
*   **Scikit-Learn** (Pembuatan model *Machine Learning* & evaluasi metrik)
*   **Imbalanced-learn** (Teknik *sampling* data)
*   **Matplotlib & Seaborn** (Visualisasi data)

## 🚀 Cara Menjalankan Proyek Secara Lokal

1. **Clone repositori ini ke komputer Anda:**
   ```bash
   git clone [https://github.com/Iwannnwn/FraudDetection.git](https://github.com/Iwannnwn/FraudDetection.git)
