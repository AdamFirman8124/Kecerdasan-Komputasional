# Rencana Tugas Kelompok

## Topik

**Comparative Performance of Decision Tree, Support Vector Machine, and Artificial Neural Network Under Severe Concept Drift on Streaming Data**

## Definisi operasional yang disarankan

Penelitian membandingkan kemampuan tiga keluarga model—Decision Tree (DT), Support Vector Machine (SVM), dan Artificial Neural Network (ANN)—untuk mempertahankan performa dan pulih setelah terjadi *severe concept drift* pada data yang datang berurutan.

Dalam penelitian ini, *severe concept drift* sebaiknya tidak hanya diartikan sebagai drift yang cepat. Istilah tersebut didefinisikan sebagai perubahan besar pada fungsi keputusan `P(y|X)`, misalnya perubahan yang memengaruhi seluruh kelas atau sebagian besar ruang fitur. Kecepatan drift kemudian diuji secara terpisah sebagai *abrupt*, *gradual*, atau *recurring drift*.

---

# 1. Review Artikel

## Artikel utama

**Aguiar, G. J., & Cano, A. (2024). A comprehensive analysis of concept drift locality in data streams. Knowledge-Based Systems, 289, 111535.**

- DOI/artikel: <https://doi.org/10.1016/j.knosys.2024.111535>
- Full text: <https://arxiv.org/abs/2311.06396>
- Dataset dan kode artikel: <https://github.com/gabrieljaguiar/locality-concept-drift>
- Jurnal: *Knowledge-Based Systems*.
- Kelayakan: terbit tahun 2024 dan jurnal tersebut berstatus Q1 pada SCImago 2024. Status kuartil tetap perlu diperiksa kembali sesuai basis pemeringkatan yang diwajibkan dosen.

## Alasan pemilihan

Artikel ini paling dekat dengan topik kelompok karena membahas pengaruh **lokalitas dan magnitude concept drift** terhadap performa classifier dan drift detector. Penulis membuat 2.760 skenario benchmark menggunakan Random RBF dan Random Tree, dengan variasi:

- *single-class* dan *multi-class drift*;
- *local* dan *global drift*;
- *sudden*, *gradual*, dan *incremental drift*;
- jumlah kelas dan fitur yang berbeda.

Artikel ini dapat menjadi dasar ilmiah untuk mendefinisikan **severe drift** sebagai *multi-class global drift* atau perubahan dengan magnitude tinggi.

## Ringkasan artikel

### Latar belakang

Concept drift dapat mengubah seluruh atau hanya sebagian distribusi data. Banyak penelitian membandingkan drift detector, tetapi belum menyediakan prosedur benchmark yang terstandardisasi untuk menguji pengaruh lokasi, skala, dan jumlah kelas yang terkena drift.

### Tujuan

1. Membuat kategorisasi concept drift berdasarkan lokalitas dan jumlah kelas yang terdampak.
2. Menyusun benchmark dengan tingkat kesulitan yang terkontrol.
3. Membandingkan sembilan drift detector.
4. Menilai pengaruh drift terhadap performa classifier dan *recovery time*.

### Metode

- Generator: Random RBF dan Random Tree.
- Kategori: *single-class local*, *single-class global*, *multi-class local*, dan *multi-class global*.
- Kecepatan drift: *sudden*, *gradual*, dan *incremental*.
- Classifier yang dipakai sebagai alat evaluasi: Hoeffding Tree.
- Drift detector: ADWIN, DDM, EDDM, HDDM, RDDM, ECDD, KSWIN, Page-Hinkley, dan STEPD.
- Metrik detector: precision, recall, F1, dan detection delay.
- Protokol: evaluasi data stream secara berurutan.

### Temuan penting

- Drift global lebih mudah dideteksi daripada drift lokal karena dampaknya terhadap distribusi dan error classifier lebih besar.
- ADWIN dan Page-Hinkley memberikan hasil yang relatif kuat pada berbagai skenario.
- Drift detector yang sangat sensitif dapat cepat mendeteksi perubahan, tetapi menghasilkan banyak *false alarm*.
- Locality, jumlah kelas, dan magnitude drift memengaruhi besar penurunan performa serta waktu pemulihan classifier.
- Tidak ada satu strategi yang selalu unggul untuk semua bentuk drift.

### Kelebihan

