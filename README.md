# Lab6Web - Praktikum Pemrograman Web Pertemuan 7

PAHMI DWIKA FAHLEVI/312510389/ I253C
## Tujuan
Memahami DOM, event handling dengan `addEventListener()`, serta validasi form menggunakan JavaScript.

## Struktur File
```
Lab6Web/
├── README.md
├── latihan6/        (To-do List)
│   ├── index.html
│   ├── style.css
│   └── script.js
└── miniproject/     (Form Pendaftaran Workshop)
    ├── index.html
    ├── style.css
    └── script.js
```

## Cara Menjalankan
Buka `index.html` di masing-masing folder dengan browser (atau gunakan Live Server di VS Code).

## Langkah Kerja
1. Membuat repository `Lab6Web`.
2. Mengerjakan Latihan 6 (To-do List) beserta tombol hapus.
3. Mengerjakan mini project form workshop: validasi, hitung karakter, ringkasan langsung, pesan error/sukses, tombol reset.
4. Mengerjakan eksperimen mandiri nomor 1-5.
5. Commit dan push ke GitHub.

## Screenshot
- Latihan 6: tugas ditambahkan, ditandai selesai, dihapus
- Form: kondisi tidak valid (nama kosong/pendek, email salah, sesi belum dipilih)
- Form: kondisi valid dan pesan sukses
(Tempel gambar di sini: `![deskripsi](screenshots/nama-file.png)`)

## Eksperimen G5 (script tanpa defer di head)
Browser menjalankan script saat HTML masih dibaca, sehingga elemen di body belum ada.
`document.getElementById(...)` mengembalikan `null`, lalu `addEventListener` memicu
`TypeError: Cannot read properties of null`. Solusi: pakai atribut `defer`, atau letakkan script di akhir body.

## Jawaban Pertanyaan Evaluasi
1. **DOM** (Document Object Model) adalah representasi dokumen HTML sebagai pohon objek yang bisa diakses dan diubah JavaScript. Manfaatnya: mengubah isi, atribut, dan gaya halaman secara dinamis tanpa memuat ulang.
2. `getElementById()` mengambil satu elemen berdasarkan id. `querySelector()` mengambil elemen pertama yang cocok dengan selector CSS. `querySelectorAll()` mengambil semua elemen yang cocok (NodeList).
3. `addEventListener()` mendaftarkan fungsi yang dijalankan saat suatu event terjadi. Contoh event: `click`, `input`, `submit` (juga `change`, `keydown`).
4. `event.preventDefault()` mencegah form dikirim dan halaman dimuat ulang, sehingga validasi JavaScript bisa dijalankan dulu.
5. `textContent` menampilkan string sebagai teks biasa sehingga aman. `innerHTML` mem-parsing string sebagai HTML, sehingga input pengguna berisi `<script>` atau `<img onerror>` bisa memicu XSS.
6. `classList.toggle("nama")` menambah class jika belum ada dan menghapusnya jika sudah ada, sehingga tampilan berganti hanya dengan satu baris kode dan CSS yang mengatur gayanya.
7. Skenario pengujian: (a) semua kolom kosong, (b) nama 1-2 karakter, (c) email tanpa `@` atau domain, (d) sesi belum dipilih, (e) semua data valid, (f) tombol reset setelah error tampil.
