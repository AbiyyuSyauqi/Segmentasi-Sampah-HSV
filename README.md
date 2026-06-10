# Segmentasi Citra Sampah Organik dan Anorganik Berbasis HSV

Repositori ini berisi implementasi dari tugas Project KDKA 2025 C pada program studi S1 Kecerdasan Buatan, Universitas Negeri Surabaya. Proyek ini memfokuskan pada pengujian dan komparasi kinerja algoritma *Unsupervised Learning* berskala besar dalam melakukan segmentasi dan klasifikasi citra sampah.

## Tim Pengembang
1. **Abiyyu Syauqi Admaja** *(Pengembangan Algoritma K-Means Clustering from scratch, Implementasi Pustaka Fuzzy C-Means (FCM), Perancangan Arsitektur Batch Processing, Pemetaan Ground Truth & Akurasi Piksel, Rule-based Heuristics, Analisis Evaluasi Metrik, dan Pemeliharaan Repositori)*
2. **Ilmanza Nafis Adidarma** *(Image Preprocessing, Visualisasi Data Spasial, Komparasi Waktu Eksekusi, dan Silhouette Scoring)*
3. **Evans Lordy Arrow Sarumaha** *(Perekapan Dokumentasi Gambar)*

## Deskripsi Proyek
Sistem ini dirancang untuk mendeteksi dan memisahkan objek sampah organik dan anorganik dari latar belakangnya secara otomatis menggunakan ekstraksi fitur ruang warna HSV (*Hue, Saturation, Value*). 

Proyek ini mengimplementasikan dan membandingkan dua pendekatan klasterisasi secara mendalam terhadap dataset berskala besar (RealWaste):
1. **K-Means Clustering (Hard Clustering):** Diimplementasikan secara manual (*from scratch*) untuk memisahkan piksel secara mutlak. Algoritma ini diuji menggunakan tiga metrik jarak spasial yang berbeda: **Euclidean, Manhattan, dan Minkowski**.
2. **Fuzzy C-Means / FCM (Soft Clustering):** Diimplementasikan menggunakan pustaka `scikit-fuzzy` untuk menangani ketidakpastian batas warna akibat pantulan cahaya, guna mengoptimalkan efisiensi memori dan waktu komputasi.

## Fitur Utama
- **Pemrosesan Batch Otomatis:** Skrip mampu menelusuri, mengeksekusi, dan mengekstrak metrik dari 4752 citra sekaligus tanpa kendala *memory crash*.
- **Rule-based Heuristics:** Implementasi logika "voting piksel" untuk penentuan kelas akhir (Organik/Anorganik) berdasarkan mayoritas piksel hasil segmentasi (>50%).
- **Automated Reporting:** Sistem secara otomatis merekap hasil evaluasi (Waktu Eksekusi, Silhouette Score, Akurasi) dari ribuan citra ke dalam file `.csv` (`rekapan_evaluasi_KMEANS.csv` dan `rekapan_evaluasi_FCM.csv`).
- **Visualisasi Komparasi Standar Publikasi:** Menghasilkan grafik bar dan *scatter plot tradeoff* beresolusi tinggi (300 DPI) untuk analisis metrik.

## Teknologi dan Pustaka/Library yang Digunakan
- **Python 3** (Bahasa Pemrograman Utama)
- **OpenCV (`cv2`)** - Manipulasi dan konversi ruang warna citra (BGR ke HSV/RGB).
- **NumPy** - Komputasi matriks, vektorisasi, dan *broadcasting*.
- **Pandas** - Pembuatan dan ekspor laporan evaluasi data tabular.
- **Scikit-Fuzzy (`skfuzzy`)** - Mesin komputasi klasterisasi probabilitas FCM.
- **Scikit-Learn (`sklearn`)** - Evaluasi validasi klaster menggunakan *Silhouette Score*.
- **Matplotlib** - Visualisasi hasil *masking* segmentasi dan *plotting* grafik evaluasi.
- **OS & Glob** - Manajemen direktori dan penelusuran *path* dataset secara otomatis.
