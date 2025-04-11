| No  | Nama                 | Skor Keaktifan | Peran                        |
| --- | -------------------- | -------------- | ---------------------------- |
| 1   | Rezky Awalya         | 3              | Mengerjakan brainstorming    |
| 2   | A. Ashadelah M.A     | 3              | Mengerjakan brainstorming    |
| 3   | Fatsa Akhwani        | 3              | Membuat soal LRS             |
| 4   | Nur Afni Ramadani    | 3              | Membuat soal Normalisasi     |
| 5   | Nur Inayah Athaillah | 2              | Sakit, mohon doanya pak.     |
| 6   | Siti Nur Hasiza.A    | 2              | Sakit juga, mohon doanya pak |
# 1. Jelaskan apa yang dimaksud dengan normalisasi database?
Normalisasi database adalah proses mengorganisir data dalam sebuah database untuk menghilangkan redundansi data, meningkatkan integritas data, dan memudahkan perawatan database.
# 2. Apa yang menjadi tujuan pembuatan database perlu dinormalisasikan?
- Menghilangkan redundansi data
- Meningkatkan integritas data
- Memudahkan perawatan database
- Meningkatkan kinerja database

# 3. Uraikan proses singkat tentang normalisasi dari tahap 1NF hingga 5NF!
Baik, kita akan menggunakan satu database yang sama dan melakukan proses normalisasi dari **1NF hingga 5NF**. Misalnya, kita memiliki database **"rental_mobil"** dengan tabel awal sebagai berikut:

### **Tabel Awal (Belum Dinormalisasi)**

|ID_Pembelian|Nama_Pembeli|No_HP|Mobil|Harga|Warna|Dealer|
|---|---|---|---|---|---|---|
|P001|Andi|081234567890|Avanza|200jt|Merah|Dealer A|
|P002|Budi|082345678901|Innova|300jt|Hitam|Dealer B|
|P003|Andi|081234567890|Xpander|350jt|Putih|Dealer C|

---

## **1NF (First Normal Form) - Menghilangkan Multi-Valued Attributes**

Dalam tabel awal, **Nama_Pembeli** memiliki **No_HP** yang mungkin lebih dari satu, sehingga kita perlu memisahkannya menjadi tabel baru.

### **Setelah 1NF**

**Tabel Pembelian:**

|ID_Pembelian|ID_Pembeli|ID_Mobil|
|---|---|---|
|P001|C001|M001|
|P002|C002|M002|
|P003|C001|M003|

**Tabel Pembeli:**

|ID_Pembeli|Nama_Pembeli|No_HP|
|---|---|---|
|C001|Andi|081234567890|
|C002|Budi|082345678901|

**Tabel Mobil:**

|ID_Mobil|Nama_Mobil|Harga|Warna|Dealer|
|---|---|---|---|---|
|M001|Avanza|200jt|Merah|Dealer A|
|M002|Innova|300jt|Hitam|Dealer B|
|M003|Xpander|350jt|Putih|Dealer C|

---

## **2NF (Second Normal Form) - Menghilangkan Ketergantungan Parsial**

Sekarang, kita periksa apakah ada kolom yang hanya bergantung pada **sebagian primary key**. Pada **Tabel Mobil**, kolom **Dealer** hanya bergantung pada **Nama_Mobil**, bukan ID_Pembelian. Maka, kita buat tabel terpisah untuk dealer.

### **Setelah 2NF**

**Tabel Mobil (Direvisi):**

|ID_Mobil|Nama_Mobil|Harga|Warna|ID_Dealer|
|---|---|---|---|---|
|M001|Avanza|200jt|Merah|D001|
|M002|Innova|300jt|Hitam|D002|
|M003|Xpander|350jt|Putih|D003|

**Tabel Dealer (Baru):**

|ID_Dealer|Nama_Dealer|
|---|---|
|D001|Dealer A|
|D002|Dealer B|
|D003|Dealer C|

---

## **3NF (Third Normal Form) - Menghilangkan Ketergantungan Transitif**

