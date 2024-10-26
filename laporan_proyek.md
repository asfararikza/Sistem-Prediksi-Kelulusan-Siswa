# Sistem Prediksi Kelulusan Siswa - Asfara Rikza

## Domain Proyek
Pendidikan memiliki peran krusial dalam meningkatkan kualitas sumber daya manusia dan memajukan suatu bangsa. Namun, tantangan besar yang dihadapi adalah tingginya angka siswa yang tidak lulus, yang mengancam pencapaian tujuan pendidikan nasional. Dalam konteks ini, kebutuhan akan informasi yang akurat untuk memahami faktor-faktor yang mempengaruhi kelulusan siswa sangat penting. Data statistik dari Kementerian Pendidikan dan Kebudayaan menunjukkan bahwa jumlah siswa putus sekolah di tingkat SMA/SMK semakin meningkat setiap tahunnya. Misalnya, di Jawa Barat, jumlah siswa putus sekolah pada tahun 2016/2017 mencapai 21.578 orang, dan meningkat menjadi 22.270 orang pada tahun 2017/2018.

Untuk mengatasi masalah ini, penggunaan teknik data mining menjadi relevan, karena dapat membantu mengidentifikasi pola dan faktor yang berkontribusi terhadap kelulusan siswa. Dengan memahami data dan informasi yang terkandung di dalamnya, institusi pendidikan dapat merumuskan strategi yang lebih efektif untuk meningkatkan tingkat kelulusan, yang pada akhirnya berkontribusi pada pembangunan masyarakat yang lebih baik

