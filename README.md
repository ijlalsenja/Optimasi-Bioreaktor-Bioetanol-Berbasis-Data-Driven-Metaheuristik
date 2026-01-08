# Optimasi Bioreaktor Bioetanol Berbasis Data-Driven & Metaheuristik

## Ringkasan Proyek
Proyek ini bertujuan untuk mengoptimalkan kondisi operasi bioreaktor fermentasi bioetanol pada Pabrik Bioenergi TIP dengan pendekatan **Data-Driven Modeling** dan **Metaheuristic Optimization**. Data historis operasional digunakan untuk membangun model surrogate berbasis Machine Learning yang mampu memprediksi **konsentrasi etanol (yield)** dan **konsumsi energi**.  
Selanjutnya, empat algoritma metaheuristik (GA, PSO, GWO, dan ACO) diterapkan untuk menentukan kombinasi variabel operasi optimal yang menyeimbangkan produktivitas dan efisiensi energi.

Hasil utama menunjukkan bahwa pendekatan ini mampu memberikan rekomendasi set-point operasi yang lebih optimal dibandingkan metode trial-and-error konvensional, serta mengidentifikasi algoritma optimasi yang paling stabil dan efisien untuk diterapkan pada sistem industri.

---

## Pendahuluan dan Latar Belakang Industri
Industri bioenergi, khususnya bioetanol, menghadapi tantangan besar dalam mengoptimalkan proses fermentasi akibat karakteristik proses yang **nonlinier**, **kompleks**, dan **bersifat black-box**. Variabel seperti suhu, pH, waktu fermentasi, konsentrasi substrat, dan kecepatan agitasi saling berinteraksi dan memengaruhi kinerja proses.

Selain itu, terdapat **trade-off** antara peningkatan yield bioetanol dan konsumsi energi. Kondisi operasi yang meningkatkan yield sering kali berdampak pada peningkatan energi yang signifikan. Oleh karena itu, dibutuhkan pendekatan berbasis data dan optimasi cerdas untuk mendukung pengambilan keputusan operasional yang lebih presisi dan efisien.

---

## Analisis Data (Exploratory Data Analysis – EDA)
Tahap EDA dilakukan terhadap 2.000 data historis operasional bioreaktor. Analisis meliputi:
- Distribusi data menggunakan histogram dan boxplot
- Hubungan antar variabel melalui scatter plot multivariat
- Korelasi antar variabel input dan output menggunakan correlation matrix

Hasil EDA menunjukkan adanya hubungan nonlinier yang kuat antara variabel suhu, waktu fermentasi, dan konsentrasi substrat terhadap yield etanol. Selain itu, konsumsi energi meningkat signifikan pada suhu dan kecepatan agitasi yang tinggi, yang menegaskan adanya trade-off antara produktivitas dan efisiensi energi.

---

## Pemodelan Machine Learning dan Validasi
Untuk menggantikan model kinetika yang tidak tersedia, digunakan pendekatan **surrogate modeling** berbasis Machine Learning. Lima algoritma regresi yang diuji adalah:
1. Linear Regression  
2. Random Forest Regressor  
3. Support Vector Regressor (SVR)  
4. Gradient Boosting Regressor  
5. K-Nearest Neighbors Regressor (KNN)  

Dataset dibagi menjadi data latih dan data uji. Evaluasi performa dilakukan menggunakan metrik **RMSE** dan **R² Score**.  
Model terbaik berdasarkan performa prediksi kemudian dipilih untuk memodelkan:
- Ethanol Yield (maksimisasi)
- Energy Consumption (minimisasi)

Model terbaik inilah yang digunakan sebagai fungsi prediksi pada tahap optimasi metaheuristik.

---

## Optimasi Metaheuristik dan Perbandingan Algoritma
Tahap optimasi dilakukan menggunakan empat algoritma metaheuristik:
- Genetic Algorithm (GA)
- Particle Swarm Optimization (PSO)
- Grey Wolf Optimizer (GWO)
- Ant Colony Optimization (ACO)

Permasalahan multi-objective disederhanakan menjadi fungsi tujuan tunggal menggunakan metode pembobotan:

Setiap algoritma dievaluasi berdasarkan:
- Nilai fitness akhir
- Grafik konvergensi
- Stabilitas solusi
- Waktu komputasi

Hasil perbandingan menunjukkan perbedaan karakteristik tiap algoritma, di mana beberapa algoritma unggul dalam kecepatan konvergensi, sementara yang lain lebih stabil dalam menemukan solusi optimal global.

---

## Pembahasan Hasil dan Implikasi Industri
Hasil optimasi menunjukkan bahwa pendekatan metaheuristik berbasis surrogate model mampu memberikan rekomendasi kondisi operasi yang secara signifikan meningkatkan yield bioetanol dengan kenaikan konsumsi energi yang masih terkendali.

Dari sudut pandang industri, hasil ini dapat dimanfaatkan sebagai dasar penentuan set-point operasi bioreaktor yang lebih optimal, konsisten, dan berbasis data. Implementasi pendekatan ini berpotensi mengurangi biaya operasional sekaligus meningkatkan produktivitas pabrik bioenergi.

---

## Rekomendasi Operasi Optimal
Berdasarkan algoritma terbaik hasil optimasi, direkomendasikan satu set parameter operasi optimal sebagai berikut:

- **Temperature (T)** : ± XX °C  
- **pH** : ± XX  
- **Fermentation Time (t)** : ± XX jam  
- **Substrate Concentration (S)** : ± XX g/L  
- **Agitation Speed (RPM)** : ± XX rpm  

Nilai numerik di atas diperoleh langsung dari hasil optimasi dan dapat dijadikan acuan awal untuk pengaturan operasi bioreaktor.

---

## Kesimpulan Manajerial
Dari perspektif pengambilan keputusan bisnis, proyek ini menunjukkan bahwa:
1. **Peningkatan produktivitas** (yield bioetanol) dapat dicapai secara kuantitatif tanpa peningkatan konsumsi energi yang proporsional, berkat optimasi berbasis data.
2. Algoritma metaheuristik terbaik berdasarkan stabilitas, fitness, dan waktu komputasi direkomendasikan untuk diintegrasikan ke dalam sistem kontrol dan pengambilan keputusan operasional pabrik.
3. Secara strategis, hasil optimasi ini dapat diterapkan pada skala industri dengan langkah awal berupa implementasi decision-support system berbasis Machine Learning dan optimasi metaheuristik untuk mendukung operasi berkelanjutan dan efisien.

---

## Reproducibility
Seluruh proses komputasi (EDA, Modeling, dan Optimasi) dikerjakan menggunakan Python dan dapat dijalankan ulang melalui Google Colab pada tautan berikut:

🔗 **Google Colab Notebook**:  
[https://link-google-colab-anda-di-sini]

---

## Penutup
Pendekatan Data-Driven dan Metaheuristik yang diterapkan dalam proyek ini membuktikan bahwa transformasi digital dalam pengelolaan proses fermentasi bioetanol sangat memungkinkan dan memberikan manfaat nyata bagi industri bioenergi.
