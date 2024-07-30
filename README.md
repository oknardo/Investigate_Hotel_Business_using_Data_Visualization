# Investigate Business Hotel using Data Visualization

## Created By:
**Name:** Oknardo Budi Setiawan Tulung  
**Email:** oknardotulung@gmail.com  
**LinkedIn:** [www.linkedin.com/in/oknardo-tulung](https://www.linkedin.com/in/oknardo-tulung)  
**GitHub:** [https://github.com/oknardo](https://github.com/oknardo)

## Dataset
Dataset diperoleh dari Rakamin Academy, berisi data pemesanan pada suatu perusahaan hotel.

## Latar Belakang dan Objektif
### Latar Belakang
Sebuah perusahaan hotel ingin mengetahui faktor dan insight apa saja yang berhubungan dengan performa pemesanan dalam bisnis hotel. serta mencari faktor-faktor yang mempengaruhi pembatalan pemesanan tiket hotel.

### Objektif
- Mengukur perilaku pemesanan hotel berdasarkan jenis hotel dan musim/event.
- Menilai pengaruh durasi menginap terhadap tingkat pembatalan pemesanan.
- Menganalisis pengaruh lead time (waktu antara pemesanan dan tanggal kedatangan) terhadap tingkat pembatalan pemesanan.

## Batasan Masalah
- Analisis ini hanya mencakup data pemesanan hotel dari tahun 2017 hingga 2019.
- Hanya melakukan analisis terkait perilaku pemesanan, durasi menginap, dan lead time.
- Tidak mencakup analisis eksternal seperti tren pasar atau analisis kompetitor.

## Data dan Asumsi
### Data
Data yang digunakan dalam analisis ini terdiri dari beberapa tabel dengan format csv yang mencakup informasi berikut:
- **Hotel Data**: Informasi tentang jenis hotel.
- **Booking Data**: Informasi tentang pemesanan, termasuk tanggal pemesanan, durasi menginap, jumlah tamu, dan status pembatalan.
- **Customer Data**: Informasi tentang pelanggan, termasuk id pelanggan, jumlah anak, dan agen pemesanan.
- **Payment Data**: Informasi tentang tipe pembayaran yang digunakan dalam setiap transaksi.

### Asumsi
- Data yang tersedia akurat dan mencerminkan aktivitas bisnis yang sebenarnya.
- Semua transaksi yang dicatat adalah valid dan telah diverifikasi.

## Analisis Data
### Proses Analisis
1. **Handle Missing Value**:
   - Menghapus baris dengan nilai null di kolom children.
   - Mengisi nilai pada fitur city dengan "Undefined".
   - Mengisi nilai pada fitur agent dan company dengan 0.

2. **Handling Duplicated Data**:
   - Tidak menghapus duplicate data, karena terlalu banyak data duplicated (33.261 baris dari total 119.390 baris).

3. **Feature Selection**:
   - Pada fitur meals menyederhanakan kategori breakfast, full board, dan dinner menjadi with meals dan no meals.
   - Filter fitur guest lebih dari 0.

4. **Feature Transformation**:
   - Transformasi fitur normalisasi.

5. **Handling Outliers**:
   - Menghapus baris dengan adr kurang dari 0 atau lebih dari 5000.
   - Menghapus baris dengan required_car_parking_spaces sama dengan 8.
   - Menghapus baris dengan babies lebih dari 8.
   - Menghapus baris dengan children sama dengan 10.
   - Menghapus baris dengan total tamu (adults + children + babies) sama dengan 0.

### Hasil Analisis
1. **Ratio Pemesanan Hotel Per-Tahun**:
   - Analisis pemesanan hotel berdasarkan jenis hotel dari tahun 2017 sampai tahun 2019.

![image](https://github.com/user-attachments/assets/792df449-dfac-4f32-9e6e-d3038250be92)

2. **Monthly Hotel Booking Analysis Based on Hotel Type**:
   - Kenaikan jumlah pemesanan hotel sering kali terjadi selama musim liburan.
   - Kenaikan pada bulan Mei - Agustus dipengaruhi oleh faktor musim libur sekolah serta adanya perayaan Cuti Bersama & Hari Raya Idul Fitri.
   - Kenaikan pada bulan November dan Desember dipengaruhi oleh faktor Hari Raya Natal dan Tahun Baru.

![image](https://github.com/user-attachments/assets/a3653612-b57a-4533-85cc-df30583da1ed)

3. **Persentase Pemesanan Hotel Berdasarkan Durasi yang Diambil**:
   - Data dibagi berdasarkan kategori durasi menginap, yaitu Short Stay (1-3 hari), Medium Stay (4-7 hari), Long Stay (8-14 hari), dan Extended Stay (14-28 hari).
   - Rata-rata yang datang ke hotel bertipe City Hotel menginap dengan kategori durasi Short Stay.
   - Hotel dengan tipe Resort Hotel mendominasi pelanggan yang menginap dengan kategori durasi Medium Stay, Long Stay, dan Extended Stay.

![image](https://github.com/user-attachments/assets/bece9b33-6aef-4a92-b32f-5df043a51b40)

4. **Cancellation Rate Based on Stay Duration Categories**:
   - Semakin lama durasi pemesanan yang diambil semakin tinggi juga tingkat pembatalan pemesanan.
   - Resort Hotel menjadi pilihan terbaik untuk menginap dengan durasi lebih pendek (short stay) dikarenakan persentase pembatalannya yang lebih rendah dibanding City Hotel.

![image](https://github.com/user-attachments/assets/a2d7d84a-dfbd-4a19-93d7-b3f15f32c99c)

5. **Cancellation Ratio by Lead Time Category and Hotel Type**:
   - Semakin lama lead time (waktu antara pemesanan dan tanggal kedatangan), semakin tinggi rasio pembatalan pesanan.
   - Pola serupa terlihat di Resort Hotel, meskipun dengan variasi pembatalan lebih rendah.

![image](https://github.com/user-attachments/assets/5dd09239-27d7-4857-bd6b-c2aadec7f1f6)

## Simpulan
- **Perilaku Pemesanan**: City Hotel mendominasi pemesanan dengan durasi menginap yang lebih pendek, sedangkan Resort Hotel mendominasi pemesanan dengan durasi menginap yang lebih lama.
- **Pembatalan Pemesanan**: Semakin lama lead time (waktu antara pemesanan dan tanggal kedatangan), semakin tinggi rasio pembatalan pesanan. Hotel dengan lead time yang lebih pendek cenderung memiliki tingkat pembatalan yang lebih rendah.

## Saran
- **Optimalkan Manajemen Reservasi**: Hotel dapat menyesuaikan kebijakan pembatalan atau menawarkan insentif untuk pelanggan dengan lead time yang lebih lama untuk mengurangi risiko pembatalan dan meningkatkan pendapatan kamar hotel secara keseluruhan.
- **Fokus pada Musim Liburan**: Mengoptimalkan strategi pemasaran dan penawaran khusus selama musim liburan untuk meningkatkan jumlah pemesanan.
- **Penyesuaian Fasilitas**: Menyediakan fasilitas tambahan yang menarik untuk tamu yang menginap dalam durasi yang lebih lama di Resort Hotel untuk meningkatkan kepuasan pelanggan dan mengurangi pembatalan.
