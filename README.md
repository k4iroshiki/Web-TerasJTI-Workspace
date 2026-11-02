# Web Akademik Mahasiswa Polije

Proyek kelompok mata kuliah Workshop Desain Aplikasi (TIF110809), Politeknik Negeri Jember.

Kita membuat website akademik sederhana dengan HTML saja. Halamannya: Login, Dashboard, KRS, KHS, Jadwal, dan Profil. Desainnya mengikuti prototype Figma dari Minggu 10.

PENTING: Semua data (nama, NIM, nilai, jadwal) adalah data karangan. Jangan memasukkan data pribadi yang asli.

---

## Isi Folder Proyek

```
web-akademik-polije/
  index.html        Halaman Login
  dashboard.html    Halaman Dashboard
  krs.html          Kartu Rencana Studi
  khs.html          Kartu Hasil Studi
  jadwal.html       Jadwal Kuliah
  profil.html       Profil Mahasiswa
  assets/
    images/         Tempat menyimpan logo dan gambar
  README.md         File yang sedang kamu baca
```

Aturan nama file:
- Pakai huruf kecil semua.
- Jangan pakai spasi.
- Akhiri dengan .html

Contoh benar: jadwal.html
Contoh salah: Jadwal Kuliah.HTML

---

## Cara Mulai (untuk yang belum pernah coding)

### Langkah 1. Siapkan alat

Kamu butuh tiga hal:
1. Browser: Chrome, Firefox, atau Edge.
2. Editor kode: Visual Studio Code (gratis), unduh di https://code.visualstudio.com
3. Akun GitHub: daftar di https://github.com, lalu kirim username kamu ke ketua supaya diundang ke repo ini.

### Langkah 2. Ambil proyek ke laptop

Cara paling mudah adalah memakai GitHub Desktop, jadi tidak perlu mengetik perintah apa pun.

1. Pasang GitHub Desktop dari https://desktop.github.com lalu login.
2. Klik menu File, lalu Clone repository.
3. Pilih repo ini, lalu klik Clone.
4. Klik tombol Open in Visual Studio Code.

### Langkah 3. Edit file

1. Buka file bagianmu di VS Code, misalnya krs.html.
2. Tulis atau ubah kodenya.
3. Simpan dengan menekan Ctrl + S.
4. Buka file itu di browser dengan klik dua kali pada file di folder.
5. Setiap habis mengubah sesuatu: simpan, lalu refresh browser dengan F5.

### Langkah 4. Kirim hasil kerjamu ke GitHub

Di GitHub Desktop:
1. Perubahanmu akan muncul di daftar sebelah kiri.
2. Tulis pesan singkat di kotak Summary, contoh: "Tambah tabel KRS".
3. Klik Commit to main.
4. Klik Push origin.

### Langkah 5. Ambil hasil kerja teman

Sebelum mulai bekerja, klik Fetch origin, lalu Pull origin. Dengan begitu file di laptopmu selalu yang terbaru.

Aturan sederhana yang harus diingat:
- Pull dulu sebelum mulai bekerja.
- Push setelah selesai bekerja.
- Edit hanya file bagianmu sendiri supaya tidak bentrok dengan teman.

---

## Kamus Istilah

| Istilah | Artinya |
|---------|---------|
| Repository (repo) | Folder proyek yang disimpan di GitHub |
| Clone | Menyalin repo dari GitHub ke laptop |
| Commit | Menyimpan perubahan lengkap dengan catatan singkat |
| Push | Mengirim perubahan dari laptop ke GitHub |
| Pull | Mengambil perubahan terbaru dari GitHub ke laptop |
| HTML | Bahasa untuk menyusun kerangka halaman web |
| Tag | Penanda HTML, contoh <p>. Biasanya ada pembuka dan penutup |
| Atribut | Keterangan tambahan di dalam tag, contoh href="krs.html" |

---

## Belajar HTML Pelan-pelan

Pelajari satu level untuk satu sesi kerja. Setelah membaca, langsung praktikkan di halaman bagianmu.

### Level 1. Kerangka dasar

Setiap halaman HTML diawali dengan kerangka ini:

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

Penjelasan:
- head berisi informasi tentang halaman. Isinya tidak tampil di layar.
- body berisi isi halaman. Semua yang tampil di layar ada di sini.
- title adalah tulisan yang muncul di tab browser.
- Tulisan di antara tanda `<!--` dan `-->` adalah komentar. Browser tidak menampilkannya.

### Level 2. Teks, daftar, tautan, dan gambar

```html
<h1>Judul Besar</h1>
<h2>Sub Judul</h2>
<p>Paragraf biasa.</p>

<ul>
  <li>Poin satu</li>
  <li>Poin dua</li>
</ul>

<a href="krs.html">Menuju halaman KRS</a>

<img src="assets/images/logo.png" alt="Logo Polije">
```

Penjelasan:
- h1 sampai h6 adalah judul. h1 yang paling besar dan paling penting.
- p adalah paragraf.
- ul adalah daftar berpoin, dan li adalah satu poin di dalamnya.
- a adalah tautan. Alamat tujuan ditulis di href.
- img adalah gambar. Isi alt adalah tulisan pengganti kalau gambar gagal tampil.

Nama file pada href harus sama persis dengan nama file tujuan.

### Level 3. Struktur halaman

Bagi halaman menjadi bagian-bagian yang jelas fungsinya:

```html
<header>Kepala halaman atau identitas aplikasi</header>
<nav>Menu navigasi</nav>
<main>Isi utama halaman</main>
<footer>Bagian penutup</footer>
```

Contoh menu navigasi:

