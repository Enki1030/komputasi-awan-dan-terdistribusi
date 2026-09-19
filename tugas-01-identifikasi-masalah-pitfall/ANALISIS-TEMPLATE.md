# Tugas 1 — Analisis Pitfall FoodGo

**Kelompok:** Mati Tanam

| Nama | NIM | Kontribusi |
|---|---|---|
| Bezaliel Agung Trilaksana | 103072400008 | Pitfall 1 |
| Niko Rajani Syahputra | 103072400167 | Pitfall 2 |
| | | |

## Pitfall 1: [nama pitfall] — ditulis oleh [nama]

**Bukti di skenario:** [kutip/paraphrase bagian skenario]

**Kenapa ini keliru:** [penjelasan]

**Dampak ke FoodGo:** [mekanisme kegagalan konkret]

**Solusi desain awal:** [usulan solusi]

**Trade-off:** [apa yang dikorbankan/risiko dari solusi ini]

---

## Pitfall 2: Network is Reliabel — ditulis oleh Niko Rajani Syahputra

**Bukti di skenario:** "Tim menemukan bahwa kode mereka menulis asumsi seperti # network is always reliable, no need for retry "

**Kenapa ini keliru:** Programmer beranggapan bahwa jaringan mereka aman. asumsi ini muncul ketika mereka melakukan testing program secara lokal (misal manggil 1 function di _ localhost_) dan berhasil. Faktanya, jenis jenis kegagalan jaringan itu ada banyak, seperti Kabel bisa putus, router bisa crash, sinyal Wi-Fi bisa terganggu, atau pusat data bisa mati listrik. Jadi mengasumsikan bahwa network is reliable itu keliru karena programmer hanya melakukan percobaan ketika testing saja sebelum di serbu oleh request pengguna. 

**Dampak ke FoodGo:** Karena kodenya tidak bersiap jika ada gangguan internet singkat, saat koneksi putus sedetik saja, proses pesan makanan langsung batal total atau nyangkut, membuat pembeli rugi dan bingung.

**Solusi desain awal:** Buat fitur Coba Lagi Otomatis (Retry Logic). Jika panggilan ke modul pembayaran gagal, sistem akan mencoba mengirim ulang otomatis beberapa saat kemudian dengan jeda yang makin lama (Exponential Backoff).

**Trade-off:** Kalau server pembayaran sebenarnya memang sedang mati total, fitur coba lagi otomatis dari ribuan pembeli justru akan membombardir server itu dengan request yang di pending dan membuatnya makin _crash_.

---

## Pitfall 3: Single Point of Failure / Monolith — ditulis oleh Niko Rajani Syahputra

**Bukti di skenario:** "Saat trafik naik, satu server yang menangani semua modul (pesanan, pembayaran, notifikasi kurir) kewalahan karena semuanya berjalan di satu proses monolith yang sama" dan server sampai crash (mati total).

**Kenapa ini keliru:** Menyuruh satu dapur (satu server) mengerjakan semua hal sekaligus—mulai dari memasak, menerima uang, sampai memanggil kurir—tanpa ada pembagian ruang kerja.

**Dampak ke FoodGo:** Saat promo jam makan siang tiba dan modul pembayaran macet, seluruh dapur (server) ikut terbakar dan mati total. Padahal pembeli yang cuma mau lihat-lihat menu pun jadi tidak bisa buka aplikasi sama sekali.

**Solusi desain awal:** Pisahkan Tugas ke Server Berbeda (Dekomposisi Layanan / Microservices). Modul pesanan, pembayaran, dan kirim pesan ke kurir dipisah rumahnya. Untuk tugas yang tidak buru-buru (seperti kirim notifikasi ke kurir), gunakan Papan Antrean Pesan (Message Queue) agar bisa dikerjakan belakangan tanpa membebani proses utama.

**Trade-off:** Biaya sewa server jadi lebih mahal dan cara mengelolanya jadi jauh lebih rumit karena tim harus merawat banyak rumah/server sekaligus alih-alih cuma satu.

---

## Kesimpulan Kelompok

[Ringkasan: jika FoodGo memperbaiki ketiga pitfall ini, apa arsitektur yang disarankan secara garis besar? Kaitkan dengan Tugas 2.]