- Eksperimen besar, sistematis, dan dapat direproduksi.
- Drift point dan bentuk drift diketahui sehingga evaluasi lebih objektif.
- Menjelaskan perbedaan local/global drift yang relevan dengan istilah severe drift.
- Dataset, generator, kode, dan hasil tersedia secara publik.

### Keterbatasan

- Fokus utama artikel adalah drift detector, bukan perbandingan keluarga classifier.
- Dampak drift pada classifier hanya dianalisis menggunakan Hoeffding Tree.
- Belum membandingkan DT, SVM, dan ANN dalam protokol adaptasi yang sama.
- Aspek biaya komputasi, memori, dan energi belum menjadi fokus utama.

### Hubungan dengan penelitian kelompok

Artikel ini menyediakan definisi, generator, dan skenario drift, sedangkan penelitian kelompok memperluasnya dengan membandingkan **DT, SVM, dan ANN**. Kontribusi penelitian kelompok dapat diarahkan pada pertanyaan: model mana yang mengalami penurunan terkecil dan pulih paling cepat ketika magnitude drift tinggi?

## Rancangan isi Google Slides

1. **Identitas artikel**: judul, penulis, jurnal, tahun, DOI, dan kuartil.
2. **Masalah penelitian**: drift tidak selalu global; locality dan magnitude menentukan tingkat kesulitan.
3. **Tujuan dan kontribusi**: kategorisasi drift dan 2.760 benchmark.
4. **Metodologi**: generator, empat kategori locality, tiga kecepatan drift, classifier, detector, dan metrik.
5. **Hasil utama**: drift global lebih mudah dideteksi; ADWIN dan Page-Hinkley relatif kuat; sensitivitas tinggi meningkatkan false alarm.
6. **Kelebihan dan keterbatasan**.
7. **Research gap**: belum ada perbandingan adil DT–SVM–ANN di bawah severe drift.
8. **Relevansi untuk penelitian kelompok**: kategori *multi-class global drift* dipakai sebagai severe drift.

## Artikel pendukung

1. Pereira, E. V., & Silva, W. S. (2025). *A Comparison of Approaches for Handling Concept Drifts in Data Processed With Machine Learning*. IEEE Access, 13, 61109–61121.  
   Artikel: <https://doi.org/10.1109/ACCESS.2025.3557229>
2. Mahdi, O. A., et al. (2024). *Roadmap of Concept Drift Adaptation in Data Stream Mining, Years Later*. IEEE Access, 12, 21129–21146.  
   Artikel: <https://doi.org/10.1109/ACCESS.2024.3358817>
3. Hinder, F., Vaquet, V., & Hammer, B. (2024). *One or two things we know about concept drift—Part A: detecting concept drift*. Frontiers in Artificial Intelligence, 7.  
   Artikel: <https://doi.org/10.3389/frai.2024.1330257>
4. Aguiar, G., Krawczyk, B., & Cano, A. (2024). *A survey on learning from imbalanced data streams*. Machine Learning, 113, 4165–4243.  
   Artikel: <https://doi.org/10.1007/s10994-023-06353-6>  
   Full text: <https://arxiv.org/abs/2204.03719>

---

# 2. Dataset

Penelitian sebaiknya menggunakan **dataset sintetis terkontrol sebagai eksperimen utama** dan **dataset real-world sebagai validasi eksternal**. Dataset sintetis diperlukan karena titik, bentuk, kecepatan, dan magnitude drift harus diketahui untuk membuktikan bahwa drift benar-benar severe.

## Rekomendasi utama: benchmark Concept Drift Locality

- Repository: <https://github.com/gabrieljaguiar/locality-concept-drift>
- Artikel sumber: <https://doi.org/10.1016/j.knosys.2024.111535>

**Alasan:** menyediakan Random RBF dan Random Tree dengan variasi local/global, single/multi-class, sudden/gradual/incremental, serta magnitude yang terkontrol. Ini merupakan pilihan paling sesuai dengan fokus severe drift.

## Dataset sintetis tambahan

### SEA

- Dokumentasi dan generator: <https://riverml.xyz/latest/api/datasets/synth/SEA/>
- Karakteristik: tiga fitur numerik, klasifikasi biner, dan fungsi keputusan dapat diganti antarvarian.
- Kegunaan: *sanity check* yang ringan untuk abrupt dan gradual drift.

### STAGGER

- Dokumentasi dan generator: <https://riverml.xyz/latest/api/datasets/synth/STAGGER/>
- Karakteristik: fitur kategorikal dengan beberapa fungsi klasifikasi.
- Kegunaan: menguji perubahan aturan keputusan yang jelas dan mudah dijelaskan.

