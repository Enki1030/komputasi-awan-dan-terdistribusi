# Jurnal Proses — Tugas 6

## Implementasi find_successor
- Kesalahan pertama yang ditemui (mis. lupa wrap-around di ring): ...
- Cara memperbaikinya: ...

## Skenario join/leave
- Hasil sebelum & sesudah node baru bergabung:

- sebelum : kita telah mendaftarkan kurir contohnya (kurir-001, kurir-002, kurir-003) dan nama tersebut kita hash, setelah kita hash, kita mencari mana id hash yang terdekat dengan mengikuti kondisi (ID node => key_hash).

- Sesudah `node-medan-1` masuk ke dalam *ring*, sistem akan meng-hash nama tersebut menjadi sebuah ID. Jika posisi ID node baru ini berada lebih dekat dengan ID kurir dan menggantikan posisi node penanggung jawab sebelumnya, maka `node-medan-1` akan otomatis mengambil alih kepemilikan data kurir tersebut. Informasi IP kurir akan ikut dipindahkan dan disimpan dengan aman oleh node baru untuk memastikan tidak ada data yang hilang dari sistem selama masa transisi.

- Hasil sebelum & sesudah node keluar: ...

- Sebelum: `node-jakarta-1` tidak menyimpan data kurir apa pun karena ID hash-nya bukan merupakan node terdekat (successor) bagi ID kurir mana pun yang sudah terdaftar di dalam sistem.

- Sesudah: Saat fungsi `leave("node-jakarta-1")` dijalankan, sistem memeriksa apakah ada data pada node tersebut yang perlu dialihkan. Karena node-jakarta-1 tidak memegang data kurir apa pun, node tersebut langsung keluar dari ring tanpa perlu memindahkan data ke node lain.

## Log Penggunaan AI (Level 2)

> Wajib diisi sesuai kebijakan Level 2 di [`../RUBRIK-UMUM.md`](../RUBRIK-UMUM.md). Tulis "Tidak memakai AI" pada baris pertama jika memang tidak dipakai. Hanya untuk brainstorming ide/outline — bukan untuk kode/analisis/teks akhir.

| Tanggal | Tool AI | Prompt yang diberikan | Ringkasan saran/ide AI | Bagaimana diolah jadi tulisan/kode sendiri |
|---|---|---|---|---|
| ... | ... | ... | ... | ... |
