# Laporan Singkat Workflow KNIME
## Richie C14250090 & David C14250084

Workflow ini dibuat untuk melakukan preprocessing data, analisis visual, perbandingan antar variabel, serta pembuatan model machine learning berbasis Decision Tree. Tahapan yang dilakukan adalah sebagai berikut:

---

## 1. CSV Reader
Dataset diimpor menggunakan node CSV Reader untuk membaca file berformat `.csv` sebagai sumber data awal.
Output: tabel mentah yang digunakan sebagai input workflow.

---

## 2. Column Filter
Memilih kolom yang diperlukan dan menghapus kolom tidak relevan.
Kolom yang dipilih:
- Tahun
- Harga
- CC
- HP

Tujuan: fokus pada variabel penting.

---

## 3. Row Filter
Memfilter baris berdasarkan kondisi tertentu, yaitu tahun 1998–2004.

---

## 4. GroupBy
Mengelompokkan data berdasarkan Tahun dan menghitung:
- Rata-rata harga per tahun
- Rata-rata HP per CC
- Rata-rata HP per tahun

Output: satu baris per tahun dan per CC.

---

## 5. Column Renamer
Memperjelas nama kolom agar lebih konsisten.

---

## 6. Visualisasi Data
Menggunakan:
- Table View
- Bar Chart
- Line Plot  
Untuk melihat pola, distribusi, dan tren harga mobil.

---

## 7. Rule Engine
Membuat kategori harga:

Harga rata-rata <= 10000 => "Murah"

Harga rata-rata <= 15000 => "Sedang"

TRUE => "Mahal"


---

## 8. Table Partitioner
Membagi dataset menjadi:
- 70% Training Set
- 30% Testing Set

---

## 9. Number to String
Konversi tipe data numerik menjadi string untuk label klasifikasi.

---

## 10. Decision Tree Learner
Melatih model berdasarkan:
- Input: Tahun
- Output: Harga rata-rata

---

## 11. Decision Tree Predictor
Memprediksi harga berdasarkan model.

Output:
- Predicted value
- Confidence (opsional)

---

## 12. Scorer
Evaluasi model dengan:
- Confusion Matrix
- Akurasi prediksi

---

# 13. Comparison & Visualisasi Tambahan

## a. CC vs Mean HP
Perbandingan rata-rata HP berdasarkan kapasitas mesin (CC).

**Visualisasi:**

<img src="https://github.com/richiehutomoo/UAS-DAE/blob/main/CC%20VS%20MEAN%20HP.png" width="700" height="400">

---

## b. Harga rata-rata mobil Corolla (1998–2004)
Tren harga rata-rata per tahun menggunakan Line Plot / Bar Chart.

**Visualisasi:**
<img src="https://github.com/richiehutomoo/UAS-DAE/blob/52fbbc3936d7c372c75f3dc1db571cb18b67b695/Harga%20rata-rata%20mobil%20Corolla%20dari%20tahun%201998-2004.png" width="700" height="400">

---

## c. Tahun vs Rata-rata HP  
Slot untuk chart ketiga.

**Visualisasi (silakan upload chart):**

<img src="" width="700" height="400">

---

# INSIGHT
- Harga mobil berubah cukup signifikan per tahun.
- Rata-rata harga menunjukkan tren naik dari 1998–2004.
- HP dan CC menunjukkan hubungan kuat.
- Tahun produksi memengaruhi performa (HP) dan harga.
- Decision Tree menangkap tren, bukan prediksi detail.

---

# INTERPRETASI
- Tahun bisa digunakan untuk membaca pola harga, namun tidak cukup untuk prediksi akurat.
- Faktor lain seperti kilometer, kondisi, dan fitur sangat berpengaruh.
- Comparison analysis memberi pemahaman mendalam terhadap hubungan antar variabel.
- Decision Tree cocok untuk insight sederhana namun kurang presisi untuk prediksi harga real.

---

# Struktur Folder (Rekomendasi)

---

## 8. Table Partitioner
Membagi dataset menjadi:
- 70% Training Set
- 30% Testing Set

---

## 9. Number to String
Konversi tipe data numerik menjadi string untuk label klasifikasi.

---

## 10. Decision Tree Learner
Melatih model berdasarkan:
- Input: Tahun
- Output: Harga rata-rata

---

## 11. Decision Tree Predictor
Memprediksi harga berdasarkan model.

Output:
- Predicted value
- Confidence (opsional)

---

## 12. Scorer
Evaluasi model dengan:
- Confusion Matrix
- Akurasi prediksi

---

# 13. Comparison & Visualisasi Tambahan

## a. CC vs Mean HP
Perbandingan rata-rata HP berdasarkan kapasitas mesin (CC).

**Visualisasi:**

*(upload gambar ke folder repo dan ganti path ini)*  
`![CC vs Mean HP](images/cc_vs_hp.png)`

---

## b. Harga rata-rata mobil Corolla (1998–2004)
Tren harga rata-rata per tahun menggunakan Line Plot / Bar Chart.

**Visualisasi:**

*(upload grafik ke folder repo dan ganti path ini)*  
`![Harga rata-rata](images/harga_rerata_1998_2004.png)`

---

## c. Tahun vs Rata-rata HP  
Slot untuk chart ketiga.

**Visualisasi (silakan upload chart):**

`![Rata-rata HP per Tahun](images/hp_per_tahun.png)`

---

# INSIGHT
- Harga mobil berubah cukup signifikan per tahun.
- Rata-rata harga menunjukkan tren naik dari 1998–2004.
- HP dan CC menunjukkan hubungan kuat.
- Tahun produksi memengaruhi performa (HP) dan harga.
- Decision Tree menangkap tren, bukan prediksi detail.

---

# INTERPRETASI
- Tahun bisa digunakan untuk membaca pola harga, namun tidak cukup untuk prediksi akurat.
- Faktor lain seperti kilometer, kondisi, dan fitur sangat berpengaruh.
- Comparison analysis memberi pemahaman mendalam terhadap hubungan antar variabel.
- Decision Tree cocok untuk insight sederhana namun kurang presisi untuk prediksi harga real.

---
