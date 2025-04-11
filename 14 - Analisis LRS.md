| No  | Nama                 | Skor Keaktifan | Peran                          |
| --- | -------------------- | -------------- | ------------------------------ |
| 1   | Rezky Awalya         | 3              | Mengerjakan Nomor 1 + bagian e |
| 2   | A. Ashadelah M.A     | 3              | Mengerjakan Nomor 2 bagian a   |
| 3   | Fatsa Akhwani        | 3              | Mengerjakan Nomor 2 bagian b   |
| 4   | Nur Afni Ramadani    | 3              | Mengerjakan Nomor 2 bagian c   |
| 5   | Nur Inayah Athaillah | 2              | Sakit, mohon doanya pak.       |
| 6   | Siti Nur Hasiza.A    | 3              | Mengerjakan Nomor 2 bagian d   |

1. mengapa tabel siswa dan tabel kartu pelajar terpisah menjadi dua tabel dan dihubungkan secara 1: 1, berikan pula contoh yang lain yang semisal seperti kasus tersebut! berikan penjelasannya!

	Tabel **Siswa** dan **Kartu_Pelajar** dipisahkan karena walaupun setiap siswa hanya memiliki satu kartu pelajar (hubungan 1:1), data kartu pelajar bisa bersifat opsional, memiliki atribut khusus, atau memerlukan perlakuan keamanan yang berbeda. Pemisahan ini membantu menjaga struktur data tetap modular, fleksibel, dan mudah dikelola.
	**Contoh lain:**  
	Misalnya, tabel **Ekskul** dan **Detail_Ekskul**.
	- **Ekskul:** Menyimpan data dasar tentang ekstrakurikuler, seperti nama dan jenis kegiatan.
	- **Detail_Ekskul:** Menyimpan informasi tambahan seperti jadwal, lokasi, dan kontak, yang meskipun hanya satu per ekskul, dipisahkan untuk menjaga kejelasan data dan memudahkan pembaruan informasi detail.

2. 5 bentuk kardinalitas di database masing-masing sesuai dengan konsep LRS Jika tabel memiliki semua kardinalitas, maka 2 nya bisa bebas ntahkah 1:1, 1:N, N:N

	a. **One-to-One (1:1):**  
	Setiap record di Tabel A berhubungan dengan tepat satu record di Tabel B.  
	_Contoh:_ Tabel **Siswa** dan **Kartu_Pelajar** dipisah karena setiap siswa hanya memiliki satu kartu pelajar. Ini memungkinkan data kartu pelajar dikelola secara independen, misalnya jika ada informasi tambahan atau aturan keamanan khusus.
	
	b. **One-to-Many (1:N):**  
	Satu record di Tabel A dapat berhubungan dengan banyak record di Tabel B, sedangkan setiap record di Tabel B hanya terhubung ke satu record di Tabel A.  
	_Contoh:_ Tabel **Pembina** dan **Ekskul**, di mana satu kelas memiliki banyak siswa.
	
	c. **Many-to-Many (N:N):**  
	Banyak record di Tabel A dapat berhubungan dengan banyak record di Tabel B. Relasi ini biasanya dipecah melalui tabel relasi (junction table).  
	_Contoh:_ Tabel **Siswa** dan **Ekskul** dihubungkan melalui tabel **Siswa_Ekskul**, karena seorang siswa bisa mengikuti beberapa ekskul dan satu ekskul bisa diikuti banyak siswa.
	
	d. **One-to-One (1:1):**  
	Setiap record di Tabel A berhubungan dengan tepat satu record di Tabel B.  
	_Contoh:_ **Ekskul** dan **Detail_Ekskul** dipisah karena setiap ekstrakurikuler memiliki satu set data detail yang spesifik, seperti jadwal, lokasi, atau kontak. Pemisahan ini memungkinkan data detail dikelola secara independen sehingga jika ada perubahan pada informasi detail, pembaruan dapat dilakukan dengan mudah tanpa mempengaruhi data utama di tabel **Ekskul**.
	
	e. **One-to-Many (1:N):**  
	Satu record di Tabel A dapat berhubungan dengan banyak record di Tabel B, sedangkan setiap record di Tabel B hanya terhubung ke satu record di Tabel A.
	_Contoh:_ Dalam hal ini, satu ekstrakurikuler dapat meraih banyak prestasi (misalnya, juara lomba, penghargaan akademis, dsb.), namun setiap pencapaian (prestasi) hanya terkait dengan satu ekstrakurikuler tertentu.