Dalam **Tabel Pembeli**, jika kita punya atribut seperti **Kota** dan **Kode_Pos**, maka **Kode_Pos** bergantung pada **Kota**, bukan pada ID_Pembeli. Kita pecah ke tabel baru.

### **Setelah 3NF**

**Tabel Pembeli (Direvisi):**

|ID_Pembeli|Nama_Pembeli|No_HP|ID_Kota|
|---|---|---|---|
|C001|Andi|0812|K001|
|C002|Budi|0823|K002|

**Tabel Kota (Baru):**

|ID_Kota|Nama_Kota|Kode_Pos|
|---|---|---|
|K001|Jakarta|10110|
|K002|Bandung|40231|

---

## **4NF (Fourth Normal Form) - Menghilangkan Multi-Valued Dependencies**

Jika satu dealer menjual banyak mobil **dan** berlokasi di lebih dari satu tempat, maka ada **multi-valued dependency**. Kita buat tabel relasi **Dealer_Lokasi**.

### **Setelah 4NF**

**Tabel Dealer_Lokasi (Baru):**

|ID_Dealer|Lokasi|
|---|---|
|D001|Jakarta|
|D001|Surabaya|
|D002|Bandung|

---

## **5NF (Fifth Normal Form) - Menghilangkan Join Dependency**

Jika dalam satu transaksi kita menyimpan **ID_Pembelian**, **ID_Pembeli**, dan **ID_Mobil**, tetapi ada kemungkinan bahwa **satu mobil bisa dibeli lebih dari satu kali** atau **satu pelanggan bisa membeli lebih dari satu mobil**, kita pisahkan lagi ke tabel hubungan.

### **Setelah 5NF**

**Tabel Pembelian (Final):**

|ID_Pembelian|Tanggal_Pembelian|
|---|---|
|P001|2025-02-25|
|P002|2025-02-26|

**Tabel Pembelian_Detail (Baru) (Relasi Many-to-Many)**

|ID_Pembelian|ID_Pembeli|ID_Mobil|
|---|---|---|
|P001|C001|M001|
|P001|C001|M003|
|P002|C002|M002|

---

## **Kesimpulan**

✅ **1NF**: Memisahkan **No_HP** yang sebelumnya multi-valued.  
✅ **2NF**: Memisahkan **Dealer** dari **Mobil**.  
✅ **3NF**: Memisahkan **Kota dan Kode_Pos** dari **Pembeli**.  
✅ **4NF**: Memisahkan **Dealer_Lokasi** agar satu dealer bisa punya banyak lokasi.  
✅ **5NF**: Memisahkan **Pembelian_Detail** agar hubungan antara pembeli dan mobil lebih fleksibel.
# 4. Buatlah contoh normalisasi database minimal dari tahap 1NF hingga 3NF pada kasus database proyek basis data sekolah masing-masing!

## **📌 Tabel Tidak Normal (UNF)**

|id_siswa|nama_siswa|kelas|jurusan|ekskul|
|---|---|---|---|---|
|1|Adel|XII RPL 1|RPL|PMR, OSIS, Pramuka|
|2|Alya|XII RPL 1|RPL|OSIS, Paskibra, Pramuka|
|3|Hasiza|XI RPL 1|RPL|Paskibra|
|4|Nayah|XI RPL 1|RPL|Pramuka|
|5|Caca|X RPL 1|RPL|Pramuka|
|6|Fina|X RPL 1|RPL|Pramuka|

---

## **📌 First Normal Form (1NF)**

|id_siswa|nama_siswa|kelas|jurusan|ekskul|
|---|---|---|---|---|
|1|Adel|XII RPL 1|RPL|PMR|
|1|Adel|XII RPL 1|RPL|OSIS|
|1|Adel|XII RPL 1|RPL|Pramuka|
|2|Alya|XII RPL 1|RPL|OSIS|
|2|Alya|XII RPL 1|RPL|Paskibra|
|2|Alya|XII RPL 1|RPL|Pramuka|
|3|Hasiza|XI RPL 1|RPL|Paskibra|
|4|Nayah|XI RPL 1|RPL|Pramuka|
|5|Caca|X RPL 1|RPL|Pramuka|
|6|Fina|X RPL 1|RPL|Pramuka|

