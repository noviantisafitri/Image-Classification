# Plant Village Image Classification

## Deskripsi Proyek
Proyek ini bertujuan untuk membangun model klasifikasi gambar menggunakan Convolutional Neural Network (CNN) untuk mendeteksi penyakit pada tanaman kentang. Dataset yang digunakan adalah **Plant Village**, yang diunduh dari Kaggle. Model dikembangkan menggunakan TensorFlow dan dievaluasi berdasarkan akurasi klasifikasinya.

## Informasi Pengembang
- **Nama:** Novianti Safitri  
- **Email:** noviantis112@gmail.com  
- **ID Dicoding:** novianti_safitri  

## Teknologi yang Digunakan
- Python
- TensorFlow
- TensorFlow.js
- Google Colab
- Kaggle API
- Matplotlib
- Pandas
- NumPy
- Zipfile
- Pathlib

## Struktur Direktori
```
├── dataset
│   ├── PlantVillage
│   ├── PotatoDataset
├── saved_model
├── tflite
│   ├── model.tflite
│   ├── label.txt
├── tfjs_model
├── requirements.txt
├── main.ipynb (notebook utama proyek)
```

## Cara Menggunakan Proyek
### 1. Instalasi Dependensi
Pastikan untuk menginstal semua dependensi sebelum menjalankan proyek.
```sh
pip install -r requirements.txt
```

### 2. Unduh Dataset dari Kaggle
1. **Upload `kaggle.json` ke Google Colab**
2. **Jalankan perintah berikut untuk mengunduh dataset:**
   ```sh
   kaggle datasets download -d arjuntejaswi/plant-village
   unzip plant-village.zip -d dataset
   ```

### 3. Persiapan Dataset
- Dataset akan diekstrak ke dalam folder `dataset/PlantVillage`.
- Hanya gambar tanaman kentang yang akan dipilih dan dipindahkan ke `PotatoDataset`.

### 4. Preprocessing dan Augmentasi Data
- Data akan diubah ke ukuran `224x224` piksel.
- Augmentasi dilakukan dengan `RandomFlip` dan `RandomRotation`.
- Dataset dibagi menjadi **training (80%)**, **validation (10%)**, dan **testing (10%)**.

### 5. Training Model
- Model menggunakan **CNN** dengan 3 lapisan **Conv2D** dan **MaxPooling2D**.
- **Early Stopping** dan **ReduceLROnPlateau** digunakan untuk menghindari overfitting.
- Model dilatih selama **20 epoch** dengan optimasi **Adam** dan **Sparse Categorical Crossentropy** sebagai loss function.

### 6. Evaluasi Model
- Model diuji pada training dan testing dataset.
- Grafik akurasi dan loss ditampilkan untuk melihat performa model.

### 7. Konversi Model
Model yang telah dilatih dikonversi ke beberapa format untuk deployment:
- **SavedModel (TensorFlow format)**
- **TensorFlow Lite (TFLite format)**
- **TensorFlow.js (TFJS format)**

## Hasil Evaluasi
- **Akurasi Training:** 98.61%  
- **Akurasi Testing:** 96.48%  

## Catatan Tambahan
- Jika menggunakan Google Colab, pastikan sesi tidak timeout saat pelatihan model.
- Dataset besar bisa menyebabkan keterbatasan memori. Gunakan **batch size** yang sesuai.
