# Credit Risk Prediction  

## Project Overview  
Proyek ini bertujuan untuk meningkatkan akurasi penilaian dan pengelolaan risiko kredit menggunakan model machine learning. Dengan memanfaatkan data pinjaman historis, dua algoritma utama, yaitu Logistic Regression dan Random Forest, dikembangkan untuk memprediksi risiko kredit.  
Teknik **SMOTE (Synthetic Minority Oversampling Technique)** digunakan untuk menangani data tidak seimbang, sementara **hyperparameter tuning** dilakukan untuk mengoptimalkan performa model.  

## Dataset  
Dataset yang digunakan diambil dari Rakamin LMS, terdiri dari:  
- **466,285 rows** dan **75 columns**  
- Berisi data numerik dan kategorik terkait informasi pinjaman, seperti jumlah pinjaman, tingkat bunga, status pembayaran, serta karakteristik peminjam.  

## Project Workflow  

### 1. Data Understanding  
- Dataset berisi fitur-fitur utama seperti `loan_amnt`, `int_rate`, `loan_status`, `emp_length`, dll.  
- Beberapa fitur memiliki nilai kosong (*missing values*), yang ditangani dalam tahap berikutnya.  

### 2. Data Preprocessing & Feature Engineering  
- Dilakukan penghapusan fitur yang tidak relevan, seperti fitur dengan seluruh nilainya kosong atau informasi unik seperti `id` dan `url`.  
- Nilai kosong diisi menggunakan metode seperti imputasi rata-rata atau modus.  
- Fitur kategorik diubah menjadi bentuk numerik menggunakan teknik seperti one-hot encoding.  
- Data tidak seimbang pada target `loan_status` ditangani menggunakan **SMOTE** untuk memastikan model tidak bias terhadap kelas mayoritas.  

### 3. Exploratory Data Analysis (EDA)  
- Distribusi target `loan_status` dianalisis untuk memahami proporsi data positif dan negatif.  
- Hubungan antara fitur seperti `loan_amnt` dan `int_rate` dengan `loan_status` dianalisis untuk mencari pola.  

### 4. Data Modeling  
Model yang digunakan adalah:  
- **Logistic Regression**: Digunakan sebagai baseline karena interpretabilitasnya.  
- **Random Forest**: Dipilih karena kemampuannya menangkap pola data yang kompleks.  

#### Hyperparameter Tuning  
- Proses tuning dilakukan menggunakan **RandomizedSearchCV** untuk mengoptimalkan hyperparameter seperti jumlah estimator dan kedalaman pohon pada Random Forest.  

### 5. Model Evaluation  
Model dievaluasi menggunakan metrik:  
- **Accuracy**: Mengukur persentase prediksi yang benar.  
- **Precision**: Mengukur ketepatan prediksi positif.  
- **Recall**: Mengukur kemampuan model mengidentifikasi data positif.  
- **F1-Score**: Kombinasi precision dan recall untuk evaluasi keseluruhan.  

Hasil evaluasi menunjukkan bahwa Random Forest dengan tuning hyperparameter memberikan hasil terbaik dengan akurasi lebih dari 98%, sementara Logistic Regression mencapai akurasi 83%.  

## Setup Environment 
```
pip install -r requirements.txt
```