Referensi:
- [Penerapan Data Mining untuk Memprediksi Hasil Kelulusan Siswa Menggunakan Metode Naïve Bayes](https://journal.uc.ac.id/index.php/JUISI/article/view/1685)
- [APLIKASI DATA MINING UNTUK MENGHASILKAN POLA
KELULUSAN SISWA DENGAN METODE NAÏVE BAYES](https://d1wqtxts1xzle7.cloudfront.net/56132051/27-49-1-SM.pdf?1521729451=&response-content-disposition=inline%3B+filename%3DAPLIKASI_DATA_MINING_UNTUK_MENGHASILKAN.pdf&Expires=1729939655&Signature=UFmYn142dqQBXRjJjEPubT7NviNRtqRxEdoRQBlMu4WppiN4DPg-viKRi4MybB46xtPRPyTVQhukU3NfJD27AUUS1llNd1Tj7om3bbjFVjZD60XLf60Hw9VXdOIJY-ytvQJ0~AZm6MqZLONpc077Ts5TlWUB-pvmaJKtGWxFOTdggbCN--QofLW9HwrgaZHiimgloWkOl9VPiY6qhNqUFlz0DIWPwFv5LijTErO~nFyOr5OTvVI1nAxPfPHr9GgmwzCcapCKIpk06eKMvxkuxTCjdymSHASDDzWnqmUinZhy5Y2~wH1-4pFNkGJGgVAI-~DEouKunAA~w0EvC2tYbQ__&Key-Pair-Id=APKAJLOHF5GGSLRBV4ZA)
- [ANALISIS PREDIKSI KELULUSAN SISWA PKBM PAKET C DENGAN METODA ALGORITMA NAÏVE BEYES](https://ejournal.poltektedc.ac.id/index.php/tedc/article/view/13/22)

## Business Understanding

### Problem Statement
Berdasarkan data yang ada, banyak siswa yang tidak mencapai kelulusan pada tingkat SMA/SMK, yang dapat disebabkan oleh berbagai faktor, termasuk rendahnya nilai ujian dan kurangnya perhatian dari pihak sekolah. Oleh karena itu, perlu dilakukan langkah-langkah proaktif untuk mengidentifikasi siswa yang berisiko tidak lulus sebelum terlambat.

### Goals
1. Membangun sistem prediksi kelulusan siswa berdasarkan nilai ujian dan data terkait lainnya.
2. Mengidentifikasi siswa yang diprediksi tidak lulus, sehingga pihak sekolah dapat memberikan perhatian dan dukungan yang diperlukan untuk meningkatkan peluang kelulusan mereka.
3. Meningkatkan kualitas pendidikan di sekolah dengan memanfaatkan data dan analisis untuk mengambil keputusan yang lebih baik.

### Solution Statement
Untuk mencapai tujuan peningkatan kelulusan siswa, dua solusi berikut diusulkan:

1. **Pengembangan Model Prediksi dengan Algoritma SVM dan XGBoost**
   - Dua model prediksi akan dibangun menggunakan Support Vector Machine (SVM) dan XGBoost. Hasil akurasi dari masing-masing model akan dibandingkan, dan model dengan akurasi tertinggi akan dipilih untuk digunakan dalam sistem prediksi.

2. **Identifikasi Faktor yang Berpengaruh Terhadap Kelulusan Siswa**
   - Proyek ini akan mengidentifikasi faktor-faktor yang paling berpengaruh terhadap kelulusan siswa. Dengan memahami faktor-faktor ini, pihak sekolah dapat lebih fokus pada area yang memerlukan perhatian khusus, seperti nilai ujian atau kondisi sosial-ekonomi siswa.

Dengan menggunakan pendekatan ini, diharapkan sistem prediksi kelulusan siswa dapat memberikan informasi yang berguna bagi para pendidik dalam memberikan perhatian lebih terhadap siswa yang berisiko, serta membantu dalam memahami faktor-faktor kunci yang mempengaruhi keberhasilan pendidikan siswa.

## Data Understanding

Dataset yang digunakan dalam analisis ini adalah dataset nyata yang berisi nilai siswa dalam mata pelajaran Sejarah dan Geografi dari sebuah sekolah menengah umum di Aljazair. Dataset ini terdiri dari total 634 catatan, masing-masing mewakili kinerja akademis seorang siswa, bersama dengan berbagai fitur yang relevan.

Sumber dataset: [Students Annual Score in History Geography subject](https://www.kaggle.com/datasets/fundal/students-annual-score-in-history-geography-subject/data)

Dataset ini memiliki kolom-kolom sebagai berikut:

| Kolom          | Tipe Data |
|----------------|-----------|
| Gender         | object    |
| Test_01         | float64   |
| Exam_01        | float64   |
| Test_02         | float64   |
| Exam_02        | float64   |
| Test_03       | float64   |
| Exam_03        | float64   |
| Annual_Score   | float64   |
| Success        | int64     |

 Tipe data:
- **Gender**: Variabel kategorikal yang menunjukkan jenis kelamin siswa.
- **Nilai Ujian dan Tes**: Variabel kontinu yang mewakili nilai dari berbagai tes dan ujian.
- **Skor Tahunan**: Variabel kontinu yang mewakili kinerja keseluruhan siswa selama tahun ajaran.
- **Success**: Indikator biner (0 atau 1) yang menunjukkan apakah seorang siswa berhasil lulus atau tidak.

### Analisis Faktor Pengaruh Kelulusan Siswa
![Matriks Korelasi](https://raw.githubusercontent.com/asfararikza/Sistem-Prediksi-Kelulusan-Siswa/refs/heads/main/images/correlation%20matrix.png)  
Berdasarkan matriks korelasi, terlihat bahwa fitur yang paling berpengaruh dalam menentukan kelulusan siswa adalah nilai ujian dan skor tahunan. Hal ini menunjukkan bahwa nilai ujian memiliki peran yang lebih signifikan dibandingkan nilai tes dalam menilai hasil kelulusan siswa. Temuan ini menegaskan pentingnya nilai ujian sebagai indikator utama dalam evaluasi keberhasilan akademis.

## Data Preparation

Pada tahap **Data Preparation**, data dipersiapkan sebelum digunakan untuk pelatihan model. Beberapa langkah yang dilakukan dalam tahap ini meliputi:

1. **Penghapusan Fitur yang Tidak Diperlukan**: 
   Kolom yang tidak relevan, yaitu `Unnamed: 9`, dihapus dari DataFrame untuk memastikan hanya fitur yang diperlukan yang digunakan dalam analisis.

2. **Pemeriksaan Data Kosong (Null Values)**: 
   Data kosong diperiksa untuk memastikan tidak ada nilai yang hilang dalam dataset. Hasil pemeriksaan menunjukkan bahwa tidak ada data yang kosong pada setiap kolom, yaitu:
   - Gender: 0
   - Test_01: 0
   - Exam_01: 0
   - Test_02: 0
   - Exam_02: 0
   - Test_03: 0
   - Exam_03: 0
   - Annual_Score: 0
   - Success: 0

3. **Pemeriksaan Data Duplikat**: 
   Data duplikat diperiksa untuk menghindari pengaruh negatif terhadap model. Hasil pemeriksaan menunjukkan bahwa jumlah data duplikat adalah 0, yang berarti tidak ada entri yang sama dalam dataset.

4. **Penyesuaian Tipe Data**: 
   Tipe data untuk setiap fitur diperiksa dan disesuaikan jika diperlukan agar sesuai dengan format yang tepat untuk analisis lebih lanjut.

5. **Pembagian Data Uji dan Data Latih**: 
   Dataset dibagi menjadi fitur (X) dan target (y) di mana `X` berisi semua kolom kecuali kolom `Success`, dan `y` hanya berisi kolom `Success`. Data kemudian dibagi menjadi data latih dan data uji dengan proporsi 85% untuk data latih dan 15% untuk data uji. Hasil pembagian menunjukkan bahwa data latih terdiri dari sejumlah entri, sementara data uji berisi sisa entri.

## Modeling

Pada tahap **Modeling**, dua algoritma digunakan untuk memprediksi kelulusan siswa, yaitu **Support Vector Machine (SVM)** dan **XGBoost**. Kedua algoritma ini dibandingkan, dan model dengan akurasi tertinggi akan dipilih sebagai solusi terbaik.

### Algoritma yang Digunakan

1. **Support Vector Machine (SVM)**
   - **Kelebihan**:
     - SVM efektif pada data dengan dimensi yang tinggi dan performanya tetap baik walaupun jumlah fitur lebih banyak dari jumlah sampel.
     - SVM bekerja baik dengan margin yang jelas antara kelas-kelas dan dapat menghasilkan keputusan yang optimal karena mencari garis pemisah terbaik (hyperplane) untuk memaksimalkan margin.
   - **Kekurangan**:
     - SVM cenderung lambat pada dataset yang besar, terutama jika jumlah fitur dan sampel meningkat.
     - Tidak terlalu efektif pada data dengan noise yang tinggi karena bisa mengurangi akurasi dalam menentukan hyperplane terbaik.
   
2. **XGBoost**
   - **Kelebihan**:
     - XGBoost adalah algoritma yang sangat cepat dan efisien, yang secara khusus dioptimalkan untuk performa komputasi dan pemrosesan data dalam jumlah besar.
     - Memiliki kemampuan untuk mengatasi overfitting dan memberikan hasil yang akurat pada data yang kompleks karena menggunakan teknik boosting, yaitu memperbaiki kesalahan prediksi dari model sebelumnya.
   - **Kekurangan**:
     - Memiliki kompleksitas yang lebih tinggi, yang dapat menyebabkan waktu pemrosesan lebih lama jika model tidak diatur dengan baik.
     - XGBoost membutuhkan parameter yang cukup banyak untuk disesuaikan agar mencapai hasil optimal.

### Pemilihan Model Terbaik

Setelah menguji kedua algoritma pada dataset, model dengan akurasi tertinggi dipilih sebagai solusi terbaik. Alasan pemilihan ini adalah untuk memastikan prediksi yang akurat terhadap kelulusan siswa, sehingga guru dapat lebih awal mengidentifikasi siswa yang memerlukan perhatian khusus. 

## Evaluation

Evaluasi model dilakukan menggunakan beberapa metrik untuk mengukur kinerja dalam klasifikasi:

1. **Precision**  
   Precision mengukur akurasi prediksi positif model. Precision dihitung dengan rumus: jumlah True Positives dibagi dengan jumlah True Positives ditambah False Positives. Precision yang tinggi menunjukkan sedikit kesalahan pada prediksi positif dan penting dalam kasus di mana kesalahan pada prediksi positif dapat merugikan.

2. **Recall**  
   Recall menunjukkan seberapa baik model dalam menemukan semua contoh positif dalam data. Recall dihitung dengan rumus: jumlah True Positives dibagi dengan jumlah True Positives ditambah False Negatives. Nilai recall yang tinggi penting ketika tujuan utama adalah meminimalkan jumlah kasus positif yang tidak terdeteksi.

3. **F1-Score**  
   F1-Score adalah rata-rata harmonis dari precision dan recall. Rumusnya adalah 2 dikalikan dengan hasil perkalian antara precision dan recall, lalu dibagi dengan hasil penjumlahan antara precision dan recall. F1-Score berguna saat terdapat ketidakseimbangan data antara kelas positif dan negatif.

4. **Accuracy**  
   Accuracy mengukur persentase prediksi yang benar dari keseluruhan prediksi. Rumusnya adalah jumlah True Positives ditambah True Negatives dibagi dengan total jumlah sampel. Accuracy memberi gambaran umum performa model dalam keseluruhan data, namun tidak selalu cocok bila terdapat ketidakseimbangan antar kelas.

---

**Hasil Evaluasi Model**

- **Model SVM**  
   * Precision: 0.99
   * Recall: 0.98
   * F1-Score: 0.99
   * Accuracy: 0.99

- **Model XGBoost**  
   * Precision: 1.00
   * Recall: 1.00
   * F1-Score: 1.00
   * Accuracy: 1.00

Dari hasil evaluasi di atas, model XGBoost dipilih sebagai model terbaik karena mencapai akurasi sempurna (100%) dan memiliki nilai precision, recall, serta F1-Score yang lebih tinggi dibandingkan model SVM.







 