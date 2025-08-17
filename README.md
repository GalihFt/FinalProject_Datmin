# Hotel Reservation Cancellation Prediction Dashboard

## Ringkasan Proyek

Industri perhotelan sering menghadapi tantangan berupa tingginya tingkat pembatalan reservasi, yang berdampak langsung pada penurunan pendapatan dan efisiensi operasional. Proyek ini bertujuan untuk mengatasi masalah tersebut dengan mengembangkan sebuah dasbor interaktif menggunakan R Shiny. Dasbor ini menyediakan dua fungsionalitas utama: (1) analisis eksplorasi data untuk memvisualisasikan tren dan karakteristik reservasi, dan (2) model prediktif yang mampu memperkirakan kemungkinan seorang pelanggan akan membatalkan pesanannya.

Tujuan akhirnya adalah untuk menyediakan alat bantu bagi manajemen hotel dalam memahami pola pembatalan, sehingga dapat merancang strategi yang lebih efektif untuk meningkatkan retensi dan mengoptimalkan pendapatan.

---

## Fitur Dashboard

Dasbor ini terbagi menjadi tiga tab utama dengan fitur-fitur sebagai berikut:

#### 1. **Beranda**

* Halaman penyambutan yang menampilkan gambaran umum proyek.

#### 2. **Dashboard Visualisasi**

* **Filter Interaktif:** Pengguna dapat memfilter data berdasarkan status pemesanan (`Canceled` / `Not Canceled`) dan rentang tanggal kedatangan.
* **Indikator Kinerja Utama (KPI):** Menampilkan ringkasan metrik penting seperti Jumlah Total Pemesanan, Total Pendapatan, Rata-rata Lama Menginap di Akhir Pekan, dan Rata-rata Lama Menginap di Hari Kerja.
* **Visualisasi Data:**
  * Proporsi pelanggan yang kembali (`repeated_guest`) dalam bentuk diagram lingkaran.
  * Tren jumlah pemesanan dari waktu ke waktu dalam bentuk diagram garis.
  * Distribusi pelanggan berdasarkan segmen pasar (`market_segment_type`).
  * Analisis mendalam mengenai karakteristik tipe kamar yang dipesan.

#### 3. **Dashboard Klasifikasi (Prediksi)**

* **Input Data Pelanggan:** Formulir bagi pengguna untuk memasukkan detail reservasi baru.
* **Pilihan Model:** Pengguna dapat memilih salah satu dari empat model machine learning untuk melakukan prediksi:
  * Decision Tree
  * Naive Bayes
  * Regresi Logistik
  * XGBoost
* **Hasil Prediksi:** Probabilitas pembatalan ditampilkan secara visual melalui diagram lingkaran beserta interpretasi teksnya.
* **Evaluasi Model:** Menampilkan metrik kinerja (Akurasi, Sensitivitas, Spesifisitas, AUC) dari hasil validasi silang 10-fold, kurva ROC, serta plot fitur terpenting (*feature importance*) untuk model yang dipilih.

#### 4. **Database**

* Menyediakan akses untuk melihat tabel data mentah, struktur data, dan ringkasan statistik dari dataset yang digunakan.

---

## Pengaturan dan Instalasi

Untuk menjalankan dasbor ini secara lokal, ikuti langkah-langkah berikut:

**1. Prasyarat:**

* Pastikan Anda telah menginstal R dan RStudio di komputer Anda.

**2. File yang Dibutuhkan:**
Pastikan kedua file ini berada dalam satu direktori yang sama:

* `app.R` (kode aplikasi Shiny)
* `Hotel Reservations.csv` (dataset)

**3. Instalasi Pustaka (Libraries):**
Buka RStudio, lalu jalankan perintah berikut di konsol untuk menginstal semua pustaka yang diperlukan:

```R
install.packages(c(
  "shiny", "shinydashboard", "ggplot2", "dplyr", "DT", "tidyverse", 
  "readxl", "reshape", "plotly", "tidyr", "sf", "shinydashboardPlus", 
  "dashboardthemes", "xgboost", "caret", "pROC", "ggcorrplot", 
  "e1071", "randomForest", "naivebayes", "rsconnect"
))
```

4. **Menjalankan Aplikasi:**

* Buka file `app.R` di RStudio.
* Klik tombol **"Run App"** yang terletak di bagian kanan atas editor RStudio.
