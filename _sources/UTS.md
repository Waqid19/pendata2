# Ujian Tengah Semester

## 1. Pendahuluan
Penelitian ini bertujuan untuk menganalisis tingkat kesuburan tanah berdasarkan parameter kimia dan fisik menggunakan metode **K-Nearest Neighbors (KNN)**.

Dataset terdiri dari beberapa fitur penting seperti:
- pH tanah
- Nitrogen (N)
- Fosfor (P)
- Kalium (K)
- C-organik
- KTK
- Kejenuhan basa
- Tekstur tanah
- Kadar air
- Bulk density

---

## 2. Data Understanding

Tahap data understanding dilakukan untuk memahami struktur dataset, jenis atribut, distribusi data, serta kualitas data sebelum proses preprocessing dan pemodelan dilakukan.

Dataset yang digunakan berisi beberapa parameter kimia dan fisik tanah yang berpengaruh terhadap tingkat kesuburan. Setiap baris data merepresentasikan satu sampel tanah dengan label kelas **Subur** atau **Tidak Subur**.

### Atribut Dataset:

- pH tanah  
- Nitrogen (N)  
- Fosfor (P)  
- Kalium (K)  
- C-organik  
- KTK  
- Kejenuhan basa  
- Tekstur tanah  
- Kadar air  
- Bulk density  
- Label kesuburan tanah

### Proses Data Understanding yang dilakukan:

- Melihat jumlah baris dan kolom dataset  
- Mengecek tipe data setiap atribut  
- Menampilkan beberapa data awal (preview dataset)  
- Mengecek missing value / data kosong  
- Melihat distribusi kelas target  
- Mengamati rentang nilai setiap fitur numerik

### Hasil Pengamatan:

- Dataset terdiri dari data numerik dan kategorikal  
- Tidak terdapat data kosong  
- Kelas target terdiri dari dua kategori, yaitu **Subur** dan **Tidak Subur**  
- Nilai fitur memiliki rentang yang berbeda sehingga perlu normalisasi

### Tampilan Dataset Awal

![Dataset Awal](/foto/1.png)
 - untuk data id role nya di ganti menjadi meta
 - untuk data label di ganti menjadi target 

## 3. Preprocessing Data

Tahapan preprocessing yang dilakukan:

- Normalisasi data numerik ke rentang **[0,1]**
- Transformasi variabel kategorikal (tekstur tanah) menggunakan **one-hot encoding**
- Pemisahan fitur dan label

### Isi Missing Values
![Normalisasi]/foto/(mising.png)

### Normalisai data
![Normalisasi](/foto/normalisasi.png)

### Hasil Preprocessing
![Preprocessing](/foto/hasil-nor.png)

---

## 4. Metode KNN

Model yang digunakan adalah **K-Nearest Neighbors (KNN)** dengan parameter:

- **K = 5**
- **Distance Metric = Euclidean**
- **Weight = Distance**

### Penjelasan:
- **K = 5** → Model melihat 5 tetangga terdekat  
- **Euclidean** → Menghitung jarak lurus antar data  
- **Distance Weight** → Tetangga yang lebih dekat lebih berpengaruh  

### Setting KNN
![KNN Setting](/foto/setingKNN.png)

---

## 5. Hasil Evaluasi

Evaluasi dilakukan menggunakan **Cross Validation**.

### Hasil Test & Score:
- Accuracy: **100%**
- Precision: **100%**
- Recall: **100%**
- F1-Score: **100%**

### Hasil Test & Score
![Test and Score](/foto/test_score.png)

---

## 6. Confusion Matrix

Confusion Matrix menunjukkan performa model dalam klasifikasi.

### Hasil:
- Subur → 100% 
- Tidak Subur → 100% 
- Tidak ada kesalahan klasifikasi

### Confusion Matrix
![Confusion Matrix](/foto/hsl_matrix.png)

---

## 7. Analisis

Hasil akurasi yang sangat tinggi menunjukkan bahwa:

- Data memiliki pola yang sangat jelas
- Setiap fitur memiliki batas nilai yang tegas antara kelas subur dan tidak subur

Fitur seperti:
- pH tanah
- N, P, K
- C-organik
- KTK
- Kadar air
- Bulk density

memiliki pengaruh langsung terhadap kesuburan tanah.

Namun, hasil ini juga mengindikasikan bahwa:
- Dataset kemungkinan terlalu ideal (tidak ada noise)
- Label kemungkinan dibuat berdasarkan aturan tertentu (rule-based)

---

## 8. Kesimpulan

Dari hasil analisis data sudah valid antara hasil matrixconfusion dengan yang ada pada soal dimana pada soal itu yang subur ada 1000 (50%) sampel dan yang tidak subur itu ada 1000 (50%) sampel dengan total 2000 sampel.

### Target pada soal
![Target](/foto/target.png)

### Hasil Analisis
![Analisis](/foto/hsl_matrix.png)

