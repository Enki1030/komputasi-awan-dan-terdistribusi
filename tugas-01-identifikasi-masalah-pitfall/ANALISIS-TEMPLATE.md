# Tugas 1 — Analisis Pitfall FoodGo

**Kelompok:** [nama kelompok]

| Nama | NIM | Kontribusi |
|---|---|---|
| [nama 1] | [nim] | [pitfall/bagian yang dikerjakan] |
| [nama 2] | [nim] | [pitfall/bagian yang dikerjakan] |
| [nama 3] | [nim] | [pitfall/bagian yang dikerjakan] |

## Pitfall 1: Latency is zero — ditulis oleh Bezaliel Agung Trilaksana

**Bukti di skenario:** "Tim menemukan bahwa kode mereka menulis asumsi seperti # network is always reliable, no need for retry dan tidak ada timeout sama sekali pada pemanggilan antar service (modul pesanan memanggil modul pembayaran dan menunggu tanpa batas waktu)." dan juga "Aplikasi jadi sangat lambat, beberapa permintaan timeout."

**Kenapa ini keliru:** Dikarenakan data tidak dapat melakukan perjalanan lebih cepat dari kecepatan cahaya. Semakin jauh jaraknya, semakin tinggi latensinya.Apalagi mengasumsikan tidak ada timeout juga itu salah sebab pada saat bagian di jam siang atau promo itu terkadang selalu ada timeout dikarenakan servernya sangat sibuk untuk menerima berbagai macam data dari pengguna.  

**Dampak ke FoodGo:** mengalami kegagalan sistem saat pesanan melonjak (misalnya jam makan siang atau saat promo besar).

**Solusi desain awal:** memberikan waktu timeout yang ideal untuk menquery data tersebut kurang lebih 3 detik.Memberikan caching supaya memastikan data yang sering diakses tersedia tanpa kueri database berulang   

**Trade-off:** Mungkin ada beberapa pesanan yang gagal di pesan, dikarenakan timeout yang tidak lama dikarenakan latency yang tinggi.Tinggi nya file aplikasi tersebut dikarenakan chache nya sangat besar filenya 

---

## Pitfall 2: [nama pitfall] — ditulis oleh [nama]

(ulangi struktur di atas)

---

## Pitfall 3: [nama pitfall] — ditulis oleh [nama]

(ulangi struktur di atas)

---

## Kesimpulan Kelompok

[Ringkasan: jika FoodGo memperbaiki ketiga pitfall ini, apa arsitektur yang disarankan secara garis besar? Kaitkan dengan Tugas 2.]
