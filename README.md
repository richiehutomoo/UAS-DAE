Laporan Singkat Workflow KNIME
## Richie C14250090 & David C14250084
Workflow ini dibuat untuk melakukan preprocessing data, analisis visual, serta pembuatan model machine learning berbasis Decision Tree. Tahapan yang dilakukan adalah sebagai berikut:

# 1. CSV Reader
Dataset diimpor menggunakan node CSV Reader untuk membaca file berformat .csv sebagai sumber data awal.

# 2. Column Filter
Node ini digunakan untuk memilih kolom-kolom yang diperlukan dan menghapus kolom yang tidak relevan sehingga data lebih fokus dan efisien diproses.

# 3. Row Filter
Baris data di filter berdasarkan kondisi tertentu untuk menyaring data sesuai kebutuhan analisis.

# 4. GroupBy
Data dikelompokkan berdasarkan kolom tertentu dan dilakukan agregasi seperti menghitung rata-rata, jumlah, atau nilai maksimum.

# 5. Column Renamer
Nama kolom diperbaiki agar lebih jelas, konsisten, dan mudah dipahami.

# 6. Visualisasi Data (Table, Bar Chart, Line Plot)
Table View digunakan untuk melihat data secara detail.
Bar Chart menampilkan distribusi data secara visual untuk mempermudah interpretasi.
Line Plot digunakan untuk melihat pola atau tren berdasarkan urutan data.

# 7. Rule Engine
Node ini digunakan untuk membuat kolom baru berdasarkan aturan logika tertentu, seperti klasifikasi threshold, pemberian kategori, atau label awal untuk model.

# 8. Table Partitioner
Dataset dibagi menjadi training set dan testing set untuk keperluan pemodelan machine learning.

# 9. Number to String
Digunakan untuk mengubah tipe data numerik menjadi string apabila kolom tersebut seharusnya diperlakukan sebagai kategori atau label.

# 10. Decision Tree Learner
Node ini melatih model Decision Tree berdasarkan data training.

# 11. Decision Tree Predictor
Model yang sudah dilatih diterapkan pada data testing untuk menghasilkan prediksi.

# 12. Scorer
Evaluasi performa model dilakukan menggunakan Scorer untuk memperoleh metrik seperti confusion matrix dan akurasi.

# INSIGHT
- Harga mobil berubah cukup jelas dari tahun ke tahun.  
- Rata-rata harga per tahun menunjukkan pola tren tertentu.  
- Tahun produksi adalah faktor paling berpengaruh dalam model.  
- Model hanya bisa menangkap tren umum, bukan nilai harga detail.  

INTERPRETASI
- Tahun bisa digunakan untuk membaca pola kenaikan/penurunan harga.  
- Namun tahun saja tidak cukup untuk memprediksi harga secara akurat karena harga mobil dipengaruhi juga oleh faktor lain (km, kondisi, mesin, fitur).  
- Model decision tree sederhana cocok untuk analisis tren, tetapi kurang kuat untuk prediksi harga presisi.  


