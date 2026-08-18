# 🌾 Klasifikasi Penyakit Daun Padi dengan Machine Learning

## 📌 Deskripsi Proyek
Penyakit daun padi seperti *Blast*, *Blight*, dan *Tungro* merupakan ancaman patologis serius yang dapat mereduksi kuantitas hasil panen dan mengancam ketahanan pangan. Deteksi penyakit secara manual melalui pengamatan visual rentan terhadap subjektivitas dan membutuhkan waktu yang lama. 

Penelitian Skripsi ini bertujuan untuk mengembangkan pemodelan klasifikasi penyakit daun padi menggunakan pendekatan *Machine Learning*. Pendekatan yang diusulkan mampu memetakan batas keputusan secara presisi dan menghasilkan model dengan kompleksitas komputasi yang lebih ringan tanpa memerlukan ekstraksi tekstur yang rumit. Luaran dari proyek ini diharapkan dapat diimplementasikan sebagai instrumen pendukung keputusan bagi para petani untuk mendeteksi penyakit sejak dini dan meminimalisir penggunaan pestisida yang tidak perlu.

## 🔬 Metodologi
Proyek ini mengusulkan alur pemrosesan citra dan klasifikasi dengan tahapan sebagai berikut:
1. **Prapemrosesan Citra:** Melakukan *resize* dan penyesuaian format citra.
2. **Ekstraksi Fitur:**
   * **Fitur Warna (HSV):** Mengekstrak histogram warna *Hue, Saturation*, dan *Value*.
   * **Fitur Bentuk (Shape):** Menggunakan teknik *Global Binary Thresholding* untuk mengekstrak area dan perimeter kontur daun yang terinfeksi.
3. **Normalisasi Data:** Integrasi teknik normalisasi (*Standard Scaler*) untuk mencegah bias komputasi antarfitur.
4. **Penyeimbangan Kelas (Data Balancing):** Implementasi skenario *Hybrid Sampling* (*Random OverSampler* & *Random UnderSampler*) melalui *Pipeline* untuk mengevaluasi stabilitas model terhadap ketimpangan jumlah data antar kelas.

## 🤖 Algoritma yang Dievaluasi
Pengujian komparatif dilakukan menggunakan tiga algoritma *Machine Learning* konvensional pada variasi volume dataset (200, 350, dan 500 citra):
* **Random Forest (RF)**
* **Support Vector Machine (SVM)**
* **K-Nearest Neighbors (KNN)**

## 📊 Hasil Pengujian
Berdasarkan hasil evaluasi, algoritma **Random Forest (RF)** mencatatkan kinerja klasifikasi yang paling optimal. Pada pengujian dengan skenario *balancing* bervolume **500 citra**, Random Forest berhasil mencapai tingkat **akurasi sebesar 98.00%**, mengungguli algoritma SVM dan KNN.

## 🛠️ Teknologi & Pustaka
Proyek ini dibangun menggunakan bahasa pemrograman Python dengan memanfaatkan pustaka berikut:
* **OpenCV:** Prapemrosesan dan ekstraksi fitur citra (Warna HSV & Bentuk).
* **Scikit-Learn:** Pelatihan model ML, *StandardScaler*, dan metrik evaluasi (Akurasi, Presisi, *Recall*, F1-Score).
* **Imbalanced-Learn (imblearn):** *Pipeline* untuk penyeimbangan data (Oversampling & Undersampling).
* **Matplotlib & Seaborn:** Visualisasi *Confusion Matrix* dan representasi transformasi citra.
* **Numpy & Pandas:** Manipulasi dan komputasi array.
