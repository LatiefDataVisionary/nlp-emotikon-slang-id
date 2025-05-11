**`sentimen-analisis-indonesia`**  
![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![NLP](https://img.shields.io/badge/NLP-Emotikon%20%26%20Slang-orange)

# Analisis Pengaruh Emotikon & Bahasa Informal pada Klasifikasi Sentimen Tweet Berbahasa Indonesia  
*Studi Kasus: Isu Sosial-Politik & Budaya di Platform Twitter*  

---

## 📜 Deskripsi Proyek  
Repositori ini merupakan implementasi penelitian tentang **pengaruh emotikon (😡, 🎉) dan bahasa informal (slang)** terhadap akurasi klasifikasi sentimen tweet berbahasa Indonesia. Fokus utama proyek ini adalah:  
1. Membangun *pipeline* pemrosesan teks khusus untuk bahasa informal Indonesia.  
2. Menganalisis dampak emotikon dan slang pada model *machine learning* dan *deep learning*.  
3. Menyediakan dataset berlabel dan kamus slang Indonesia yang siap digunakan untuk penelitian NLP lanjutan.  

**Contoh Kasus**:  
- 🚨 *"Gempa lagi, pemerintah tidur ya? 😡 #Gempa"* (Sentimen: Negatif)  
- ❤️ *"Layanan ojek online mantul bangeet! 👍 #Bucin"* (Sentimen: Positif)  

---

## 🎯 Fitur Utama  
- **🛠️ Preprocessing Khusus Bahasa Indonesia**  
  - Konversi emotikon → teks (😡 → `[marah]`).  
  - Translasi slang (*"wkwk"* → `tertawa`, *"bucin"* → `budak cinta`).  
- **🤖 Model Hybrid**  
  - Kombinasi *lexicon-based* (VaderSentiment) dan *deep learning* (LSTM + FastText).  
- **📊 Analisis Komparatif**  
  - Perbandingan akurasi model dengan/tanpa fitur emotikon & slang.  

---

## 📁 Struktur Repositori  
```bash
sentimen-analisis-indonesia/
├── data/                   # Dataset
│   ├── raw/                # Data mentah (CSV dari Twitter)
│   ├── processed/          # Data hasil preprocessing
│   └── labeled/            # Data berlabel manual
│
├── notebooks/              # Eksperimen Jupyter Notebook
│   ├── 1_data_collection.ipynb
│   ├── 2_preprocessing.ipynb
│   └── 3_model_training.ipynb
│
├── src/                    # Kode inti
│   ├── crawler.py          # Script crawling Twitter
│   ├── preprocessing.py    # Konversi emotikon & slang
│   └── model.py            # Arsitektur LSTM & SVM
│
├── results/                # Output analisis
│   ├── figures/            # Visualisasi (PNG/PDF)
│   └── models/             # Model terlatih (H5/PKL)
│
├── requirements.txt        Dependencies
└── README.md               Dokumentasi ini
```

---

## 🚀 Instalasi & Penggunaan  

### Prasyarat  
- Python 3.9+  
- Git  

### Langkah 1: Clone Repositori  
```bash
git clone https://github.com/username/sentimen-analisis-indonesia.git
cd sentimen-analisis-indonesia
```

### Langkah 2: Install Dependencies  
```bash
pip install -r requirements.txt
```

### Langkah 3: Jalankan Pipeline  
1. **Crawling Data** (Contoh: `#Bucin`):  
   ```python
   python src/crawler.py --query "#Bucin" --limit 1000
   ```
2. **Preprocessing**:  
   ```python
   python src/preprocessing.py --input data/raw/bucin.csv
   ```
3. **Training Model**:  
   ```python
   python src/model.py --data data/processed/cleaned_data.csv
   ```

---

## 📊 Hasil & Temuan  

### 1. Akurasi Model  
| **Model**         | **Akurasi (Tanpa Emotikon)** | **Akurasi (Dengan Emotikon)** |  
|-------------------|-----------------------------|------------------------------|  
| SVM               | 00%                        | 00% (+00%)                   |  
| LSTM              | 00%                        | **00% (+00%)**               |  

### 2. Kata Kunci Berpengaruh  
- Emotikon Paling Signifikan: ❤️ (Positif), 😡 (Negatif)  
- Slang Paling Umum: *"mantul"*, *"bucin"*, *"geming"*  

### 3. Visualisasi  
![Word Cloud Emotikon](results/figures/wordcloud_emoji.png)  
*Distribusi Emotikon dalam Dataset #Bucin*

---

## 🤝 Berkontribusi  
Kami terbuka untuk kontribusi! Berikut cara ikut serta:  
1. **Tambahkan Slang Baru**:  
   Edit `data/processed/slang_dictionary.json` dan buka *Pull Request*.  
2. **Laporkan Issue**:  
   Temukan bug? Buka [Issues](https://github.com/username/sentimen-analisis-indonesia/issues).  

**Panduan Kontribusi**:  
- Ikuti standar PEP8 untuk kode Python.  
- Dokumentasikan perubahan di `CHANGELOG.md`.  

---

## 📜 Lisensi  
Proyek ini dilisensikan di bawah **MIT License**. Lihat [LICENSE](LICENSE) untuk detail.

---

## 🙏 Ucapan Terima Kasih  
- Dosen Pembimbing: *Prof. Dr. Budi Santoso, M.Kom.*  
- Dataset: [Kaggle Indonesian Slang Words](https://www.kaggle.com/datasets/ilhamfp31/indonesian-slang-words)  
- Tools: `emoji`, `nltk`, `tweepy`  

---

**✨ Let's Revolutionize Indonesian NLP Together!**  
*"Dari tweet untuk Indonesia yang lebih memahami emosi digital warganya."*