### Rotating Hyperplane

- Dokumentasi dan generator: <https://riverml.xyz/latest/api/datasets/synth/Hyperplane/>
- Karakteristik: jumlah fitur, jumlah fitur yang berubah, noise, dan magnitude perubahan dapat dikontrol.
- Kegunaan: menguji incremental drift pada ruang fitur numerik berdimensi lebih tinggi.

## Dataset real-world: INSECTS

- Dokumentasi/dataset siap pakai: <https://riverml.xyz/latest/api/datasets/Insects/>
- Repository USP Data Stream: <https://sites.google.com/view/uspdsrepository>
- Artikel dataset: <https://doi.org/10.1007/s10618-020-00698-5>
- Full text artikel dataset: <https://arxiv.org/abs/2005.00113>

**Karakteristik:** data sensor optik penerbangan serangga, umumnya enam kelas, serta tersedia dalam varian *abrupt*, *gradual*, *incremental*, *incremental-reoccurring*, balanced, dan imbalanced. Dataset ini cocok untuk menguji apakah kesimpulan dari data sintetis tetap berlaku pada data nyata.

## Dataset validasi tambahan: Electricity/Elec2

- Dokumentasi: <https://riverml.xyz/latest/api/datasets/Elec2/>

**Karakteristik:** 45.312 observasi berurutan dari pasar listrik Australia dengan delapan fitur dan dua kelas. Dataset ini sering digunakan dalam penelitian data stream, tetapi titik dan tingkat keparahan drift tidak diketahui secara pasti. Karena itu, dataset ini hanya cocok sebagai validasi tambahan, bukan sebagai bukti utama severe drift.

## Pemilihan akhir yang disarankan

| Peran | Dataset | Alasan |
|---|---|---|
| Eksperimen utama | Concept Drift Locality Benchmark | Magnitude, locality, jumlah kelas terdampak, dan jenis drift dapat dikontrol |
| Sanity check | SEA | Ringan, mudah direproduksi, dan fungsi keputusan jelas |
| Drift bertahap | Rotating Hyperplane | Magnitude dan jumlah fitur yang berubah dapat dikontrol |
| Validasi real-world | INSECTS | Memiliki varian abrupt, gradual, incremental, dan recurring |
| Validasi tambahan | Electricity | Benchmark populer, tetapi ground-truth drift tidak tersedia |

---

# 3. Ide Tahapan Penelitian dan Skenario Uji Coba

## A. Rumusan masalah

1. Model mana di antara DT, SVM, dan ANN yang mempertahankan performa terbaik ketika mengalami severe concept drift?
2. Model mana yang paling cepat pulih setelah abrupt, gradual, dan recurring severe drift?
3. Apakah model dengan performa prediktif terbaik juga paling efisien dari sisi waktu proses dan memori?
4. Apakah peringkat model pada data sintetis konsisten dengan INSECTS sebagai data real-world?

## B. Hipotesis awal

- **DT/Hoeffding Adaptive Tree** diperkirakan cepat beradaptasi pada data tabular karena struktur cabang dapat diperbarui atau diganti.
- **SVM online** diperkirakan efisien pada perubahan decision boundary yang relatif linear, tetapi lebih lemah pada drift nonlinear berat.
- **ANN online** diperkirakan mampu memodelkan pola nonlinear, tetapi membutuhkan lebih banyak data untuk pulih dan berisiko mengalami *catastrophic forgetting*.

Hipotesis tersebut harus diuji; jangan ditulis sebagai kesimpulan sebelum eksperimen dilakukan.

## C. Model yang dibandingkan

Agar sesuai dengan data streaming, jangan menggunakan model batch biasa tanpa strategi pembaruan.

| Keluarga | Implementasi yang disarankan | Catatan |
|---|---|---|
| Decision Tree | Hoeffding Adaptive Tree | Pohon untuk stream dan memiliki mekanisme adaptasi |
| SVM | Linear online SVM dengan hinge loss/SGD | Gunakan `partial_fit` dan standardisasi online |
| ANN | MLP kecil yang diperbarui per mini-batch | Arsitektur tetap, misalnya 1–2 hidden layer |

**Kontrol penting:** ketiga model harus menerima urutan data, ukuran mini-batch, label delay, strategi reset, dan data setelah drift yang sama.

## D. Definisi severe drift

