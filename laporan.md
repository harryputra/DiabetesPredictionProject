# **Laporan Proyek Machine Learning - Diabetes Prediction**

## **1. Pendahuluan**

### **1.1 Latar Belakang**
Diabetes adalah salah satu penyakit kronis yang memerlukan perhatian khusus karena dapat menyebabkan berbagai komplikasi serius, termasuk kerusakan organ seperti ginjal, mata, dan jantung. Deteksi dini diabetes dapat membantu mencegah komplikasi tersebut dan memungkinkan pengobatan yang lebih efektif.

Dalam proyek ini, digunakan dataset **Diabetes Prediction Dataset** dari Kaggle untuk membangun model machine learning yang dapat memprediksi kemungkinan seseorang menderita diabetes berdasarkan parameter medis mereka. Proyek ini bertujuan untuk membantu profesional kesehatan dalam membuat keputusan berbasis data.

Dataset ini dapat diakses di [Diabetes Prediction Dataset](https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset).

---

## **2. Business Understanding**

### **2.1 Pernyataan Masalah**
1. Bagaimana cara memprediksi kemungkinan seseorang menderita diabetes berdasarkan parameter medis seperti BMI, usia, dan riwayat kesehatan?
2. Parameter apa yang paling signifikan dalam menentukan risiko diabetes?

### **2.2 Tujuan Proyek**
1. Membangun model machine learning untuk memprediksi diabetes berdasarkan parameter medis pasien.
2. Mengevaluasi kinerja model menggunakan metrik seperti akurasi, precision, recall, dan F1-score.

### **2.3 Pernyataan Solusi**
- Algoritma **Logistic Regression** digunakan untuk memprediksi diabetes. Model ini dipilih karena sederhana, efektif untuk klasifikasi biner, dan mudah diinterpretasikan.
- Dataset akan diproses dengan teknik data preparation seperti encoding data kategorikal dan normalisasi data numerik untuk memastikan kualitas input model.

---

## **3. Data Understanding**

Dataset yang digunakan memiliki **100.000 sampel** dengan **9 fitur**. Berikut adalah deskripsi variabel dalam dataset:

| **Nama Variabel**       | **Deskripsi**                                                                 |
|--------------------------|-------------------------------------------------------------------------------|
| `gender`                | Jenis kelamin pasien (Male/Female).                                          |
| `age`                   | Usia pasien (numerik).                                                      |
| `hypertension`          | Riwayat hipertensi (0: Tidak, 1: Ya).                                       |
| `heart_disease`         | Riwayat penyakit jantung (0: Tidak, 1: Ya).                                 |
| `smoking_history`       | Riwayat merokok pasien (kategori seperti "never", "current", "former").     |
| `bmi`                   | Indeks massa tubuh pasien.                                                  |
| `HbA1c_level`           | Level hemoglobin A1c (%).                                                  |
| `blood_glucose_level`   | Level gula darah (mg/dL).                                                   |
| `diabetes`              | Variabel target (0: Tidak diabetes, 1: Diabetes).                          |

### **Visualisasi Data**
- **Distribusi Variabel Target (`diabetes`)**:
  Sebagian besar pasien dalam dataset tidak menderita diabetes.
- **Histogram Fitur Numerik**:
  Fitur numerik seperti `age`, `bmi`, `HbA1c_level`, dan `blood_glucose_level` menunjukkan distribusi yang bervariasi.

---

## **4. Data Preparation**

### **4.1 Langkah-Langkah Preprocessing**
1. **Encoding Data Kategorikal**:
   - Variabel `gender` dan `smoking_history` diubah menjadi nilai numerik menggunakan **Label Encoding**.
   - Contoh:
     - `gender`: Female = 0, Male = 1.
     - `smoking_history`: Dikodekan ke nilai numerik.

2. **Normalisasi Fitur Numerik**:
   - Variabel numerik seperti `age`, `bmi`, `HbA1c_level`, dan `blood_glucose_level` dinormalisasi menggunakan **StandardScaler** agar memiliki skala yang seimbang.

3. **Split Dataset**:
   - Dataset dibagi menjadi **80% training set** dan **20% testing set** untuk pelatihan dan evaluasi model.

---

## **5. Modeling**

### **5.1 Algoritma yang Digunakan**
**Logistic Regression** dipilih karena:
- Efektif untuk masalah klasifikasi biner seperti prediksi diabetes.
- Memiliki interpretasi yang sederhana untuk menjelaskan hubungan antara fitur dan prediksi.

### **5.2 Proses Training**
- Model dilatih menggunakan **training set**.
- Hyperparameter default digunakan untuk baseline model.

---

## **6. Evaluation**

### **6.1 Metrik Evaluasi**
Metrik evaluasi yang digunakan:
1. **Accuracy**: Mengukur persentase prediksi yang benar.
2. **Precision**: Proporsi prediksi positif yang benar.
3. **Recall**: Kemampuan model mendeteksi semua data positif.
4. **F1-Score**: Rata-rata harmonis antara precision dan recall.
5. **Confusion Matrix**: Menampilkan prediksi benar dan salah untuk setiap kelas.

### **6.2 Hasil Evaluasi**
- **Accuracy**: 85%.
- **Classification Report**:
  - Precision, recall, dan F1-score menunjukkan performa yang baik.
- **Confusion Matrix**:
  - Memvisualisasikan bahwa model mampu memprediksi mayoritas kelas dengan akurasi tinggi.

---

## **7. Kesimpulan**

Model Logistic Regression berhasil memprediksi kemungkinan diabetes dengan akurasi yang memadai. Model ini dapat digunakan untuk analisis risiko awal diabetes, namun terdapat peluang untuk meningkatkan performa dengan eksplorasi algoritma lain.

### **Rekomendasi**
1. Eksplorasi algoritma lebih kompleks seperti Random Forest atau Gradient Boosting.
2. Melakukan **hyperparameter tuning** pada Logistic Regression untuk meningkatkan akurasi.
3. Mengintegrasikan lebih banyak fitur medis untuk meningkatkan kualitas prediksi.

---

"""