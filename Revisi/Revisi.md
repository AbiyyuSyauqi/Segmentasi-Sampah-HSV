RINGKASAN REVISI PROGRAM
PEMROSESAN BATCH OTOMATIS
Program yang awalnya hanya memproses satu gambar tunggal telah diubah menjadi pemrosesan massal (batch processing). Program kini menggunakan pustaka os dan glob untuk menelusuri, mengekstrak, dan mengeksekusi 4752 gambar sekaligus secara otomatis dari dataset realwaste.zip di lingkungan Google Colab.

IMPLEMENTASI PUSTAKA SCIKIT-FUZZY UNTUK FCM
Mengubah pendekatan perhitungan algoritma Fuzzy C-Means (FCM) dari komputasi matematis manual menjadi pemanfaatan pustaka standar industri skfuzzy.cluster.cmeans (scikit-fuzzy). Peralihan ke pustaka eksternal ini secara drastis meningkatkan efisiensi waktu komputasi, stabilitas iterasi pencarian centroid, dan mencegah kebocoran memori saat menangani dataset berukuran besar.

PENAMBAHAN EVALUASI AKURASI DAN KEPUTUSAN MAYORITAS PIKSEL
Menambahkan logika pemetaan label asli (ground truth) untuk 9 kelas dataset dari UCI Machine Learning. Folder Food Organics dan Vegetation dipetakan sebagai label Organik, sedangkan 7 folder lainnya dipetakan sebagai Anorganik. Selain itu, pengambilan keputusan akhir model kini menggunakan logika "voting piksel", di mana gambar dilabeli "Organik" hanya jika lebih dari 50% piksel hasil segmentasinya masuk ke kluster organik. Label hasil prediksi ini kemudian dicocokkan dengan label asli untuk menghasilkan persentase akurasi biner (100 atau 0).

EKSPOR REKAPAN EVALUASI CSV SECARA MANDIRI
Menambahkan fungsi pembuatan laporan otomatis menggunakan pustaka Pandas. Seluruh hasil komputasi dari ribuan gambar (Nama File, Label Asli, Prediksi Model, Algoritma, Metrik Jarak, Waktu Eksekusi, Silhouette Score, dan Akurasi) direkap dan diekspor. Untuk mencegah tumpang tindih data (data overwrite), ekspor kini dipisah ke dalam dua file mandiri: rekapan_evaluasi_KMEANS.csv dan rekapan_evaluasi_FCM.csv.

PEMBARUAN VISUALISASI 1x4 SUBPLOTS DAN ANOTASI METRIK
Arsitektur perulangan visualisasi dirombak total. Pada algoritma K-Means, program kini memproses 3 metrik jarak terlebih dahulu lalu menampilkannya secara bersamaan dalam format 1 baris 4 kolom (Citra Asli - Euclidean - Manhattan - Minkowski). Pada judul setiap gambar hasil segmentasi, kini disematkan informasi Waktu Eksekusi (Runtime) dan Silhouette Score secara presisi (floating point 2 desimal) untuk memudahkan komparasi visual.

PEMBUATAN GRAFIK KOMPARASI STANDAR PUBLIKASI
Menambahkan satu skrip program visualisasi baru yang bertugas membaca kedua file CSV rekapan, kemudian mengonversinya menjadi dua grafik beresolusi tinggi (300 DPI) tanpa pola titik (dotted pattern). Grafik meliputi Bar Chart untuk komparasi tingkat Akurasi dan Scatter Plot untuk menganalisis trade-off antara Waktu Eksekusi vs Silhouette Score, disesuaikan dengan format formal jurnal ilmiah.

OPTIMASI MEMORI GOOGLE COLAB
Membatasi visualisasi keluaran (plotting gambar) hanya untuk 5 gambar pertama pada masing-masing algoritma. Modifikasi ini bertujuan untuk mencegah terjadinya crash atau kelebihan beban memori RAM pada session Google Colab, sementara perhitungan metrik evaluasi matematis untuk sisa 4747 gambar lainnya tetap dieksekusi secara penuh di latar belakang program.