Definisi utama yang mudah direproduksi:

- **Severe:** *multi-class global real drift*, yaitu fungsi keputusan seluruh kelas berubah.
- **Pembanding:** *local drift* atau magnitude rendah/menengah.
- Jika generator menyediakan parameter magnitude, gunakan minimal tiga level, misalnya **low, medium, high**, lalu nyatakan nilai parameter eksaknya di laporan.
- Kecepatan drift dipisahkan dari severity:
  - abrupt: pergantian konsep segera;
  - gradual: konsep lama dan baru bercampur selama window transisi;
  - recurring: konsep A berubah menjadi B lalu kembali ke A.

## E. Tahapan penelitian

1. **Studi literatur**  
   Menetapkan definisi data stream, real/virtual drift, locality, magnitude, kecepatan drift, evaluasi prequential, dan recovery time.

2. **Persiapan dataset**  
   Menghasilkan stream sintetis dengan drift point yang diketahui; memuat INSECTS tanpa mengacak urutan temporal.

3. **Praproses online**  
   Melakukan encoding dan standardisasi hanya dengan informasi yang telah tiba. Hindari normalisasi menggunakan seluruh dataset karena menyebabkan *future-data leakage*.

4. **Warm-up**  
   Memberikan bagian awal stream kepada semua model, misalnya 10% awal atau satu segmen konsep stabil, sebelum pengukuran drift dimulai.

5. **Evaluasi prequential**  
   Untuk setiap observasi atau mini-batch: prediksi terlebih dahulu, catat hasil, kemudian lakukan pembaruan model menggunakan label yang baru diterima.

6. **Adaptasi**  
   Bandingkan kondisi tanpa reset dan kondisi dengan detector serta strategi reset yang sama. ADWIN dapat dipakai sebagai detector bersama agar perbedaan terutama berasal dari model.

7. **Pengulangan**  
   Jalankan sedikitnya 10 *random seeds* untuk setiap kombinasi dataset, drift, severity, dan model.

8. **Analisis hasil**  
   Bandingkan performa sebelum drift, penurunan sesudah drift, performa akhir, waktu pemulihan, waktu proses, dan memori.

9. **Uji statistik**  
   Gunakan Friedman test untuk membandingkan tiga model pada banyak skenario. Jika signifikan, lanjutkan dengan Wilcoxon signed-rank berpasangan dan koreksi Holm.

10. **Pelaporan**  
    Sajikan tabel peringkat, kurva performa terhadap waktu, *critical difference diagram* jika memungkinkan, dan pembahasan trade-off akurasi–adaptasi–efisiensi.

## F. Skenario uji coba

### Eksperimen 1 — Baseline tanpa drift

Tujuan: mengukur kemampuan dasar masing-masing model pada stream stasioner.

### Eksperimen 2 — Abrupt severe drift

- Konsep berubah secara langsung pada 25%, 50%, atau 75% panjang stream.
- Gunakan perubahan global dengan magnitude tinggi.
- Fokus: besar penurunan performa dan kecepatan pemulihan.

### Eksperimen 3 — Gradual severe drift

- Konsep lama secara bertahap digantikan konsep baru dalam transition window.
- Uji beberapa lebar window, misalnya sempit, sedang, dan lebar.
- Fokus: stabilitas selama masa transisi.

### Eksperimen 4 — Recurring severe drift

- Urutan konsep A → B → A.
- Fokus: apakah model dapat memanfaatkan konsep lama atau justru telah melupakannya.

### Eksperimen 5 — Severity ablation

- Jenis drift dan drift point dibuat tetap.
- Variasikan low, medium, dan high magnitude.
- Fokus: hubungan antara severity dengan performance drop dan recovery time.

### Eksperimen 6 — Drift adaptation ablation

Untuk tiap model, bandingkan:

1. pembaruan kontinu tanpa detector;
2. ADWIN dengan reset penuh;
3. sliding window atau replay buffer berukuran sama.

Jika waktu terbatas, gunakan hanya kondisi 1 dan 2.

### Eksperimen 7 — Validasi real-world

- Jalankan konfigurasi final pada INSECTS abrupt, gradual, incremental, dan recurring.
- Gunakan Electricity hanya sebagai pemeriksaan tambahan karena ground-truth drift-nya tidak pasti.

## G. Metrik evaluasi

### Metrik utama

