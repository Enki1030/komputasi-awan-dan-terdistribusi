# Jurnal Proses — Tugas 6

## Implementasi find_successor
- Kesalahan pertama yang ditemui: Lupa menangani kondisi *wrap-around* ketika `key_hash` lebih besar dari seluruh ID node di ring, serta belum ada validasi kondisi saat ring masih kosong.
- Cara memperbaikinya: Mengurutkan seluruh ID node aktif dengan `sorted(self.nodes.keys())`, lalu mengambil node pertama yang bernilai `>= key_hash`. Jika tidak ada node yang memenuhi, fungsi mengembalikan node pertama (`sorted_node_ids[0]`) sebagai bentuk *wrap-around* melingkar.
- Implementasi find_successor: ```find_successor``` adalah fungsi yang di gunakan sebagai mesin pencari rute didalam topologi chord (wrap around). Alur dari fungsi ini adalah sebagai berikut:
  1. Pengurutan
     Setiap kali pencarian di panggil, fungsi akan mengambil seluruh ID server (node) yang sedang aktif dan disusun dalam urutan membesar (ascending). Node yang masih dalam bentuk string (node-jakarta-1, node-bandung-1, node-jakarta-2 dst), akan di ubah lewat fungsi ``hash_id`` menjadi angka dengan rentang 0-255. Pada fase awal, node yang sudah di ubah ke bentuk hash akan berbentuk seperti [40, 102, 136, 177] dengan urutan membesar (ascending). 
  2. Pengkondisian (node_id >= key_hash)
     Algoritma akan melakukan pengecekan menggunakan kondisi: ``node_id >= key_hash``. Sistem akan melakukan pengecekan pada deret angka node tersebut [40, 102, 136, 177], lalu sistem akan berhenti pada entitas pertama yang nilainya lebih besar atau sama dengan nilai hash pencarian (node_id >= key_hash). 
  3. Pengecekan (untuk Wrap Around mekansime)
     Jika ternyata nilai key_hash nya melampaui ID server tertinggi di dalam deretan angka itu (misal 200, sementara batas atas nya adalah 177), maka siklus pemindaian nya akan gagal dan fungsi akan secara otomatis kembali secara melingkar dengan menunjuk index pertama dari deret tersebut (sorted_nodes_ids[0]), dengan begitu tercipta cincin yang di sebut mekanisme Wrap around. 

## Skenario join/leave
- Hasil sebelum & sesudah node baru bergabung:...
- Hasil sebelum & sesudah node keluar: ...

## Log Penggunaan AI (Level 2)

> Wajib diisi sesuai kebijakan Level 2 di [`../RUBRIK-UMUM.md`](../RUBRIK-UMUM.md). Tulis "Tidak memakai AI" pada baris pertama jika memang tidak dipakai. Hanya untuk brainstorming ide/outline — bukan untuk kode/analisis/teks akhir.

| Tanggal | Tool AI | Prompt yang diberikan | Ringkasan saran/ide AI | Bagaimana diolah jadi tulisan/kode sendiri |
|---|---|---|---|---|
|25-10-2026| Gemini | Jelaskan konsep Distributed Hash Table (DHT) dan algoritma Chord dalam studi kasus penamaan IP dinamis kurir FoodGo, kenapa DNS/flat naming tidak cocok, serta cara kerja fungsi lookup, join, dan leave | Menjelaskan analogi ring topology (m=8 bit), aturan successor (N >= k), serta alasan DNS konvensional gagal menangani IP dinamis akibat keterbatasan cache TTL. | Menggunakan konsep ring topology dan aturan successor tersebut sebagai kerangka analisis untuk README.md dan dasar logika alur fungsi find_successor() pada kode chord_simulation.py. |
