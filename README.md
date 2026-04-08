# Prediksi_harga_rumah_portofolio
# Mini Proyek Regresi End-to-End: Prediksi Harga Rumah

## Pendahuluan
Proyek ini adalah implementasi end-to-end dari model regresi linear untuk memprediksi harga rumah berdasarkan berbagai fitur. Tujuan utama proyek ini adalah untuk mendemonstrasikan tahapan-tahapan umum dalam pembangunan model Machine Learning, mulai dari pemuatan data, pembersihan, rekayasa fitur, pelatihan model, evaluasi, hingga interpretasi hasil.

## Dataset
Dataset yang digunakan bernama `mini_project_regresi_rumah_bersih.csv`, yang berisi informasi tentang properti rumah, termasuk:
- `id`: ID unik rumah
- `luas_rumah`: Luas bangunan rumah
- `jumlah_kamar`: Jumlah kamar tidur
- `usia_rumah`: Usia rumah
- `jarak_pusat_kota`: Jarak rumah dari pusat kota
- `kondisi_renovasi`: Status renovasi rumah (ya/tidak)
- `harga`: Harga jual rumah (variabel target)

## Langkah-Langkah Proyek
Proyek ini dibagi menjadi beberapa tahapan utama:

1.  **Pemuatan Data (`LOAD DATASET`)**
    *   Membaca dataset dari file CSV ke dalam Pandas DataFrame.

2.  **Pembersihan Data (`CLEANING`)**
    *   Menghilangkan duplikasi data.
    *   Mengubah tipe data kolom numerik dan menangani nilai non-numerik (`coerce`).
    *   Mengisi nilai yang hilang (missing values) pada kolom numerik dengan median dan pada kolom kategorikal dengan modus (mode).

3.  **Rekayasa Fitur (`FEATURE ENGINEERING`)**
    *   Membuat fitur baru `luas_per_kamar` (`luas_rumah` / `jumlah_kamar`).
    *   Mengkodekan fitur kategorikal `kondisi_renovasi` menjadi numerik (`kondisi_renovasi_encoded`: 0 untuk 'tidak', 1 untuk 'ya').
    *   Menentukan fitur (`X`) dan variabel target (`y`).

4.  **Pelatihan Model (`TRAIN MODEL`)**
    *   Membagi data menjadi set pelatihan (training set) dan set pengujian (testing set) dengan rasio 80:20.
    *   Menggunakan model `LinearRegression` dari scikit-learn.
    *   Melatih model pada data pelatihan.

5.  **Evaluasi Model (`EVALUASI`)**
    *   Membuat prediksi pada data pengujian.
    *   Menghitung metrik evaluasi seperti:
        *   **MAE (Mean Absolute Error)**: 29113.83
        *   **MSE (Mean Squared Error)**: 1106869334.11
        *   **RMSE (Root Mean Squared Error)**: 33269.65
        *   **R² (R-squared)**: 0.9724
    *   Menganalisis residual dan kesalahan terbesar.

6.  **Interpretasi Hasil (`INTERPRETASI HASIL`)**
    *   Menganalisis intercept dan koefisien dari model regresi untuk memahami pengaruh setiap fitur terhadap harga rumah.
    *   **Koefisien Positif:** `luas_rumah`, `jumlah_kamar`, `luas_per_kamar` menunjukkan hubungan positif dengan harga.
    *   **Koefisien Negatif:** `usia_rumah` menunjukkan hubungan negatif dengan harga.
    *   **Temuan Tidak Intuitif:** Koefisien `jarak_pusat_kota` (`5571.20`) dan `kondisi_renovasi_encoded` (`-58509.13`) menunjukkan hasil yang berlawanan dengan intuisi umum. Ini memerlukan investigasi lebih lanjut, mungkin karena karakteristik spesifik dataset, ukuran sampel kecil, atau multikolinearitas.

7.  **Visualisasi Data**
    *   Memvisualisasikan hubungan antara `luas_rumah` dan `harga` menggunakan regplot untuk menunjukkan tren.

8.  **Penyimpanan Data Bersih**
    *   Menyimpan DataFrame yang telah dibersihkan dan direkayasa fitur ke file CSV baru di direktori `outputs`.

## Teknologi yang Digunakan
*   **Python**
*   **Pandas**: Untuk manipulasi dan analisis data.
*   **Scikit-learn**: Untuk pembangunan dan evaluasi model Machine Learning.
*   **Matplotlib & Seaborn**: Untuk visualisasi data.

## Cara Menjalankan
1.  Pastikan Anda memiliki Python dan library yang disebutkan di atas terinstal.
2.  Unduh file notebook (.ipynb) dan dataset (`mini_project_regresi_rumah_bersih.csv`).
3.  Jalankan notebook di lingkungan seperti Jupyter Notebook atau Google Colab.
4.  Ikuti langkah-langkah dalam notebook secara berurutan.

---