- **Macro-F1:** adil untuk multiclass dan kelas yang tidak seimbang.
- **Balanced accuracy:** tidak didominasi kelas mayoritas.
- **Cohen's kappa:** membandingkan prediksi dengan peluang kesepakatan acak.

### Metrik dinamika drift

- **Performance drop:** performa pra-drift dikurangi performa minimum pasca-drift.
- **Recovery time:** jumlah observasi setelah drift sampai performa kembali minimal 95% dari baseline pra-drift.
- **Area under recovery curve:** merangkum kerusakan dan pemulihan setelah drift.
- **Worst-window performance:** performa terendah pada sliding window tertentu.

### Metrik efisiensi

- Waktu pelatihan/update.
- Throughput dalam observasi per detik.
- Peak memory.
- Ukuran model.

## H. Matriks eksperimen minimum

| Faktor | Level minimum |
|---|---|
| Model | DT, SVM, ANN |
| Drift | Abrupt, gradual, recurring |
| Severity | Medium dan severe |
| Dataset | Synthetic locality benchmark dan INSECTS |
| Adaptasi | Continuous update dan ADWIN-reset |
| Seed | 10 |

Desain minimum tersebut menghasilkan `3 × 3 × 2 × 2 × 2 × 10 = 720` run. Apabila terlalu berat, pertahankan semua model dan jenis drift, tetapi gunakan satu kondisi severe, satu strategi adaptasi, dua dataset, dan 10 seed: `3 × 3 × 1 × 2 × 1 × 10 = 180` run.

## I. Research gap dan kontribusi

### Research gap

Sebagian studi terbaru berfokus pada perbandingan drift detector, ensemble khusus, atau satu keluarga classifier. Penelitian tentang locality menunjukkan bahwa magnitude dan bagian distribusi yang terdampak menentukan kesulitan drift, tetapi belum memberikan perbandingan terkontrol antara DT, SVM, dan ANN dengan protokol adaptasi identik di bawah severe drift.

### Kontribusi yang diusulkan

1. Perbandingan adil tiga keluarga model menggunakan urutan stream dan anggaran adaptasi yang sama.
2. Definisi severe drift yang eksplisit dan dapat direproduksi.
3. Evaluasi bukan hanya berdasarkan skor akhir, tetapi juga performance drop, recovery time, throughput, dan memori.
4. Validasi pada skenario sintetis terkontrol dan dataset real-world.

---

# Jawaban Ringkas Tiga Tugas Kelompok

## 1. Paper apa yang direview?

Artikel utama adalah **Aguiar dan Cano (2024), “A comprehensive analysis of concept drift locality in data streams,” Knowledge-Based Systems**. Artikel ini dipilih karena terbit dalam tiga tahun terakhir, jurnalnya Q1 menurut SCImago 2024, menyediakan benchmark dan kode terbuka, serta langsung membahas locality dan magnitude drift yang dapat dijadikan dasar definisi severe concept drift. Link: <https://doi.org/10.1016/j.knosys.2024.111535>.

## 2. Dataset apa yang digunakan?

Gunakan **Concept Drift Locality Benchmark** sebagai eksperimen utama karena drift dapat dikontrol, **SEA atau Rotating Hyperplane** sebagai sanity check, dan **INSECTS** sebagai validasi real-world. Electricity dapat ditambahkan, tetapi tidak digunakan sebagai bukti utama severe drift karena ground-truth drift-nya tidak diketahui pasti.

## 3. Bagaimana tahapan penelitian dan skenario uji cobanya?

Bandingkan Hoeffding Adaptive Tree, online linear SVM, dan online MLP dengan evaluasi prequential. Uji abrupt, gradual, dan recurring drift pada magnitude medium dan severe; jalankan sedikitnya 10 seed; ukur Macro-F1, balanced accuracy, kappa, performance drop, recovery time, throughput, dan memori; lalu analisis perbedaannya menggunakan Friedman dan Wilcoxon-Holm.

---

# Perangkat Lunak yang Dapat Digunakan

- River: <https://riverml.xyz/>
- CapyMOA: <https://capymoa.org/>
- scikit-learn: <https://scikit-learn.org/>

**Catatan implementasi:** River cocok untuk generator dan model stream berbasis pohon; SVM online dapat menggunakan classifier SGD dengan hinge loss; ANN dapat menggunakan MLP dengan pembaruan mini-batch atau integrasi PyTorch melalui CapyMOA. Hindari membandingkan model batch statis dengan model online adaptif tanpa menyamakan protokol pembaruan.
