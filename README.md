# 🧠 Predictive Model for Customer Loyalty

Proyek machine learning untuk memprediksi apakah seorang pelanggan (member) akan melakukan pembelian kembali pada bulan berikutnya, menggunakan data transaksional dari program loyalitas **Intelectra** — perusahaan produksi dan penjualan susu bayi.

## 📌 Tujuan

Membangun model klasifikasi yang mampu memprediksi probabilitas seorang anggota akan melakukan pembelian kembali bulan depan (`next_buy`: 1 = Ya, 0 = Tidak), guna membantu strategi pemasaran yang lebih tepat sasaran dan meningkatkan retensi pelanggan.

## 📁 Struktur Proyek

```
Customer Loyalty Prediction/
├── predictive-model-for-customer-loyalty.ipynb   # Notebook utama
├── README.md                                      # Dokumentasi proyek
├── requirements.txt                               # Daftar dependency
├── .gitignore                                     # File yang diabaikan Git
└── Customer Loyalty Dataset/                      # Dataset
    ├── member_data.csv                            # Data anggota
    ├── train_transaction_data.csv                 # Transaksi training
    ├── test_transaction_data.csv                  # Transaksi testing
    ├── train_label_data.csv                       # Label target
    ├── product_data.csv                           # Data produk
    ├── prodgram_data.csv                          # Data gramasi produk
    └── sample_submission.csv                      # Template submission
```

## 📊 Deskripsi Dataset

| Tabel | Deskripsi |
|-------|-----------|
| **Member** | Data demografi anggota: ID, tanggal join, kota, jumlah anak, tanggal lahir anak |
| **Transaksi** | Riwayat pembelian: ID transaksi, sumber outlet, produk, kuantitas, harga, tanggal |
| **Produk** | Katalog produk: nama, kategori, level |
| **Prodgram** | Detail gramasi: berat, poin, harga perkiraan |
| **Label** | Target variabel: MemberID dan status pembelian bulan depan |

## 🚀 Cara Menjalankan

### 1. Clone Repository
```bash
git clone <repository-url>
cd "Customer Loyalty Prediction"
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Jalankan Notebook
```bash
jupyter notebook predictive-model-for-customer-loyalty.ipynb
```

## 🔬 Metodologi

1. **EDA & Data Preparation** — Eksplorasi data, handling missing values, deteksi duplikasi
2. **Feature Engineering** — Pembuatan fitur dari data transaksi dan member
3. **Modeling** — XGBoost dan Multi-Layer Perceptron (MLP) dengan hyperparameter tuning
4. **Evaluasi** — Feature importance, correlation analysis, permutation importance

## 🛠️ Tech Stack

- **Python 3.11+**
- **Pandas & NumPy** — Manipulasi data
- **Scikit-learn** — Preprocessing, evaluasi model
- **XGBoost** — Gradient boosting classifier
- **TensorFlow/Keras** — Neural network (MLP)
- **Matplotlib & Seaborn** — Visualisasi

## 📝 Lisensi

Proyek ini dibuat untuk keperluan kompetisi Machine Learning Quest oleh INTELLECTRA.
