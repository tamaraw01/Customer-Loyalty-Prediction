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

## Run the notebook

Clone the repository and work from its root directory so the notebook can resolve `DATA_DIR = 'Customer Loyalty Dataset'`.

```bash
git clone https://github.com/tamaraw01/Customer-Loyalty-Prediction.git
cd Customer-Loyalty-Prediction
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m pip install notebook
python -m notebook predictive-model-for-customer-loyalty.ipynb
```

The [requirements file](requirements.txt) lists the modeling libraries but does not include the Jupyter Notebook interface, which the separate install command provides. Open the [notebook](predictive-model-for-customer-loyalty.ipynb) and run its cells in order.

### Generated files

The notebook writes these CSV files to the working directory as the corresponding sections complete:

- `submission_xgb.csv`: predictions from the first XGBoost model.
- `submission_xgb_improved.csv`: predictions from the final XGBoost model after the validation and cross-validation section.
- `submission.csv`: MLP ensemble predictions, averaged across folds and then across transactions for each member before applying a probability threshold of `0.5`.

All three files contain `MemberID` and `next_buy`, with `next_buy` stored as a class label (`0` or `1`), not a probability. The XGBoost exports follow the member list in `sample_submission.csv`; the MLP export groups the test transactions by `MemberID` instead. Check its member coverage against the sample before submitting it.

Move any existing copies of these files before rerunning their export cells, which overwrite the same filenames. The MLP tuning section also uses `keras_tuner_dir/next_buy_prediction` for its search artifacts.

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