```html
<nav>
  <ul>
    <li><a href="dashboard.html">Dashboard</a></li>
    <li><a href="krs.html">KRS</a></li>
    <li><a href="khs.html">KHS</a></li>
    <li><a href="jadwal.html">Jadwal</a></li>
    <li><a href="profil.html">Profil</a></li>
  </ul>
</nav>
```

Salin menu ini dengan isi yang sama persis ke semua halaman supaya navigasinya seragam.

### Level 4. Formulir (untuk halaman Login)

```html
<form>
  <label for="nim">NIM</label>
  <input type="text" id="nim" name="nim">

  <label for="password">Kata Sandi</label>
  <input type="password" id="password" name="password">

  <button type="submit">Masuk</button>
</form>
```

Penjelasan:
- label adalah tulisan keterangan untuk kolom isian.
- input adalah kolom isian. type="password" membuat isian tertutup titik-titik.
- Nilai for pada label harus sama dengan id pada input, supaya keduanya terhubung.
- button adalah tombol.

Catatan: form ini belum berfungsi untuk login. Pada tahap ini kita hanya membuat tampilannya.

### Level 5. Tabel (untuk KRS, KHS, dan Jadwal)

```html
<table>
  <caption>Daftar Mata Kuliah</caption>
  <thead>
    <tr>
      <th>Kode</th>
      <th>Mata Kuliah</th>
      <th>SKS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>TIF110809</td>
      <td>Workshop Desain Aplikasi</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
```

Penjelasan:
- table adalah tabelnya, dan caption adalah judul tabel.
- thead adalah bagian kepala tabel, dan tbody adalah bagian isinya.
- tr adalah satu baris.
- th adalah judul kolom, dan td adalah isi satu kotak.

Gunakan tabel hanya untuk data berbentuk baris dan kolom, bukan untuk mengatur letak seluruh halaman.

---

## Daftar Tugas Proyek

Centang (ganti [ ] menjadi [x]) kalau sudah selesai.

### Persiapan
- [ ] Semua anggota punya akun GitHub dan sudah diundang
- [ ] Semua anggota sudah clone repo dan bisa membuka di VS Code
- [ ] Tabel anggota dan pembagian halaman sudah diisi
- [ ] Setiap orang sudah mencoba commit dan push satu perubahan kecil

### Acara 1. Kerangka proyek
- [ ] index.html berisi kerangka HTML5 lengkap
- [ ] Ada heading utama dan paragraf pengantar
- [ ] File untuk semua halaman sudah dibuat
- [ ] Lembar Kerja 1 dan 2 terisi

### Acara 2. Login dan Dashboard
- [ ] Login: label dan input NIM, label dan input password, tombol Masuk
- [ ] Dashboard: header, nav, main, section, footer
- [ ] Dashboard berisi salam, ringkasan data contoh, dan menu layanan
- [ ] Lembar Kerja 3 dan 4 terisi

### Acara 3. Halaman layanan akademik
- [ ] krs.html: tabel dengan kolom kode, mata kuliah, SKS, kelas, status
- [ ] khs.html: tabel dengan kolom kode, mata kuliah, SKS, nilai, keterangan, serta IPS dan IPK contoh
- [ ] jadwal.html: tabel dengan kolom hari, waktu, mata kuliah, dosen, ruang
- [ ] profil.html: identitas mahasiswa contoh
- [ ] Lembar Kerja 5 dan 6 terisi

### Acara 4. Penyambungan dan pengujian
- [ ] Menu navigasi sama di semua halaman, dan ada tautan kembali ke Dashboard
- [ ] Semua tautan sudah diklik dan tidak ada yang rusak
- [ ] Heading, tabel, dan label sudah diperiksa
- [ ] Hasil sudah dibandingkan dengan Figma, dan perbedaannya dicatat
- [ ] Alur demo berjalan: Login, Dashboard, KRS/KHS/Jadwal/Profil, kembali ke Dashboard
- [ ] Lembar Kerja 7, Hasil dan Pembahasan, serta Kesimpulan selesai

---

## Aturan Kerja Kelompok

1. Pull dulu sebelum mulai, push setelah selesai.
2. Edit hanya file bagianmu. Kalau perlu mengubah file milik teman, kabari dia dulu.
3. Tulis pesan commit yang singkat dan jelas, contoh: "Tambah tabel jadwal" atau "Perbaiki tautan menu".
4. Jangan unggah data pribadi yang asli, seperti NIM, nilai, atau password sungguhan.
5. Kalau bingung atau ada error, tanyakan di grup dan sertakan screenshot.
6. Salah itu wajar. Semua perubahan tercatat riwayatnya dan bisa dikembalikan.

---

## Masalah yang Sering Terjadi

| Masalah | Penyebab dan cara mengatasi |
|---------|-----------------------------|
| Perubahan tidak muncul di browser | Kamu belum menyimpan (Ctrl + S) atau belum refresh (F5) |
| Klik menu muncul "halaman tidak ditemukan" | Nama file di href tidak sama persis dengan nama file tujuan. Periksa huruf besar atau kecil dan akhiran .html |
| Tulisan menjadi simbol aneh | Pastikan ada baris meta charset UTF-8 di bagian head |
| Push ditolak | Lakukan Pull dulu, lalu Push lagi |
| Muncul tulisan "conflict" | Berhenti dulu dan jangan klik sembarangan. Hubungi ketua untuk dibantu |
| Gambar tidak tampil | Periksa lokasi file di assets/images dan penulisan src |

---

## Referensi Belajar

- MDN Web Docs (Bahasa Indonesia): https://developer.mozilla.org/id/docs/Learn/HTML
- W3Schools HTML: https://www.w3schools.com/html/
- Modul praktikum Minggu 11 dari dosen