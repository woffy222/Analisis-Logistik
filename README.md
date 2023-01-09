# Analisis Calon Pembeli Mobil menggunakan Logistik Regresi - Mohammad Rafdi
## Domain Project
Mobil merupakan sebuah kendaraan beroda 4 yang umumnya digunakan untuk melakukan sebuah perjalanan jarak jauh. Perkembangan mobil sudah sangat berkembang.
Mobil dapat dibagi menjadi 2 kelompok berdasarkan bahan bakar, yaitu bahan bakar bensin dan bahan bakar listrik. Kepemilikan mobil biasaya didasari oleh kebutuhan.
Kebutuhan itu juga dipengaruhi oleh beberapa faktor seperti usia, status perkawinan dan penghasilan. Beberapa faktor tersebut bisa saja mempengaruhi kepemilikan mobil.
terkadang memiliki 1 mobil saja tidak cukup dan harus memiliki 2 buah mobil.

Karena hal tersebut permasalahan tersebut penulis ingin melakukan analisis calon pembeli mobil apakah mereka sudah mempunyai mobil atau belum sehingga akan
menambah jumlah kepemilikan mobil.

## Business Understanding
Penjual mobil bisa menawarkan produknya kepada orang yang memiliki kriteria yang sangat membutuhkan mobil sehingga nilai penjualan akan meningkat.

### Problem Statement
- Bagaimana cara menentukan menentukan nilai kriteria pelanggan yang membutuhkan mobil?

### Goal
- melakukan pemodelan untuk menentukan nulai kriteria pelanggan

## Data Understanding
Data yang digunakan adalah [Data Calon Pembeli Mobil](http://buku.dioskurn.com/buku1/ch5/)

Keterangan pada dataset:
- Usia
- Status (0 = Singel, 1 = Menikah, 2 = Janda/Duda)
- Kelamin (0 = Pria, 1 = Perempuan)
- Memiliki Mobil
- Penghasilan
- Beli Mobil (0 = tidak, 1 = iya)

Tampilan dari dataset

| Usia | Status | Kelamin | Memiliki Mobil | Penghasilan | Beli Mobil |
|------|--------|---------|----------------|-------------|------------|
| 32   | 1      | 0       | 0              | 240         | 1          |
| 49   | 2      | 1       | 1              | 100         | 0          |
| 52   | 1      | 0       | 2              | 250         | 1          |
| 26   | 2      | 1       | 1              | 130         | 0          |

Tampilan dari statistik deskripsi dataset

|       | Usia      | Status   | Kelamin  | Memiliki Mobil | Penghasilan | Beli Mobil |
|-------|-----------|----------|----------|----------------|-------------|------------|
| Count | 1000      | 1000     | 1000     | 1000           | 1000        | 1000       |
| mean  | 43.532000 | 1.469000 | 0.481000 |        0.95200 | 270.09000   | 0.633000   |
| min   | 24        | 0        | 0        | 0              | 95          | 0          |
| max   | 164       | 3        | 1        | 4              | 490         | 1          |


Hasil analisis:
- Terdapat 1000 data
- Terdapat umur manusia >100 tahun sehingga kita perlu memperbaikinya
- Usia rata-rata seluruh data set adalah 43.5

## Data Preperation
Teknik data preeration adalah:
- Membatasi usia yaitu 100 tahun
- Melakukan train split 0.8 untuk train dan 0.2 untuk test

## Modeling
Model yang digunakan adalah logistik regresi untuk menentukan siapa yang akan membeli mobil atau tidak. Logistik Regresi merupakan sebuah algoritma classification
Logistik regresi adalah salah satu teknik analisis statistik yang digunakan untuk memprediksi kemungkinan terjadinya suatu kejadian berdasarkan data masa lalu. 
Dalam logistik regresi, kita mencoba untuk memprediksi kemungkinan terjadinya suatu kejadian dalam bentuk 0 atau 1 (berhasil atau tidak)

## Evaluasi 
### Confusion matrix 
Confusion matrix adalah salah satu metode yang digunakan untuk mengevaluasi akurasi suatu model pembelajaran mesin (machine learning). 
Confusion matrix merupakan tabel yang menggambarkan jumlah prediksi yang benar dan salah yang dilakukan oleh suatu model pembelajaran mesin.
Confusion matrix biasanya digunakan untuk mengevaluasi model yang digunakan untuk memprediksi kelas suatu objek.

### Precision
Precisiion adalah seberapa tepat suatu model pembelajaran mesin (machine learning) dapat memprediksi kelas suatu objek. 
Precsisi dapat diukur dengan menggunakan nilai True Positive (TP) dan False Positive (FP). 
True Positive adalah jumlah prediksi yang benar dari kelas positif (misalnya, jumlah pasien yang terdiagnosis positif untuk penyakit dan ternyata memang terkena penyakit).
False Positive adalah jumlah prediksi yang salah dari kelas positif (misalnya,
jumlah pasien yang terdiagnosis positif untuk penyakit tapi ternyata tidak terkena penyakit).

Precision dapat dihitung dengan menggunakan rumus:

Precision = True Positive / (True Positive + False Positive)

Nilai precision yang tinggi menunjukkan bahwa model tersebut memiliki tingkat akurasi yang tinggi dalam memprediksi kelas positif. 
Sebaliknya, nilai precision yang rendah menunjukkan bahwa model tersebut memiliki tingkat akurasi yang rendah dalam memprediksi kelas positif.

### AUC
Area under curve (AUC) adalah sebuah ukuran yang digunakan untuk mengevaluasi kinerja suatu model pembelajaran mesin (machine learning) yang digunakan untuk memprediksi kelas suatu objek.
AUC dihitung dengan menghitung luas di bawah kurva receiver operating characteristic (ROC).
ROC curve adalah grafik yang menggambarkan hubungan antara tingkat true positive rate (sensitivity) dan false positive rate (1 - specificity) pada berbagai tingkat threshold.

Nilai AUC yang mendekati 1 menunjukkan bahwa model tersebut memiliki kinerja yang baik dalam memprediksi kelas objek, 
sedangkan nilai AUC yang mendekati 0 menunjukkan bahwa model tersebut memiliki kinerja yang buruk dalam memprediksi kelas objek. 
AUC dapat digunakan untuk membandingkan kinerja beberapa model pembelajaran mesin yang berbeda untuk memprediksi kelas suatu objek.

## Kesimpulan
Setelah melakukan modeling didapatkan hasil evaluasi yaitu nilai akurasi adalah 95%, nilai Presisi adalah 97%, nilai AUC adalah 95% karena memiliki score evaluasi yang tinggi
maka model logistik regresi cocok dengan dataset
