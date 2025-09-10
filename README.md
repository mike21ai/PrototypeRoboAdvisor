# PrototypeRoboAdvisor

# MyGoal: Prototipe AI Financial Planner & Robo-Advisor

MyGoal adalah sebuah prototipe aplikasi web interaktif yang dirancang untuk membantu Generasi Milenial dan Z di Indonesia dalam merencanakan dan mencapai tujuan finansial mereka secara cerdas dan otomatis.  
Proyek ini menggabungkan dua konsep utama: Financial Planning yang berorientasi pada tujuan hidup (goal-based) dan Robo-Advisor yang memberikan rekomendasi investasi otomatis berdasarkan profil pengguna.  
Prototipe ini dibuat sebagai bagian dari Capstone Project mata kuliah Digital Finance.

---

## ✨ Fitur Utama (Implemented Features)

Prototipe ini telah mengimplementasikan alur pengguna utama dari awal hingga akhir, mencakup:

### Onboarding Komprehensif
- **Profiling Risiko:** Kuesioner singkat untuk menentukan profil risiko pengguna (Konservatif, Moderat, Agresif).
- **Cek Kondisi Keuangan:** Input pendapatan dan pengeluaran untuk menghitung "Kemampuan Investasi" bulanan, memastikan rencana yang dibuat realistis.

### Perencanaan Berbasis Tujuan (Goal-Based Planning)
- **Template Tujuan:** Pengguna dapat memilih dari berbagai template tujuan populer (DP Properti, Dana Pensiun, Pendidikan Anak, dll.) untuk memulai.
- **Input Fleksibel:** Pengguna memasukkan Target Dana dan Jangka Waktu untuk setiap tujuan yang dibuat.

### Rekomendasi Cerdas (Robo-Advisor Engine)
- **Perhitungan Investasi Bulanan:** AI secara otomatis menghitung berapa dana yang perlu diinvestasikan setiap bulan untuk mencapai target.
- **Alokasi Portofolio Otomatis:** Memberikan rekomendasi alokasi aset (Saham Domestik, Saham Internasional, Obligasi, Pasar Uang) yang disesuaikan dengan profil risiko dan jangka waktu tujuan.
- **Proyeksi Pertumbuhan:** Grafik interaktif yang memvisualisasikan potensi hasil investasi dalam tiga skenario pasar: Pesimis, Normal, dan Optimis.

### Dashboard & Monitoring
- **Ringkasan Finansial:** Menampilkan total aset dan kemampuan investasi pengguna.
- **Progress Tracking:** Kartu-kartu tujuan yang menampilkan progress bar visual untuk memantau pencapaian.

### Fitur Interaktif & Edukasi
- **Simulasi "What-If":** Slider interaktif yang memungkinkan pengguna melihat dampak perubahan setoran bulanan terhadap waktu pencapaian tujuan.
- **Rencana Aksi (Roadmap):** Checklist bulanan yang mengingatkan pengguna untuk melakukan setoran rutin, menjaga konsistensi.
- **Notifikasi Cerdas:** Ikon notifikasi yang memberitahu jika ada aksi yang perlu dilakukan.
- **Gamifikasi:** Sistem badge pencapaian untuk memotivasi pengguna (misal: "Langkah Pertama", "Konsisten!").
- **Layer Edukasi:** Penjelasan singkat dan mudah dipahami mengenai strategi alokasi aset.

---

## ⚙️ Penjelasan Perhitungan (Calculation Logic)

### 1. Perhitungan Investasi Bulanan

Untuk menghitung setoran bulanan (M), digunakan formula *Future Value of an Annuity*:

\[
M = \frac{FV \times r}{(1 + r)^n - 1}
\]

Keterangan:  
- **M:** Setoran bulanan yang dibutuhkan.  
- **FV:** Target Dana (Future Value).  
- **r:** Tingkat imbal hasil bulanan (asumsi imbal hasil tahunan dibagi 12).  
- **n:** Jumlah periode (Jangka Waktu dalam tahun × 12).

_Asumsi imbal hasil tahunan (annualReturnRate) berdasarkan profil risiko:_  
- Konservatif: 5%  
- Moderat: 8%  
- Agresif: 12%  

### 2. Alokasi Aset Portofolio

Alokasi aset rule-based sesuai dengan profil risiko pengguna:

| Profil Risiko | Saham Domestik | Saham Internasional | Obligasi | Pasar Uang |
|---------------|----------------|--------------------|----------|------------|
| Konservatif   | 15%            | 5%                 | 60%      | 20%        |
| Moderat       | 35%            | 15%                | 40%      | 10%        |
| Agresif       | 50%            | 25%                | 20%      | 5%         |

### 3. Proyeksi Pertumbuhan

Simulasi tiga skenario berdasarkan imbal hasil tahunan (baseRate):  
- **Normal:** Menggunakan baseRate.  
- **Optimis:** baseRate + 3%.  
- **Pesimis:** baseRate - 3%.

---

## 🚧 Status Proyek & Area Pengembangan

### Apa yang Belum Ada (Out of Scope for Prototype)
- **Backend & Database:** Semua data hanya disimpan di memori browser (appState) dan hilang saat refresh.
- **Autentikasi Pengguna:** Belum ada sistem login dan registrasi.
- **Integrasi Pihak Ketiga:** Tidak ada koneksi real ke rekening bank atau platform investasi (APERD).
- **Transaksi Aktual:** Tombol "Selesaikan Setoran" hanya simulasi, tanpa pergerakan dana nyata.
- **Model AI Statis:** Rekomendasi masih rule-based tanpa adaptasi dinamis berdasarkan kondisi pasar atau keuangan pengguna.

### Rencana Pengembangan Lanjutan (Future Roadmap)
- Implementasi Backend & Autentikasi dengan Firebase/Supabase.
- Integrasi Open Finance/Banking API untuk otomatisasi dan pendebetan.
- Kemitraan dengan APERD untuk eksekusi transaksi real-time melalui API.
- Personalisasi dengan Machine Learning agar rekomendasi adaptif.
- Modul Edukasi Lanjutan berisi artikel, video, dan kursus singkat literasi finansial.

---
