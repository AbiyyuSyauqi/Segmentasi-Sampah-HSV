RINGKASAN REVISI PROGRAM

PEMROSESAN BATCH OTOMATIS
Program yang awalnya hanya memproses satu gambar tunggal telah diubah menjadi pemrosesan massal (batch processing). Program kini menggunakan pustaka os dan glob untuk menelusuri, mengekstrak, dan mengeksekusi 4752 gambar sekaligus secara otomatis dari dataset realwaste.zip di lingkungan Google Colab.

PENAMBAHAN EVALUASI AKURASI DAN GROUND TRUTH
Menambahkan logika pemetaan label asli (ground truth) untuk 9 kelas dataset dari UCI Machine Learning. Folder Food Organics dan Vegetation dipetakan sebagai label Organik, sedangkan 7 folder lainnya dipetakan sebagai Anorganik. Label asli ini kemudian dibandingkan dengan hasil prediksi sistem untuk menghasilkan persentase akurasi.

EKSPOR REKAPAN EVALUASI KE CSV
Menambahkan fungsi pembuatan laporan otomatis menggunakan pustaka Pandas. Seluruh hasil komputasi dari ribuan gambar tersebut (Nama File, Label Asli, Hasil Prediksi, Algoritma, Metrik Jarak, Waktu Eksekusi, Silhouette Score, dan Akurasi) direkap dan diekspor ke dalam satu file bernama rekapan_evaluasi_final.csv.

OPTIMASI MEMORI GOOGLE COLAB
Membatasi visualisasi keluaran (plotting gambar) hanya untuk 5 gambar pertama. Modifikasi ini bertujuan untuk mencegah terjadinya crash atau kelebihan beban memori RAM pada Google Colab, sementara perhitungan metrik evaluasi untuk sisa 4747 gambar lainnya tetap dieksekusi secara penuh di latar belakang.
