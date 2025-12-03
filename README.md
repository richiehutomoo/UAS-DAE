Laporan Singkat Workflow KNIME
# Richie C14250090 & David C14250084
Workflow ini dibuat untuk melakukan preprocessing data, analisis visual, serta pembuatan model machine learning berbasis Decision Tree. Tahapan yang dilakukan adalah sebagai berikut:

## 1. CSV Reader
Dataset diimpor menggunakan node CSV Reader untuk membaca file berformat .csv sebagai sumber data awal. Node ini digunakan untuk mengambil data mentah dari file CSV ToyotaCorolla.
Outputnya berupa tabel yang akan digunakan untuk seluruh proses berikutnya.

## 2. Column Filter
Node ini digunakan untuk memilih kolom-kolom yang diperlukan dan menghapus kolom yang tidak relevan sehingga data lebih fokus dan efisien diproses.

Digunakan untuk memilih kolom yang diperlukan saja, yaitu:

- Tahun

- Harga

Tujuannya agar workflow fokus pada variabel yang relevan.

## 3. Row Filter
Baris data di filter berdasarkan kondisi tertentu untuk menyaring data sesuai kebutuhan analisis, yaitu memfilter data harga dari tahun 1998 - 2004.

## 4. GroupBy
Data dikelompokkan berdasarkan kolom tertentu dan dilakukan agregasi seperti menghitung rata-rata, jumlah, atau nilai maksimum.

Karena dalam satu tahun terdapat banyak harga, node ini menghitung:

Average (mean) harga per tahun

Hasilnya: satu baris per tahun, dengan harga rata-rata.

## 5. Column Renamer
Nama kolom diperbaiki agar lebih jelas, konsisten, dan mudah dipahami.

## 6. Visualisasi Data (Table, Bar Chart, Line Plot)
Table View digunakan untuk melihat data secara detail.
Bar Chart menampilkan distribusi data secara visual untuk mempermudah interpretasi.
Line Plot digunakan untuk melihat pola atau tren berdasarkan urutan data.

## 7. Rule Engine
Node ini digunakan untuk membuat kolom baru berdasarkan aturan logika tertentu, seperti klasifikasi threshold, pemberian kategori, atau label awal untuk model.

Harga rata-rata <= 10000 => "Murah"

Harga rata-rata <= 15000 => "Sedang"

TRUE => "Mahal"

## 8. Table Partitioner
Dataset dibagi menjadi training set dan testing set untuk keperluan pemodelan machine learning.

Digunakan untuk membagi data menjadi dua bagian:

- Training set (misal 70%) → untuk melatih model

- Testing set (misal 30%) → untuk mengevaluasi model

Hasilnya muncul sebagai First Partition & Second Partition.

## 9. Number to String
Digunakan untuk mengubah tipe data numerik menjadi string apabila kolom tersebut seharusnya diperlakukan sebagai kategori atau label.

## 10. Decision Tree Learner
Node ini melatih model Decision Tree berdasarkan data training.

Tujuannya untuk mempelajari pola hubungan antara:

- Input → Tahun

- Output → Harga rata-rata

Model ini membuat pohon keputusan untuk prediksi selanjutnya.

## 11. Decision Tree Predictor
Model yang sudah dilatih diterapkan pada data testing untuk menghasilkan prediksi.

Node ini menggunakan model Decision Tree untuk memprediksi harga berdasarkan data pada testing set.

- Output:

Predicted value

(Kadang) confidence/probability

Node ini hanya memberikan prediksi, belum menghitung akurasi

## 12. Scorer
Evaluasi performa model dilakukan menggunakan Scorer untuk memperoleh metrik seperti confusion matrix dan akurasi.

Node ini membandingkan:

- Predicted value (hasil model)

- Actual value (harga asli)

- Output yang dihasilkan:

Confusion Matrix (untuk klasifikasi)

- Nilai benar / salah

- Performa prediksi

## INSIGHT
- Harga mobil berubah cukup jelas dari tahun ke tahun.
  
- Rata-rata harga per tahun menunjukkan pola tren tertentu.  

- Tahun produksi adalah faktor paling berpengaruh dalam model.  

- Model hanya bisa menangkap tren umum, bukan nilai harga detail.  

## INTERPRETASI
- Tahun bisa digunakan untuk membaca pola kenaikan/penurunan harga.  

- Namun tahun saja tidak cukup untuk memprediksi harga secara akurat karena harga mobil dipengaruhi juga oleh faktor lain (km, kondisi, mesin, fitur).  

- Model decision tree sederhana cocok untuk analisis tren, tetapi kurang kuat untuk prediksi harga presisi.  


