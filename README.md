# Jankenpon-CV
Klasifikasi gambar Gunting, Batu, Kertas dengan pendekatan classic machine learning tanpa melakukan ekstraksi fitur dan praproses.

## Dataset
Dataset didapat dari Drgfreeman di Kaggle https://www.kaggle.com/datasets/drgfreeman/rockpaperscissors dengan banyak data sebagai berikut:

| Jenis Gambar | Banyaknya |
| -- | -- |
| Batu | 726 |
| Gunting | 750 |
| Kertas | 712 |

Semua ukuran gambar sama yaitu 300x200 dengan format .png data juga dipisah menjadi data train dan data test dengan perbandingan 80:20.

## Seleksi Fitur
Fitur didapatkan dengan mengubah secara langsung per piksel sehingga didapatkan 300x200 = 60000 dan juga menggunakan format RGB dalam 1 piksel sehingga banyaknya fitur yang didapatkan adalah 60000 x 3 = 180000. Sehingga, dimensi dataframe menjadi (726+750+712)x60000 = 2118x60000.

Untuk mempercepat runtime, dilakukan seleksi fitur dengan Random Forest Feature Importance dengan membuang nilai importance = 0, sehingga menjadi 10144 fitur (tidak termasuk label/target).

## Model
Menggunakan model Multi Layer Perceptron dari Scikit Learn dengan menggunakan parameter default.

## Hasil
Akurasi Data Train (Cross-Val) = 0.642 <br>
Akurasi Data Test = 0.342

## Perbandingan dengan project yang lain
Tahapan kedua, yaitu melakukan ekstraksi fitur HOG (Histogram of Oriented Gradient) : https://github.com/Otniel113/Jankenpon-CV2 <br>
Tahapan ketiga, yaitu dengan menggunakan deep learning CNN : https://github.com/Otniel113/Jankenpon-CV3
