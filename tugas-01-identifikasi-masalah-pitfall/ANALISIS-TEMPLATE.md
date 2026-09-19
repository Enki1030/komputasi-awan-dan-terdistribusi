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

**Kenapa ini keliru:** Programmer beranggapan bahwa jaringan mereka aman. asumsi ini muncul ketika mereka melakukan testing pada program (misal manggil 1 function) dan berhasil. Faktanya, jenis jenis kegagalan jarinagn itu ada banyak, seperti Kabel bisa putus, router bisa crash, sinyal Wi-Fi bisa terganggu, atau pusat data bisa mati listrik. Jadi mengasumsikan bahwa network is reliable itu keliru karena programmer hanya melakukan percobaan ketika testing saja sebelum di serbu oleh request pengguna. 

**Dampak ke FoodGo:** [mekanisme kegagalan konkret]

**Solusi desain awal:** [usulan solusi]

**Trade-off:** [apa yang dikorbankan/risiko dari solusi ini]

---

## Pitfall 3: [nama pitfall] — ditulis oleh [nama]

(ulangi struktur di atas)

---

## Kesimpulan Kelompok

[Ringkasan: jika FoodGo memperbaiki ketiga pitfall ini, apa arsitektur yang disarankan secara garis besar? Kaitkan dengan Tugas 2.]
