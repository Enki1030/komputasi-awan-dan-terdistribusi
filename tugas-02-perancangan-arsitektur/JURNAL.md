# Jurnal Proses — Tugas 2

## 26 September 2026
- Opsi arsitektur yang dipertimbangkan: Menggunakan arsitektur SOA untuk semua Sistem FoodGo
- Kenapa akhirnya pilih SOA: Karena di nilai aman karena menggunakan mekanisme Request - Response. 
- Revisi diagram (versi 1 → versi 2, apa yang berubah dan kenapa): Diagram awal yang sederhana, hanya punya 4 modul dengan alur yang simpel. 

## 27 September 2026
- Opsi arsitektur yang dipertimbangkan: Menggunakan arsitektur SOA untuk semua Sistem FoodGo
- Kenapa akhirnya pilih SOA: Karena di nilai aman karena menggunakan mekanisme Request - Response. 
- Revisi diagram (versi 1 → versi 2, apa yang berubah dan kenapa): Menambahkan Beberapa Detail dan service seperti penambahan Service Kurir dan Notifikasi, dan juga alur pemotongan saldo. 

## 29 September 2026
- Opsi arsitektur yang dipertimbangkan: Merubah agar menggunakan hibrid, SOA dan Publish Subscribe. 
- Kenapa akhirnya pilih SOA & Pub-Sub:  Karena SOA dinilai aman, tetapi sangat lambat karena memerlukan pesan dua arah berupa request dan response. jadi untuk proses yang memerlukan kecepatan seperti Service dapur untuk memproses pesanan, di perlukan sistem Pub-Sub yang cepat. 
- Revisi diagram (versi 1 → versi 2, apa yang berubah dan kenapa): Merubah keseluruhan diagram nya untuk menerapkan hibrida (SOA untuk Service Pesanan, Katalog, Pembayaran yang membutuhkan keandalan dan keamanan dan Pub-Sub untuk Service Dapur dan Service Kurir yang membutuhkan kecepatan)

  
## Log Penggunaan AI (Level 2)

> Wajib diisi sesuai kebijakan Level 2 di [`../RUBRIK-UMUM.md`](../RUBRIK-UMUM.md). Tulis "Tidak memakai AI" pada baris pertama jika memang tidak dipakai. Hanya untuk brainstorming ide/outline — bukan untuk kode/analisis/teks akhir.

| Tanggal | Tool AI | Prompt yang diberikan | Ringkasan saran/ide AI | Bagaimana diolah jadi tulisan/kode sendiri |
||---|---|---|---|
| ... | ... | ... | ... | ... |
