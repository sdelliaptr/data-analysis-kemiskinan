# 📊 Analisis Kemiskinan Kabupaten/Kota di Indonesia

Proyek analisis data menggunakan Python untuk mengeksplorasi data kemiskinan dan indikator sosial-ekonomi pada tingkat kabupaten/kota di Indonesia.

## 📌 Tentang Proyek

Kemiskinan merupakan salah satu permasalahan sosial-ekonomi yang memiliki karakteristik berbeda di setiap wilayah. Proyek ini dilakukan untuk mengeksplorasi pola kemiskinan serta melihat hubungan antara tingkat kemiskinan dengan beberapa indikator sosial-ekonomi.

Analisis mencakup proses data understanding, data cleaning, exploratory data analysis (EDA), analisis korelasi, serta visualisasi data.

## 🎯 Tujuan Analisis

- Memahami karakteristik dan persebaran tingkat kemiskinan antarwilayah.
- Mengidentifikasi indikator sosial-ekonomi yang memiliki hubungan dengan tingkat kemiskinan.
- Membandingkan kondisi kemiskinan antarprovinsi dan kabupaten/kota.
- Menghasilkan insight berdasarkan hasil eksplorasi dan analisis data.

## 🗂️ Dataset

Dataset berisi data tingkat kabupaten/kota dengan beberapa indikator sosial-ekonomi.

### Variabel yang Digunakan

| Variabel | Deskripsi |
|---|---|
| `Provinsi` | Nama provinsi |
| `KabKota` | Nama kabupaten/kota |
| `Kemiskinan` | Persentase penduduk miskin |
| `RLS` | Rata-rata Lama Sekolah (tahun) |
| `Pengeluaran` | Rata-rata pengeluaran per kapita |
| `IPM` | Indeks Pembangunan Manusia |
| `UHH` | Umur Harapan Hidup |
| `Sanitasi` | Persentase akses sanitasi layak |
| `AirMinum` | Persentase akses air minum layak |
| `TPT` | Tingkat Pengangguran Terbuka (%) |
| `TPAK` | Tingkat Partisipasi Angkatan Kerja (%) |

## 🔍 Proses Analisis

### 1. Data Understanding
- Memahami struktur dan karakteristik dataset.
- Melakukan statistik deskriptif.
- Memeriksa nilai unik.
- Mengidentifikasi missing value.
- Mendeteksi outlier menggunakan boxplot dan metode IQR.
- Memeriksa data duplikat.

### 2. Data Cleaning
Beberapa proses yang dilakukan meliputi:

- Menangani missing value pada variabel `IPM`, `UHH`, `Sanitasi`, dan `AirMinum` menggunakan imputasi median.
- Mengoreksi nilai ekstrem pada data kemiskinan Kota Medan yang terindikasi sebagai kesalahan format desimal (`834` menjadi `8.34`).
- Menangani outlier ekstrem pada `TPT` menggunakan clipping/winsorizing berdasarkan batas IQR.
- Mempertahankan outlier pada variabel lain apabila masih merepresentasikan kondisi nyata antarwilayah.
- Menghapus 16 baris data duplikat.

### 3. Exploratory Data Analysis (EDA)
Analisis eksploratif dilakukan untuk melihat:

- Distribusi tingkat kemiskinan.
- Perbandingan tingkat kemiskinan antarprovinsi.
- Perbandingan karakteristik antarwilayah.
- Hubungan antara kemiskinan dengan indikator sosial-ekonomi.

### 4. Analisis Korelasi
Analisis korelasi digunakan untuk melihat hubungan antara tingkat kemiskinan dengan variabel numerik lainnya melalui correlation matrix dan heatmap.

## 💡 Insight Utama

- `IPM` memiliki korelasi negatif paling kuat dengan tingkat kemiskinan (r = -0.54), diikuti oleh `Sanitasi` (r = -0.48) dan `UHH` (r = -0.40).
- Beberapa provinsi seperti Papua, Papua Barat, Nusa Tenggara Timur, dan Maluku memiliki rata-rata tingkat kemiskinan yang relatif tinggi dibandingkan provinsi lainnya.
- Wilayah dengan IPM tinggi didominasi oleh wilayah berstatus kota, yang menunjukkan adanya perbedaan karakteristik pembangunan antara wilayah perkotaan dan kabupaten.
- Terdapat beberapa kabupaten/kota dengan tingkat kemiskinan tinggi meskipun rata-rata kemiskinan provinsinya tidak termasuk yang tertinggi. Hal ini menunjukkan adanya variasi kondisi kemiskinan di dalam suatu provinsi.
- Hubungan negatif antara IPM dan kemiskinan menunjukkan adanya keterkaitan antara kualitas pembangunan manusia dengan tingkat kemiskinan, meskipun faktor lain seperti kondisi geografis dan struktur ekonomi lokal juga dapat berperan.

## 🛠️ Tools & Libraries

- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## 📁 Struktur Repository

```text
data-analysis-kemiskinan/
├── README.md
└── notebooks/
    └── analisis-kemiskinan.ipynb

## ▶️ Cara Menjalankan

```bash
pip install pandas numpy seaborn matplotlib
jupyter notebook
notebooks/analisis-kemiskinan.ipynb
```

## 📊 Dashboard

Hasil analisis data kemiskinan divisualisasikan dalam dashboard interaktif menggunakan Looker Studio.

🔗 **Lihat Dashboard:** [Dashboard Analisis Kemiskinan](https://datastudio.google.com/reporting/6b7ec764-b513-4e50-835c-b2f42dcb3bf9)


## ✍️ Author

**Dellia Putri Santoso**
