# Teras JTI: Aplikasi Reservasi Co-working Space

Proyek kelompok 4 "No Bug No Cry", mata kuliah Workshop Desain Aplikasi (TIF110809), Politeknik Negeri Jember.

Kita membuat website reservasi co-working space Teras JTI memakai **HTML saja** (belum ada CSS dan JavaScript). Tampilan dan isi halaman mengikuti prototype Figma hi-fi dari Minggu 10.

> **PENTING:** semua data (nama, NIM, tanggal, ruang) adalah data karangan. Jangan memasukkan data pribadi yang asli.

---

## Cara Memakai README Ini

README ini adalah **kompas dan kamus** kalian saat ngoding atau memakai Git. Jangan dibaca sekali lalu ditinggal, buka lagi setiap kali bingung.

| Kamu sedang... | Buka bagian |
|---|---|
| Baru mulai dan belum tahu harus ngapain? | [1. Kompas Kerja](#1-kompas-kerja) |
| Bingung halaman apa saja yang harus dibuat? | [2. Peta Proyek](#2-peta-proyek) |
| Mau pakai Git atau GitHub Desktop? | [3. Panduan Git](#3-panduan-git) |
| Mau menulis kode HTML? | [4. Panduan HTML](#4-panduan-html) |
| Mau menulis kode yang rapi dan seragam? | [5. Aturan Penulisan Kode](#5-aturan-penulisan-kode) |
| Ada error atau hasil tidak sesuai? | [6. Masalah yang Sering Terjadi](#6-masalah-yang-sering-terjadi) |
| Mau tahu arti sebuah istilah? | [7. Kamus Istilah](#7-kamus-istilah) |

---

## 1. Kompas Kerja

Setiap kali mau bekerja, ikuti urutan ini:

1. **Pull**: ambil perubahan terbaru dari teman.
2. **Buka** file bagianmu di VS Code.
3. **Tulis atau ubah** kodenya, lalu simpan dengan `Ctrl + S`.
4. **Cek di browser**, lalu refresh dengan `F5`.
5. **Commit** dengan pesan singkat.
6. **Push**: kirim ke GitHub.

Tiga aturan emas:

- Pull dulu sebelum mulai, push setelah selesai.
- Edit hanya file bagianmu. Kalau perlu mengubah file teman, kabari dia dulu.
- Kalau ragu atau muncul tulisan `conflict`, berhenti dan tanya ketua. Jangan klik sembarangan.

### Pembagian halaman

| Anggota | Peran | Halaman yang dikerjakan |
|---|---|---|
| Farrel Ananta Firmansyah | Ketua | |
| Deva Riski Anjani | Anggota | |
| Achmad Solikhin (Lihin) | Anggota | |
| Firsty Maylisha Putri | Anggota | |
| Wildzan Suryabuana Jarot | Anggota | |

---

## 2. Peta Proyek

### Isi folder

```
nama-folder-proyek/
  index.html        Halaman Login
  dashboard.html    Halaman utama setelah login
  reservasi.html    Form reservasi dan tabel ketersediaan
  riwayat.html      Riwayat reservasi
  jadwal.html       Jadwal dan ketersediaan Teras JTI
  profil.html       Profil pengguna
  tentang.html      Tentang kelompok kita
  assets/
    images/         Logo dan gambar
  README.md         File yang sedang kamu baca
```

### Isi tiap halaman

| File | Fungsi | Isi yang harus ada |
|---|---|---|
| `index.html` | Login | Judul, teks petunjuk, label dan input NIM, label dan input kata sandi, tombol Masuk, tautan bantuan |
| `dashboard.html` | Beranda | Identitas aplikasi, salam untuk pengguna contoh, ringkasan reservasi, menu ke halaman lain |
| `reservasi.html` | Membuat reservasi | Form pilih tanggal, jam, dan ruang, plus tabel ketersediaan ruang |
| `riwayat.html` | Riwayat | Tabel dengan kolom kode, tanggal, ruang, status, keterangan |
| `jadwal.html` | Jadwal | Tabel dengan kolom hari, jam, ruang, status ketersediaan |
| `profil.html` | Profil | Nama contoh, NIM contoh, program studi, dalam bentuk daftar |
| `tentang.html` | Tentang kami | Profil singkat kelompok dan tujuan aplikasi |

### Aturan yang berlaku di semua halaman

- Setiap halaman memakai kerangka HTML5 yang sama (lihat [Level 1](#level-1-kerangka-dasar)).
- Menu navigasi **sama persis** di semua halaman, dan ada jalan kembali ke Dashboard.
- Setiap `input` punya `label`, dan keduanya dihubungkan lewat `for` dan `id`.
- Judul memakai `h1` sampai `h6` secara berurutan, jangan melompat.
- Setiap gambar punya `alt`.
- Nama file: huruf kecil, tanpa spasi, berakhiran `.html`. Contoh benar: `riwayat.html`. Contoh salah: `Riwayat Reservasi.HTML`.

### Alur yang akan didemokan

Login, Dashboard, Reservasi / Riwayat / Jadwal / Profil, lalu kembali ke Dashboard.

Login belum berfungsi pada tahap ini. Tombol Masuk hanya tampilan.

---

## 3. Panduan Git

### Persiapan satu kali

1. Buat akun di https://github.com, lalu kirim username-mu ke ketua supaya diundang ke repo.
2. Pasang **GitHub Desktop** dari https://desktop.github.com, lalu login.
3. Pasang **Visual Studio Code** dari https://code.visualstudio.com
4. Di GitHub Desktop: menu **File**, **Clone repository**, pilih repo ini, klik **Clone**.
5. Klik **Open in Visual Studio Code**.

### Kerja sehari-hari (GitHub Desktop)

| Tujuan | Yang diklik |
|---|---|
| Ambil perubahan teman | **Fetch origin**, lalu **Pull origin** |
| Melihat apa yang kamu ubah | Daftar file di sebelah kiri |
| Menyimpan perubahan | Tulis pesan di kotak **Summary**, lalu **Commit to main** |
| Mengirim ke GitHub | **Push origin** |

### Pesan commit yang baik

Singkat, jelas, dan menyebut apa yang dikerjakan.

- Bagus: `Tambah tabel riwayat reservasi`, `Perbaiki tautan menu di jadwal`
- Kurang bagus: `update`, `fix`, `asdf`

### Kalau lebih suka terminal

| Tujuan | Perintah |
|---|---|
| Ambil perubahan terbaru | `git pull` |
| Lihat file yang berubah | `git status` |
| Siapkan semua perubahan | `git add .` |
| Simpan perubahan | `git commit -m "pesan singkat"` |
| Kirim ke GitHub | `git push` |

### Kalau ada masalah di Git

| Masalah | Yang dilakukan |
|---|---|
| Push ditolak | Pull dulu, lalu push lagi |
| Muncul tulisan `conflict` | Berhenti, jangan klik sembarangan |
| Salah commit atau salah ubah file | Tenang, semua riwayat tercatat dan bisa dikembalikan. |

---

## 4. Panduan HTML

Pelajari satu level per sesi kerja, lalu langsung praktikkan di halaman bagianmu.

### Level 1. Kerangka dasar

Setiap halaman diawali dengan kerangka ini:

```html
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Judul di Tab Browser</title>
</head>
<body>
  <!-- Semua yang tampil di layar ditulis di sini -->
  <h1>Judul Halaman</h1>
  <p>Ini paragraf.</p>
</body>
</html>
```

- `head` berisi informasi tentang halaman dan tidak tampil di layar.
- `body` berisi semua yang tampil di layar.
- `title` adalah tulisan di tab browser.
- Tulisan di antara `<!--` dan `-->` adalah komentar. Browser tidak menampilkannya, jadi pakai untuk catatan.

### Level 2. Teks, daftar, tautan, dan gambar

```html
<h1>Judul Besar</h1>
<h2>Sub Judul</h2>
<p>Paragraf biasa.</p>

<ul>
  <li>Poin satu</li>
  <li>Poin dua</li>
</ul>

<a href="reservasi.html">Buat Reservasi</a>

<img src="assets/images/logo.png" alt="Logo Teras JTI">
```

- `h1` sampai `h6` adalah judul. `h1` paling besar dan paling penting, satu halaman cukup satu `h1`.
- `ul` adalah daftar berpoin, `li` adalah satu poin di dalamnya. Untuk daftar bernomor pakai `ol`.
- `a` adalah tautan, alamat tujuan ditulis di `href`.
- `img` adalah gambar. `alt` adalah tulisan pengganti kalau gambar gagal tampil.
- Nama file di `href` harus sama persis dengan nama file tujuan.

### Level 3. Struktur halaman

Bagi halaman menjadi bagian yang jelas fungsinya:

```html
<header>Kepala halaman atau identitas aplikasi</header>
<nav>Menu navigasi</nav>
<main>
  <section>Satu kelompok isi</section>
</main>
<footer>Bagian penutup</footer>
```

Menu navigasi untuk dipakai di semua halaman:

```html
<nav>
  <ul>
    <li><a href="dashboard.html">Dashboard</a></li>
    <li><a href="reservasi.html">Reservasi</a></li>
    <li><a href="riwayat.html">Riwayat</a></li>
    <li><a href="jadwal.html">Jadwal</a></li>
    <li><a href="profil.html">Profil</a></li>
    <li><a href="tentang.html">Tentang</a></li>
  </ul>
</nav>
```

Salin dengan isi yang sama persis ke semua halaman (kecuali Login) supaya navigasinya seragam.

### Level 4. Formulir

Dipakai di halaman Login dan Reservasi.

```html
<form>
  <label for="nim">NIM</label>
  <input type="text" id="nim" name="nim">

  <label for="password">Kata Sandi</label>
  <input type="password" id="password" name="password">

  <button type="submit">Masuk</button>
</form>
```

Pilihan dari daftar (misalnya memilih ruang di halaman Reservasi):

```html
<label for="ruang">Pilih Ruang</label>
<select id="ruang" name="ruang">
  <option value="meja-a">Meja A</option>
  <option value="meja-b">Meja B</option>
</select>
```

- `label` adalah keterangan untuk kolom isian.
- Nilai `for` pada `label` harus sama dengan `id` pada `input`, supaya keduanya terhubung.
- `type="password"` membuat isian tertutup titik-titik.
- Form ini belum berfungsi. Pada tahap ini kita hanya membuat tampilannya.

### Level 5. Tabel

Dipakai di halaman Reservasi, Riwayat, dan Jadwal.

```html
<table>
  <caption>Riwayat Reservasi</caption>
  <thead>
    <tr>
      <th>Kode</th>
      <th>Tanggal</th>
      <th>Ruang</th>
      <th>Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>RSV-001</td>
      <td>10 November 2026</td>
      <td>Meja A</td>
      <td>Disetujui</td>
    </tr>
  </tbody>
</table>
```

- `caption` adalah judul tabel.
- `thead` adalah kepala tabel, `tbody` adalah isinya.
- `tr` adalah satu baris, `th` adalah judul kolom, `td` adalah satu kotak isi.
- Pakai tabel hanya untuk data berbentuk baris dan kolom, bukan untuk mengatur letak seluruh halaman.

### Level 6. Daftar identitas (untuk Profil)

```html
<dl>
  <dt>Nama</dt>
  <dd>Mahasiswa Contoh</dd>
  <dt>NIM</dt>
  <dd>E00000000</dd>
</dl>
```

`dl` adalah daftar deskripsi, `dt` adalah nama bagian, `dd` adalah isinya. Boleh juga memakai `ul` biasa.

---

## 5. Aturan Penulisan Kode

1. Gunakan **huruf kecil** untuk nama tag, atribut, dan nama file.
2. Setiap tag yang dibuka harus ditutup, kecuali `img` dan `br`.
3. **Rapikan indentasi**: isi di dalam sebuah tag digeser 2 spasi ke kanan, supaya mudah dibaca.
4. Kasih **komentar** `<!-- ... -->` di bagian yang penting, terutama kalau kurang paham.
5. Nama `id` dan `name` pakai huruf kecil tanpa spasi, contoh: `tanggal-reservasi`.
6. Jangan memakai data asli. Pakai nama, NIM, dan tanggal karangan.
7. Jangan mengubah tampilan dengan trik tabel atau spasi kosong. CSS baru dipelajari nanti.

---

## 6. Masalah yang Sering Terjadi

| Masalah | Penyebab dan cara mengatasi |
|---|---|
| Perubahan tidak muncul di browser | Belum disimpan (`Ctrl + S`) atau belum refresh (`F5`) |
| Klik menu muncul "halaman tidak ditemukan" | Nama file di `href` tidak sama persis dengan nama file tujuan. Periksa huruf besar atau kecil dan akhiran `.html` |
| Tulisan menjadi simbol aneh | Pastikan ada baris `<meta charset="UTF-8">` di bagian `head` |
| Gambar tidak tampil | Periksa lokasi file di `assets/images` dan penulisan `src` |
| Tampilan berantakan setelah mengedit | Biasanya ada tag yang lupa ditutup. Cek pasangan tag pembuka dan penutup |
| Push ditolak | Pull dulu, lalu push lagi |
| Muncul tulisan `conflict` | Berhenti dan cek bareng |

---

## 7. Kamus Istilah

### Istilah Git

| Istilah | Artinya |
|---|---|
| Repository (repo) | Folder proyek yang disimpan di GitHub |
| Clone | Menyalin repo dari GitHub ke laptop |
| Commit | Menyimpan perubahan lengkap dengan catatan singkat |
| Push | Mengirim perubahan dari laptop ke GitHub |
| Pull | Mengambil perubahan terbaru dari GitHub ke laptop |
| Fetch | Mengecek apakah ada perubahan baru di GitHub (belum mengambilnya) |
| Conflict | Dua orang mengubah bagian yang sama, sehingga Git tidak tahu mana yang dipakai |

### Istilah HTML

| Istilah | Artinya |
|---|---|
| HTML | Bahasa untuk menyusun kerangka halaman web |
| Tag | Penanda HTML, contoh `<p>`. Biasanya ada pembuka `<p>` dan penutup `</p>` |
| Elemen | Satu tag lengkap beserta isinya |
| Atribut | Keterangan tambahan di dalam tag, contoh `href="jadwal.html"` |
| Semantik | Tag yang namanya menjelaskan fungsinya, contoh `header`, `nav`, `main`, `footer` |
| Tautan relatif | Alamat tujuan yang ditulis berdasarkan lokasi file saat ini, contoh `href="jadwal.html"` |
| Komentar | Catatan di kode yang tidak tampil di browser: `<!-- catatan -->` |

---

## Referensi Belajar

- MDN Web Docs (Bahasa Indonesia): https://developer.mozilla.org/id/docs/Learn/HTML
- W3Schools HTML: https://www.w3schools.com/html/
- Modul praktikum Minggu 11 dari dosen