---

## **📌 Second Normal Form (2NF)**

### **Tabel `siswa`**

|id_siswa|nama_siswa|kelas|jurusan|
|---|---|---|---|
|1|Adel|XII RPL 1|RPL|
|2|Alya|XII RPL 1|RPL|
|3|Hasiza|XI RPL 1|RPL|
|4|Nayah|XI RPL 1|RPL|
|5|Caca|X RPL 1|RPL|
|6|Fina|X RPL 1|RPL|

### **Tabel `ekskul`**

|id_ekskul|nama_ekskul|
|---|---|
|1|PMR|
|2|OSIS|
|3|Pramuka|
|4|Paskibra|

### **Tabel `siswa_ekskul` (Relasi)**

|id_siswa|id_ekskul|
|---|---|
|1|1|
|1|2|
|1|3|
|2|2|
|2|4|
|2|3|
|3|4|
|4|3|
|5|3|
|6|3|

---

## **📌 Third Normal Form (3NF)**

### **Tabel `siswa`

| id_siswa          | nama_siswa | kelas     | jurusan |
| ----------------- | ---------- | --------- | ------- |
| 1                 | Adel       | XII RPL 1 | RPL     |
| 2                 | Alya       | XII RPL 1 | RPL     |
| 3                 | Hasiza     | XI RPL 1  | RPL     |
| 4                 | Nayah      | XI RPL 1  | RPL     |
| 5                 | Caca       | X RPL 1   | RPL     |
| 6                 | Fina       | X RPL 1   | RPL     |

### **Tabel `ekskul`

| id_ekskul          | nama_ekskul |
| ------------------ | ----------- |
| 1                  | PMR         |
| 2                  | OSIS        |
| 3                  | Pramuka     |
| 4                  | Paskibra    |

### **Tabel `siswa_ekskul` (Relasi)

| id_siswa                          | id_ekskul |
| --------------------------------- | --------- |
| 1                                 | 1         |
| 1                                 | 2         |
| 1                                 | 3         |
| 2                                 | 2         |
| 2                                 | 4         |
| 2                                 | 3         |
| 3                                 | 4         |
| 4                                 | 3         |
| 5                                 | 3         |
| 6                                 | 3         |




# SOAL NORMALISASI
- Soal 1
Dalam struktur database yang ditunjukkan, jika seorang siswa mengikuti beberapa kegiatan ekstrakurikuler dan setiap ekskul memiliki beberapa pembina, jenis hubungan apa yang paling tepat antara tabel "siswa", "ekskul", dan "pembina"?
    A. Hubungan satu ke satu antara siswa dan ekskul, serta satu ke banyak antara ekskul dan pembina.
    B. Hubungan banyak ke banyak antara siswa dan ekskul, serta satu ke banyak antara ekskul dan pembina.
    C. Hubungan satu ke banyak antara siswa dan ekskul, serta satu ke satu antara ekskul dan pembina.
    D. Hubungan banyak ke satu antara siswa dan ekskul, serta satu ke banyak antara siswa dan pembina.

Jawaban yang benar: B. Hubungan banyak ke banyak antara siswa dan ekskul, serta satu ke banyak antara ekskul dan pembina.

- Soal 2
Tabel mana yang berisi informasi tentang pembina dari setiap kegiatan ekstrakurikuler?
    A. Tabel ekskul
    B. Tabel siswa
    C. Tabel pembina
    D. Tabel detail

Jawaban yang benar: C. Tabel pembina

- Soal 3
Apa hubungan antara tabel siswa dan tabel ekskul dalam database ini?
    A. Siswa memiliki banyak ekskul
    B. Ekskul memiliki banyak siswa
    C. Siswa dan ekskul tidak memiliki hubungan
    D. Siswa hanya terdaftar di satu ekskul

Jawaban yang benar: A. Siswa memiliki banyak ekskul

- Soal 4
Apa yang dimaksud dengan normalisasi dalam konteks database yang ditunjukkan?
    A. Menggabungkan semua informasi ke dalam satu tabel
    B. Memecah tabel besar menjadi tabel yang lebih kecil
    C. Menghapus data yang tidak relevan
    D. Menambah kolom baru pada tabel

