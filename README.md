Analisis Pendapatan Transaksi POS 2024 vs 2025

Nama: Alya Zhafira (10124124)

Hasil

| Tahun | Pendapatan |
|-------|-----------:|
| 2024  | Rp 127.406.475 |
| 2025  | Rp 135.001.100 |

Pendapatan 2025 lebih tinggi sekitar Rp 7,6 juta (kira-kira 6%) dibanding 2024.

Data dibaca sebagai teks terlebih dahulu supaya format harga yang campur tidak rusak. Setelah itu dicek missing value dan duplikat. Missing value hanya ada di kolom `kode_kasir` (261 baris). Kolom ini tidak dipakai untuk menghitung pendapatan, jadi diisi `TIDAK_DIKETAHUI` agar transaksinya tidak hilang. Ada juga 30 baris duplikat persis yang dihapus, sehingga tersisa 5.000 baris.

Berikutnya format data diseragamkan. Kolom `harga_satuan` punya dua format, yaitu `7500,00` (koma sebagai desimal) dan `13.000` (titik sebagai ribuan), dan keduanya diubah menjadi angka. Kolom `tanggal` juga punya beberapa format seperti `2025-06-02`, `26/03/2025`, dan `14-03-2024`, lalu diseragamkan dan diambil tahunnya.

Kolom `jumlah` dicek untuk mencari anomali. Pembelian di kasir normalnya 1 sampai 12 unit, sedangkan di data ditemukan nilai negatif dan nilai ekstrem sampai 2.375 unit yang dianggap salah input, jadi tidak ikut dihitung.

Untuk menghitung pendapatan, hanya transaksi berstatus `SELESAI` yang dipakai, karena `BATAL` dan `RETUR` bukan pendapatan. Pendapatan tiap baris dihitung dengan rumus `jumlah × harga_satuan × (1 − diskon_persen / 100)`. Setelah semua penyaringan, ada 4.672 transaksi yang dipakai. Terakhir, pendapatan dijumlahkan per tahun (2024 dan 2025 dipisah) dan ditampilkan dalam grafik batang.
