# Perbandingan CatBoost vs SVM (RBF)  
## Studi Kasus: Klasifikasi Kualitas Udara Jakarta 2020

Analisis ini membandingkan dua algoritma populer—**CatBoost** dan **Support Vector Machine (RBF)**—dalam mengklasifikasikan kualitas udara Jakarta berdasarkan data SPKU tahun 2020.

---

## 🔍 Tujuan  
- Menerapkan dan membandingkan CatBoost vs SVM (RBF)  
- Mengevaluasi model dengan metrik: Accuracy, Precision, Recall, F1-score  
- Menginterpretasi confusion matrix untuk masing-masing model

---

## 📁 Dataset  
- Sumber: [satudata.jakarta.go.id](https://satudata.jakarta.go.id)  
- Parameter polusi harian dari beberapa stasiun di Jakarta sepanjang 2020  
- Label: 0 = “Baik”, 1 = “Tidak Baik”

---

## 📊 Langkah Analisis  
1. Eksplorasi & pembersihan data  
2. Preprocessing & label encoding  
3. Split data (Train/Test)  
4. Modeling menggunakan CatBoost & SVM (RBF)  
5. Evaluasi metrik & confusion matrix  
6. Interpretasi hasil & kesimpulan

---

## ✅ Hasil Evaluasi

| Metrik / Model          | CatBoost         | SVM (RBF)        |
|-------------------------|------------------|------------------|
| **Accuracy**            | 0.99             | 0.95             |
| **Precision (kelas 0)** | 0.96             | 0.82             |
| **Recall (kelas 0)**    | 0.97             | 0.97             |
| **F1-score (kelas 0)**  | 0.97             | 0.89             |
| **Precision (kelas 1)** | 0.99             | 0.99             |
| **Recall (kelas 1)**    | 0.99             | 0.94             |
| **F1-score (kelas 1)**  | 0.99             | 0.97             |
| **False Positives**     | 2                | 2                |
| **False Negatives**     | 3                | 17               |

---

## 🔍 Interpretasi Confusion Matrix

- **CatBoost** (`[[75,2],[3,286]]`):  
  - TN=75, FP=2, FN=3, TP=286  
  - Sangat sedikit kesalahan; andal dalam mendeteksi “Tidak Baik”.  
- **SVM (RBF)** (`[[75,2],[17,272]]`):  
  - TN=75, FP=2, FN=17, TP=272  
  - Recall kelas “Tidak Baik” lebih rendah karena banyak sampel kritis terlewat.

---

## 📝 Kesimpulan  
1. **CatBoost** unggul dengan metrik hampir sempurna di kedua kelas.  
2. **SVM (RBF)** solid tapi cenderung melewatkan kasus “Tidak Baik” (lebih banyak FN).  

## ⚙️ Rekomendasi  
- Pilih **CatBoost** untuk hasil klasifikasi yang lebih akurat dan stabil.  
- Jika menggunakan **SVM**, lakukan tuning `C` & `gamma` serta scaling fitur secara optimal.

---

## 💻 Tools & Library  
- Python, scikit-learn, CatBoost  
- Pandas, NumPy, Matplotlib

---

## 📬 Kontak  
Diskusi atau kolaborasi? Kunjungi profil LinkedIn saya!  