Jawaban yang benar: B. Memecah tabel besar menjadi tabel yang lebih kecil


# SOAL LRS
- Soal 1
Dalam model relasional basis data, keberadaan atribut id_detail dalam tabel ekskul dapat menyebabkan anomali berikut, kecuali:
	A. Anomali penyisipan (insertion anomaly), di mana informasi detail ekstrakurikuler tidak bisa ditambahkan tanpa adanya data ekstrakurikuler baru.
	B. Anomali penghapusan (deletion anomaly), di mana menghapus satu ekstrakurikuler dapat menghilangkan informasi detail yang masih dibutuhkan.
	C. Anomali pemutakhiran (update anomaly), di mana pembaruan informasi detail harus dilakukan di beberapa baris data ekstrakurikuler.
	D. Anomali keterhubungan (relation anomaly), di mana satu detail dapat terkait dengan banyak ekstrakurikuler yang berbeda.

Jawaban: D. Anomali keterhubungan (relation anomaly), di mana satu detail dapat terkait dengan banyak ekstrakurikuler yang berbeda.

- Soal 2
Jika dalam sistem ini seorang siswa dapat mengikuti beberapa ekstrakurikuler, tetapi setiap ekstrakurikuler hanya dapat memiliki satu pembina, maka bentuk normalisasi yang paling sesuai untuk tabel pembina adalah:
	A.  Tidak dilakukan normalisasi karena data sudah efisien dalam bentuk 1NF.
	B.  Menjadikan id_pembina sebagai primary key di tabel pembina dan menjadikannya foreign key di tabel ekskul.
	C. Membuat tabel tambahan yang menghubungkan pembina dengan ekskul secara Many-to-Many.
	D. Menghapus tabel pembina dan langsung menyimpan data pembina dalam tabel ekskul.

Jawaban: B. Menjadikan id_pembina sebagai primary key di tabel pembina dan menjadikannya foreign key di tabel ekskul.

 - Soal 3
 Dalam implementasi basis data ini, tabel siswa_ekskul memiliki dua foreign key: id_siswa dan id_ekskul. Jika terjadi skenario di mana seorang siswa keluar dari ekstrakurikuler, tetapi datanya masih diperlukan untuk laporan historis, teknik yang paling tepat untuk menjaga integritas referensial adalah:
	A.  Menggunakan constraint ON DELETE CASCADE agar saat siswa keluar, data relasinya dihapus secara otomatis.
	B. Menggunakan constraint ON DELETE SET NULL agar saat siswa keluar, id_ekskul diubah menjadi NULL.
	C. Menambahkan atribut status di tabel siswa_ekskul untuk menandai apakah siswa masih aktif atau sudah keluar dari ekstrakurikuler.
	D. Menghapus data di tabel siswa_ekskul dan menyimpannya di tabel baru khusus riwayat keikutsertaan siswa.

Jawaban: C. Menambahkan atribut status di tabel siswa_ekskul untuk menandai apakah siswa masih aktif atau sudah keluar dari ekstrakurikuler.

- Soal 4
Jika terjadi skenario di mana satu siswa mendapatkan prestasi dalam ekstrakurikuler tertentu, tetapi data siswa dihapus dari sistem karena lulus, bagaimana seharusnya hubungan antara prestasi dan siswa diatur untuk menghindari kehilangan informasi historis?
	A. Menetapkan id_siswa dalam prestasi sebagai ON DELETE CASCADE, sehingga prestasi ikut terhapus ketika siswa dihapus.
	B. Menggunakan ON DELETE SET NULL untuk id_siswa dalam prestasi, sehingga data prestasi tetap ada meskipun siswa dihapus.
	C. Menghilangkan foreign key id_siswa dari tabel prestasi agar tidak bergantung pada data siswa.
	D. Membuat tabel histori_prestasi yang menyimpan data prestasi siswa sebelum data siswa dihapus.

Jawaban: B. Menggunakan ON DELETE SET NULL untuk id_siswa dalam prestasi, sehingga data prestasi tetap ada meskipun siswa dihapus.