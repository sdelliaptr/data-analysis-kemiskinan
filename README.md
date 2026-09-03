# 📊 Analisis Kemiskinan Kabupaten/Kota di Indonesia

Proyek Uji Kompetensi (UJIKOM) — Exploratory Data Analysis & Data Cleaning terhadap data kemiskinan dan indikator sosial-ekonomi di 514 kabupaten/kota, 34 provinsi di Indonesia.

## 📌 Latar Belakang

Kemiskinan masih menjadi salah satu tantangan utama pembangunan di Indonesia, dengan tingkat yang sangat bervariasi antarwilayah. Proyek ini bertujuan menggali pola serta faktor sosial-ekonomi yang paling berhubungan dengan tingkat kemiskinan, sebagai dasar rekomendasi kebijakan maupun pemodelan lanjutan.

**Rumusan masalah:**
1. Bagaimana persebaran dan karakteristik tingkat kemiskinan di berbagai kabupaten/kota di Indonesia?
2. Faktor sosial-ekonomi apa yang paling berhubungan dengan tingkat kemiskinan?
3. Wilayah mana yang perlu menjadi prioritas intervensi?

## 🗂️ Dataset

| Detail | Keterangan |
|---|---|
| Jumlah baris (sebelum cleaning) | 532 |
| Jumlah kolom | 11 |
| Level data | Kabupaten/Kota |

**Kamus data:**

| Kolom | Deskripsi |
|---|---|
| `Provinsi` | Nama provinsi |
| `KabKota` | Nama kabupaten/kota |
| `Kemiskinan` | Persentase penduduk miskin (variabel target) |
| `RLS` | Rata-rata Lama Sekolah (tahun) |
| `Pengeluaran` | Rata-rata pengeluaran per kapita |
| `IPM` | Indeks Pembangunan Manusia |
| `UHH` | Umur Harapan Hidup |
| `Sanitasi` | Persentase akses sanitasi layak |
| `AirMinum` | Persentase akses air minum layak |
| `TPT` | Tingkat Pengangguran Terbuka (%) |
| `TPAK` | Tingkat Partisipasi Angkatan Kerja (%) |

## 🧹 Alur Analisis

1. **Data Understanding** — struktur data, statistik deskriptif, pengecekan nilai unik, missing value, outlier (boxplot + IQR), dan data duplikat.
2. **Data Cleaning**
   - Missing value pada `IPM`, `UHH`, `Sanitasi`, `AirMinum` ditangani dengan **imputasi median**.
   - Koreksi kesalahan input ekstrem: `Kemiskinan` Kota Medan (`834` → `8.34`, indikasi kesalahan format desimal).
   - Outlier ekstrem pada `TPT` (beberapa nilai >90%) ditangani dengan **clipping/winsorizing** menggunakan batas IQR, outlier pada variabel lain dipertahankan karena masih merepresentasikan kondisi riil antarwilayah.
   - 16 baris data duplikat dihapus.
   - Dataset bersih disimpan sebagai `dataset_kemiskinan_clean.csv`.
3. **Analisis Korelasi** — heatmap korelasi antar variabel numerik.
4. **Exploratory Data Analysis (EDA)** — distribusi variabel, perbandingan antarprovinsi/wilayah, dan hubungan antar-indikator.

## 💡 Insight Utama

- **Determinan kemiskinan terkuat**: `IPM` (r = -0.54), `Sanitasi` (r = -0.48), dan `UHH` (r = -0.40) memiliki korelasi negatif terkuat terhadap kemiskinan — wilayah dengan kualitas pembangunan manusia, kesehatan, dan sanitasi yang lebih baik cenderung punya kemiskinan lebih rendah.
- **Kesenjangan wilayah timur-barat**: Rata-rata kemiskinan tertinggi konsisten berada di **Papua (±28.6%)**, **Papua Barat (±24.2%)**, **Nusa Tenggara Timur (±19.3%)**, dan **Maluku (±17.6%)**, jauh di atas provinsi lain.
- **Kesenjangan kota-desa**: Seluruh 10 wilayah dengan IPM tertinggi adalah wilayah berstatus "Kota" (Yogyakarta, Banda Aceh, Kendari, dll), menunjukkan akses pendidikan/kesehatan/ekonomi yang lebih baik di perkotaan.
- **Kantong kemiskinan lokal**: Beberapa kabupaten dengan kemiskinan tertinggi (Morowali, Situbondo, Banyu Asin) justru berada di provinsi dengan rata-rata kemiskinan yang tidak paling tinggi — mengindikasikan perlunya kebijakan berbasis kabupaten/kota, bukan hanya provinsi.
- **IPM saja belum cukup**: Hubungan IPM–Kemiskinan negatif namun sebarannya cukup lebar pada rentang IPM menengah, menandakan faktor lain (geografis, struktur ekonomi lokal) turut berkontribusi.

## 🛠️ Tools & Library

- Python 3
- `pandas`, `numpy` — manipulasi data
- `seaborn`, `matplotlib` — visualisasi

## 📁 Struktur Repo

```
├── UJIKOM_DataKemiskinan_DelliaPutriSantoso.ipynb   # Notebook analisis lengkap
├── Dataset_Kemiskinan (1).csv                        # Dataset mentah
├── dataset_kemiskinan_clean.csv                       # Dataset hasil cleaning
└── README.md
```

## ▶️ Cara Menjalankan

```bash
pip install pandas numpy seaborn matplotlib
jupyter notebook UJIKOM_DataKemiskinan_DelliaPutriSantoso.ipynb
```

## ✍️ Author

**Dellia Putri Santoso**
