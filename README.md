SEGMENTASI CITRA SAMPAH ORGANIK DAN ANORGANIK BERBASIS HSV

Repositori ini berisi implementasi dari tugas Project KDKA 2025 C pada program studi S1 Kecerdasan Buatan, Universitas Negeri Surabaya. Proyek ini membandingkan kinerja algoritma Unsupervised Learning dalam melakukan segmentasi citra sampah.

TIM PENGEMBANG
1. Abiyyu Syauqi Admaja (Fuzzy C-Means, Rule-based Heuristics, Analisis Evaluasi)
2. Ilmanza Nafis Adidarma (K-Means Clustering from scratch, Image Preprocessing, Silhouette Scoring)
3. Evans Lordy Arrow Sarumaha (Visualisasi Data, Komparasi Waktu Eksekusi, Pelaporan Teknis)

DESKRIPSI PROYEK
Sistem ini dirancang untuk mendeteksi dan memisahkan objek sampah organik dan anorganik dari latar belakangnya secara otomatis menggunakan fitur ruang warna HSV (Hue, Saturation, Value). 

Proyek ini mengimplementasikan dan membandingkan dua pendekatan klasterisasi:
1. K-Means Clustering (Hard Clustering): Diimplementasikan secara manual (from scratch) untuk memisahkan piksel secara mutlak menggunakan metrik jarak spasial.
2. Fuzzy C-Means atau FCM (Soft Clustering): Diimplementasikan menggunakan pustaka scikit-fuzzy untuk menangani ketidakpastian batas warna akibat pantulan cahaya.

TEKNOLOGI DAN PUSTAKA YANG DIGUNAKAN
- Python 3
- OpenCV (cv2) untuk manipulasi dan konversi ruang warna citra
- NumPy untuk komputasi matriks dan broadcasting
- Scikit-Fuzzy untuk mesin klasterisasi probabilitas FCM
- Scikit-Learn untuk evaluasi metrik Silhouette Score
- Matplotlib untuk visualisasi hasil masking segementasi
