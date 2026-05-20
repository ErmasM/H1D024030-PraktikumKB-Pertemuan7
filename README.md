# Laporan Praktikum Kecerdasan Buatan - Pertemuan 7

* **Nama:** Ermas Muhammad Syatafa
* **NIM:** H1D024030
* **Kelas:** Praktikum Kecerdasan Buatan (F)

## Deskripsi Tugas
Repositori ini dibuat untuk mengumpulkan tugas praktikum Pertemuan 7 mengenai implementasi Jaringan Syaraf Tiruan (JST) Klasifikasi menggunakan TensorFlow dan Keras. Studi kasus yang digunakan adalah klasifikasi spesies bunga Iris (Iris-setosa, Iris-versicolor, dan Iris-virginica) berdasarkan empat fitur morfologi: sepal length, sepal width, petal length, dan petal width.

## Arsitektur Model JST
Model dibangun menggunakan tipe tipe *Sequential* dengan susunan layer sebagai berikut:
1. **Input Layer:** Menerima input sesuai dengan jumlah fitur data (4 fitur).
2. **Dense Layer 1:** 1000 neuron dengan fungsi aktivasi ReLU.
3. **Dense Layer 2:** 500 neuron dengan fungsi aktivasi ReLU.
4. **Dense Layer 3:** 300 neuron dengan fungsi aktivasi ReLU.
5. **Output Layer:** 3 neuron dengan fungsi aktivasi Softmax untuk menghasilkan probabilitas masing-masing kelas.

Model dikompilasi menggunakan optimizer Adam dan loss function *Sparse Categorical Crossentropy*. Proses pelatihan dilakukan sebanyak 50 epoch dengan ukuran batch sebesar 32.

## Hasil Evaluasi dan Analisis

### 1. Grafik Akurasi dan Loss
<img width="885" height="547" alt="Cuplikan layar 2026-05-20 194153" src="https://github.com/user-attachments/assets/513919c5-8353-4033-b998-d531aa1e5923" />


Berdasarkan grafik riwayat pelatihan di atas, proses optimasi bobot model berjalan dengan sangat baik. Nilai loss (baik data training maupun validation) mengalami penurunan drastis pada beberapa epoch pertama dan stabil di bawah nilai 0.1. Sejalan dengan itu, tingkat akurasi meningkat pesat hingga mendekati nilai tertinggi secara konsisten. Karakteristik kurva ini menunjukkan model berhasil mempelajari pola data dengan optimal tanpa indikasi overfitting.

### 2. Confusion Matrix
<img width="755" height="585" alt="Cuplikan layar 2026-05-20 194205" src="https://github.com/user-attachments/assets/22ece562-f29e-43c2-971e-ad110342cd56" />

Pengujian model menggunakan data testing (rasio 80:20) menghasilkan performa klasifikasi yang sempurna. Berdasarkan confusion matrix di atas, seluruh sampel uji berhasil diklasifikasikan dengan tepat ke kelas aslinya tanpa ada kesalahan satu pun (*zero misclassification*):
* **Iris-setosa:** 10 sampel berhasil diprediksi benar.
* **Iris-versicolor:** 9 sampel berhasil diprediksi benar.
* **Iris-virginica:** 11 sampel berhasil diprediksi benar.

## Uji Coba Input Data Baru
Program ini menyediakan fungsi interaktif untuk memprediksi data baru melalui input terminal. Berikut adalah contoh hasil pengujian fungsi tersebut dengan memasukkan nilai acak:

```text
Masukkan sepal length: 2        
Masukkan sepal width: 3
Masukkan petal length: 4
Masukkan petal width: 5
1/1 ━━━━━━━━━━━━━━━━━━━━ 0s 72ms/step
Prediksi kelas: Iris-virginica
