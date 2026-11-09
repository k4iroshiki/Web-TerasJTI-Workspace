# Teras JTI - Web Reservasi Co-Working Space (Versi HTML)

Proyek Kelompok 4 (NoBugNoCry), Golongan C, D4 Teknik Informatika, Jurusan Teknologi Informasi, Politeknik Negeri Jember.
Mata kuliah Workshop Desain Aplikasi (TIF110809), BKPM Minggu 11.

Repo ini berisi website statis (HTML saja) yang dibuat dari prototype Figma aplikasi Teras JTI (hasil BKPM Minggu 10) dan laporan perancangan Kelompok 4.

Catatan penting:
- Semua data di website ini adalah data contoh (fiktif). Jangan memasukkan data pribadi asli, password asli, atau bukti pembayaran asli.
- Form Login, Registrasi, dan Pembayaran hanya berupa tampilan. Belum ada proses login atau pembayaran.
---

## Daftar Isi

1. [Tentang Proyek](#1-tentang-proyek)
2. [Anggota dan Pembagian Tugas](#2-anggota-dan-pembagian-tugas)
3. [Peta Halaman: dari Figma ke HTML](#3-peta-halaman-dari-figma-ke-html)
4. [Struktur Folder](#4-struktur-folder)
5. [Alur Kerja Git Sehari-hari](#5-alur-kerja-git-sehari-hari)
6. [Panduan HTML untuk Proyek Ini](#6-panduan-html-untuk-proyek-ini)
7. [Spesifikasi Isi Tiap Halaman](#7-spesifikasi-isi-tiap-halaman)
8. [Data Contoh Baku](#8-data-contoh-baku)
9. [Aturan Konsistensi](#9-aturan-konsistensi)
10. [Rencana 7 Hari](#10-rencana-7-hari)
11. [Papan Progres](#11-papan-progres)
12. [Pengujian Akhir](#12-pengujian-akhir)
13. [Hasil yang Dikumpulkan ke Dosen](#13-hasil-yang-dikumpulkan-ke-dosen)
14. [Masalah yang Sering Terjadi](#14-masalah-yang-sering-terjadi)
15. [Catatan untuk Pengembangan Mobile](#15-catatan-untuk-pengembangan-mobile)
16. [Kamus Istilah dan Referensi](#16-kamus-istilah-dan-referensi)

---

## 1. Tentang Proyek

**Teras JTI** adalah aplikasi untuk memesan (reservasi) tempat di Teras JTI secara online. Pengguna tidak perlu datang langsung atau menunggu konfirmasi manual dari pengelola. Untuk tempat berbayar, pengguna membayar uang muka (DP) lewat QRIS atau transfer. Tempat yang tidak berbayar langsung terkonfirmasi.

Masalah yang ingin diselesaikan (dari wawancara dan observasi):
1. Reservasi masih manual atau datang langsung, sehingga jadwal bisa bentrok.
2. Pengantaran pesanan menu mini cafe terlambat 1 sampai 2 kali per hari.

### Yang dikerjakan di Minggu 11

Fokus kita adalah **alur reservasi pengguna (US-01) dan pembayaran DP (US-04)**, karena itulah yang sudah dirancang di Figma (22 layar). Alur pengelola dan mini cafe belum punya layar di Figma, jadi tidak dikerjakan di tahap ini.

| Dikerjakan | Tidak dikerjakan (tahap berikutnya) |
|------------|--------------------------------------|
| Login dan Registrasi | Halaman pengelola dan laporan |
| Beranda dan daftar tempat | Halaman mini cafe (staf) |
| Detail tempat dan ketersediaan slot | Proses login/pembayaran sungguhan |
| Form reservasi (gratis dan berbayar) | Tampilan CSS seperti Figma |
| Hasil reservasi dan pembayaran DP | Interaksi JavaScript |
| Riwayat dan pembatalan, Profil | Versi aplikasi mobile |

### Keterkaitan dengan modul dosen

Modul Minggu 11 memakai contoh "Web Akademik" (Login, Dashboard, KRS, KHS, Jadwal, Profil). Lembar Kerja 3 pada modul meminta pemetaan "sesuaikan dengan hasil desain", jadi kelompok kita menerapkan kompetensi yang sama (struktur HTML5, semantik, form, tabel, daftar, tautan) pada aplikasi Teras JTI. Padanannya:

| Contoh di modul | Padanan di proyek kita |
|-----------------|------------------------|
| index.html (Login) | index.html (Login) |
| dashboard.html | dashboard.html (Beranda) |
| krs.html, khs.html, jadwal.html (tabel) | ketersediaan.html, riwayat.html, pembayaran-dp.html (tabel) |
| profil.html | profil.html |

Kalau dosen meminta nama file atau halaman lain (misalnya halaman "Tentang Kami"), tinggal tambahkan.

---

## 2. Anggota dan Pembagian Tugas

| No | Nama | NIM | Jobdesk | Halaman yang dikerjakan |
|----|------|-----|---------|-------------------------|
| 1 | Farrel Ananta Firmansyah | E41261072 | Design Engineer / Full-Stack Generalist | dashboard.html, struktur repo, navigasi seragam, review akhir |
| 2 | Wildzan Suryabuana Jarot | E41260847 | Frontend Developer | reservasi.html, hasil-reservasi.html |
| 3 | Achmad Solikhin | E41260957 | UI/UX Designer, QA / Tester | detail-tempat.html, ketersediaan.html, pengujian (Lembar Kerja 4 dan 7) |
| 4 | Deva Riski Anjani | E41260874 | Project Manager | riwayat.html, profil.html, papan progres, lembar kerja dan laporan |
| 5 | Firsty Maylisha Putri | E41261055 | Backend Developer | index.html (Login), registrasi.html, pembayaran-dp.html |

Pembagian di atas adalah usulan awal berdasarkan jobdesk dan bisa diubah lewat kesepakatan kelompok. Bobot pekerjaan sengaja diseimbangkan: halaman form diberikan ke Firsty dan Wildzan, halaman tabel dan daftar ke Achmad dan Deva.

Aturan kepemilikan file:
- Setiap file HTML dipegang satu orang. Hanya pemegangnya yang mengedit file itu.
- Mau mengubah file orang lain? Minta orangnya yang mengubah, atau kabari di grup dulu.
- Hanya Deva yang mengedit README.md (terutama papan progres), supaya tidak bentrok.

---

## 3. Peta Halaman: dari Figma ke HTML

Prototype Figma punya 22 layar. Satu file HTML bisa memuat beberapa layar yang masih satu halaman (misalnya layar normal dan layar galat). Karena belum belajar JavaScript, **kondisi galat dan kosong ditampilkan sebagai bagian terpisah di halaman yang sama** dengan judul jelas, misalnya "Contoh Tampilan: Login Gagal". Nanti dengan JavaScript, bagian-bagian itu bisa disembunyikan dan ditampilkan sesuai kondisi.

| File HTML | Layar Figma | Isi | PIC |
|-----------|-------------|-----|-----|
| index.html | 1 Login, 2 Login Gagal | Form login dan contoh pesan gagal | Firsty |
| registrasi.html | 3 Registrasi, 4 Registrasi Kolom Kosong | Form daftar dan contoh pesan galat | Firsty |
| dashboard.html | 5 Beranda, 6 Beranda Banner Notifikasi | Pencarian, filter, daftar tempat, contoh notifikasi | Farrel |
| detail-tempat.html | 7 Detail Tempat | Foto, fasilitas, jam operasional, aturan | Achmad |
| ketersediaan.html | 8 dan 9 Ketersediaan Slot | Pilih tanggal dan jam, legenda | Achmad |
| reservasi.html | 10, 11, 12, 13 Form Reservasi | Form, info DP, contoh validasi dan bentrok | Wildzan |
| hasil-reservasi.html | 14, 15, 17 Hasil | Sukses gratis, menunggu pembayaran, DP lunas | Wildzan |
| pembayaran-dp.html | 16 Pembayaran DP | Rincian biaya, metode, unggah bukti | Firsty |
| riwayat.html | 18, 19, 20, 21 Riwayat | Tabel reservasi, dialog batal, ditolak, kosong | Deva |
| profil.html | 22 Profil | Data pengguna contoh dan menu | Deva |

### Alur perpindahan halaman

```
index.html (Login)
   |-- "Belum punya akun? Daftar" --> registrasi.html --> kembali ke index.html
   |-- Login (simulasi) -----------> dashboard.html
                                        |-- Lihat Jadwal --> detail-tempat.html --> ketersediaan.html
                                        |                                              |
                                        |                                              v
                                        |                                        reservasi.html
                                        |                                              |
                                        |                      tempat gratis           |        tempat berbayar
                                        |                            v                 |              v
                                        |                   hasil-reservasi.html <-----+--- pembayaran-dp.html
                                        |-- Riwayat --> riwayat.html
                                        |-- Profil  --> profil.html --> Keluar --> index.html
```

---

## 4. Struktur Folder

```
Web-TerasJTI-Workspace/
  index.html
  registrasi.html
  dashboard.html
  detail-tempat.html
  ketersediaan.html
  reservasi.html
  hasil-reservasi.html
  pembayaran-dp.html
  riwayat.html
  profil.html
  assets/
    images/          (logo, foto Ruang Diskusi dan Aula Mini)
  docs/              (laporan perancangan, lembar kerja, screenshot Figma)
  README.md
```

Aturan nama file: huruf kecil semua, tanpa spasi, pakai tanda hubung (-), berakhiran .html. Contoh benar: detail-tempat.html. Contoh salah: Detail Tempat.HTML.

Simpan di folder docs:
- Laporan Perancangan Aplikasi Co-Working Space Teras JTI (PDF)
- Lembar kerja Minggu 10 (docx)
- Screenshot layar Figma, supaya semua anggota bisa membandingkan tanpa membuka Figma.

---

## 5. Alur Kerja Git Sehari-hari

### Pengaturan sekali di awal (tiap anggota)

```
git config --global user.name "Nama Kamu"
git config --global user.email "email@kamu.com"
git config --global pull.rebase false
git clone https://github.com/k4iroshiki/Web-TerasJTI-Workspace.git
cd Web-TerasJTI-Workspace
```

Baris `pull.rebase false` mencegah error "divergent branches" saat `git pull`.

Kamu bisa memakai terminal, panel Source Control di VS Code, atau GitHub Desktop (Windows dan Mac). Perintah di bawah memakai terminal, dan semua tombol di aplikasi lain melakukan hal yang sama.

### Rutinitas setiap kali bekerja (5 langkah)

```
1. git pull                          # ambil kerja teman dulu
2. (edit file milikmu, simpan, cek di browser)
3. git status                        # lihat file apa yang berubah
4. git add nama-file-milikmu.html    # pilih file yang mau disimpan
5. git commit -m "pesan singkat"     # simpan perubahan dengan catatan
6. git push                          # kirim ke GitHub
```

Hafalkan: **Pull dulu, kerja, Add, Commit, Push.**

Tips:
- Pakai `git add nama-file.html`, bukan `git add .`, supaya tidak ikut menyimpan file yang bukan milikmu.
- Commit sering dan kecil. Satu commit untuk satu pekerjaan, contoh: satu halaman selesai atau satu bagian diperbaiki.
- Selalu pakai `-m "..."` pada commit. Tanpa `-m`, Git mengira teks itu nama file dan muncul error.

### Format pesan commit

| Awalan | Dipakai untuk | Contoh |
|--------|---------------|--------|
| tambah | file atau bagian baru | tambah: form login dan registrasi |
| perbaiki | memperbaiki kesalahan | perbaiki: tautan menu riwayat |
| rapikan | merapikan tanpa mengubah isi | rapikan: indentasi dashboard.html |
| dokumen | README atau docs | dokumen: update papan progres |

### Kalau muncul masalah

Lihat bagian [14. Masalah yang Sering Terjadi](#14-masalah-yang-sering-terjadi). Aturan emas kalau panik: **berhenti, jalankan `git status`, baca isinya, lalu tanya di grup dengan menyertakan hasilnya.** Jangan menjalankan perintah acak.

---

## 6. Panduan HTML untuk Proyek Ini

Semua contoh memakai konten Teras JTI. Pelajari satu bagian per sesi lalu langsung praktikkan di halamanmu.

### 6.1 Kerangka dasar (wajib ada di setiap halaman)

```html
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Beranda - Teras JTI</title>
</head>
<body>
  <header>
    <h1>Teras JTI</h1>
  </header>

  <main>
    <h2>Tempat Tersedia</h2>
  </main>

  <footer>
    <p>Teras JTI - Kelompok 4 NoBugNoCry</p>
  </footer>
</body>
</html>
```

- `head` berisi informasi halaman (tidak tampil). `body` berisi isi halaman.
- `title` tampil di tab browser. Buat berbeda di tiap halaman.
- Catatan di HTML ditulis dengan `<!-- seperti ini -->` dan tidak tampil.

### 6.2 Teks, daftar, tautan, gambar

```html
<h2>Fasilitas</h2>
<ul>
  <li>Wi-Fi</li>
  <li>Proyektor</li>
  <li>Stop kontak</li>
  <li>AC</li>
</ul>

<a href="ketersediaan.html">Pilih Jadwal</a>

<img src="assets/images/ruang-diskusi.jpg" alt="Foto Ruang Diskusi Teras JTI">
```

- `h1` hanya satu per halaman. Setelah itu pakai `h2`, `h3` secara berurutan.
- Nama file pada `href` harus sama persis dengan nama file tujuan.
- `alt` pada gambar wajib diisi dengan deskripsi singkat.
- Teks tautan harus jelas tujuannya. Pakai "Lihat Jadwal", bukan "klik di sini".

### 6.3 Elemen semantik dan navigasi seragam

Semua halaman setelah login memakai blok navigasi yang sama persis. Salin blok ini ke setiap halaman:

```html
<nav>
  <ul>
    <li><a href="dashboard.html">Beranda</a></li>
    <li><a href="riwayat.html">Riwayat</a></li>
    <li><a href="profil.html">Profil</a></li>
  </ul>
</nav>
```

Halaman turunan (detail tempat, ketersediaan, reservasi, pembayaran) juga diberi tautan kembali di awal `main`:

```html
<a href="dashboard.html">Kembali</a>
```

Di Figma, menu bawah hanya muncul di Beranda, Riwayat, dan Profil. Pada versi HTML, menu juga dipasang di halaman turunan karena modul meminta navigasi yang konsisten di semua halaman. Perbedaan ini dicatat di Lembar Kerja.

### 6.4 Formulir (Login, Registrasi, Reservasi)

```html
<form>
  <label for="email">Email</label>
  <input type="email" id="email" name="email" placeholder="Masukkan email">

  <label for="sandi">Kata Sandi</label>
  <input type="password" id="sandi" name="sandi" placeholder="Masukkan kata sandi">

  <button type="submit">Login</button>
</form>

<p>Belum punya akun? <a href="registrasi.html">Daftar</a></p>
```

Pilihan jumlah orang:

```html
<label for="jumlah">Jumlah Orang</label>
<select id="jumlah" name="jumlah">
  <option value="">Pilih jumlah orang</option>
  <option value="2">2 orang</option>
  <option value="4">4 orang</option>
  <option value="6">6 orang</option>
</select>
```

Aturan form:
- Setiap `input` punya `label`, dan nilai `for` pada label sama dengan `id` pada input.
- Pakai `type` yang sesuai: `email`, `password`, `date`, `time`, `file`.
- Tombol `button` tidak bisa pindah halaman tanpa JavaScript. Untuk simulasi alur, taruh tautan tambahan, contoh: `<a href="dashboard.html">Masuk (simulasi)</a>`. Tautan ini dihapus atau diganti saat JavaScript sudah dipelajari.
- Jangan membuat form yang mengirim password lewat URL. Cukup biarkan form tanpa `action`.

### 6.5 Tabel (Ketersediaan, Rincian Biaya, Riwayat)

```html
<table>
  <caption>Slot Jam Rabu, 28 Okt 2026</caption>
  <thead>
    <tr>
      <th>Jam</th>
      <th>Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>08:00</td>
      <td>Kosong</td>
    </tr>
    <tr>
      <td>10:00</td>
      <td>Terisi</td>
    </tr>
    <tr>
      <td>13:00</td>
      <td>Kosong</td>
    </tr>
  </tbody>
</table>
```

- `th` untuk judul kolom, `td` untuk isi. `caption` adalah judul tabel.
- Pakai tabel untuk data baris dan kolom saja, bukan untuk mengatur tata letak halaman.
- Status jangan hanya mengandalkan warna. Selalu tulis teksnya ("Terisi", "Dipilih").

### 6.6 Kartu tempat (Beranda)

```html
<article>
  <img src="assets/images/ruang-diskusi.jpg" alt="Ruang Diskusi">
  <h3>Ruang Diskusi</h3>
  <p>Kapasitas: 8 orang</p>
  <p>GRATIS</p>
  <a href="detail-tempat.html">Lihat Jadwal</a>
</article>
```

Sesuaikan kapasitas dengan Figma. Angka di atas hanya contoh.

### 6.7 Deskripsi ringkasan (Hasil Reservasi, Profil)

```html
<dl>
  <dt>Tempat</dt>
  <dd>Ruang Diskusi</dd>
  <dt>Tanggal dan Jam</dt>
  <dd>Rabu, 28 Okt 2026, 13:00 - 15:00</dd>
  <dt>Status</dt>
  <dd>Terkonfirmasi</dd>
</dl>
```

---

## 7. Spesifikasi Isi Tiap Halaman

Gunakan tulisan persis seperti di Figma. Daftar di bawah adalah ringkasan dari Lembar Kerja 2 Minggu 10.

### index.html - Login (Firsty)
- `header`: logo (`img` + `alt`), `h1` "Teras JTI", paragraf "Reservasi tempat Jurusan Teknologi Informasi".
- `form`: label dan input Email, label dan input Kata Sandi (`type="password"`), tombol "Login".
- Tautan "Belum punya akun? Daftar" ke registrasi.html. Tautan simulasi ke dashboard.html.
- Bagian "Contoh Tampilan: Login Gagal": teks "Login Gagal - Email atau kata sandi salah" dan "Periksa kembali kata sandi Anda".
- Tidak ada menu bawah (belum login).

### registrasi.html - Registrasi (Firsty)
- `h1` "Buat Akun", paragraf "Daftar untuk mulai memesan tempat".
- Input Nama Lengkap, Email, Kata Sandi, tombol "Daftar".
- Tautan "Sudah punya akun? Login" ke index.html.
- Bagian "Contoh Tampilan: Kolom Kosong": "Nama lengkap wajib diisi", "Email wajib diisi", "Kata sandi wajib diisi".

### dashboard.html - Beranda (Farrel)
- `header` "Teras JTI" dan tautan notifikasi.
- Kolom pencarian dengan label "Cari tempat atau ruangan".
- Filter: Semua, Gratis, Berbayar (DP). Boleh berupa `select` atau daftar tautan.
- `h2` "Tempat Tersedia" dan dua kartu: Ruang Diskusi (GRATIS) dan Aula Mini (DP Rp 50.000), masing-masing berisi foto, nama, kapasitas, label biaya, tautan "Lihat Jadwal".
- Bagian "Contoh Tampilan: Notifikasi": "Reservasi Terkonfirmasi - Reservasi Ruang Diskusi 28 Okt 2026 terkonfirmasi." dengan tautan "Lihat" ke riwayat.html.
- Navigasi seragam.

### detail-tempat.html - Detail Tempat (Achmad)
- Tautan Kembali, `h1` nama tempat, foto, label biaya.
- `h2` Fasilitas (daftar): Wi-Fi, Proyektor, Stop kontak, AC.
- `h2` Jam Operasional (tabel): hari dan jam.
- `h2` Aturan Penggunaan (daftar bernomor, isi contoh yang masuk akal).
- Tautan "Pilih Jadwal" ke ketersediaan.html.

### ketersediaan.html - Ketersediaan (Achmad)
- Tautan Kembali, `h1` "Ketersediaan".
- Label dan input `type="date"` untuk tanggal (nilai contoh 2026-10-28). Kalender bulanan Figma tidak bisa ditiru persis tanpa CSS dan JavaScript.
- `h2` "Pilih Jam" dan tabel slot (08:00 Kosong, 10:00 Terisi, 13:00 Kosong).
- Legenda (daftar): Kosong, Terisi, Dipilih.
- Bagian "Contoh Tampilan: Slot Dipilih" yang menuliskan slot 13:00 berstatus Dipilih.
- Tautan "Pesan Slot Terpilih" ke reservasi.html.

### reservasi.html - Form Reservasi (Wildzan)
- Tautan Kembali, `h1` "Reservasi".
- Form: Tempat, Tanggal (`date`), Jam Mulai (`time`), Jam Selesai (`time`), Jumlah Orang (`select`), tombol "Kirim Reservasi".
- Bagian "Contoh Tampilan: Tempat Berbayar": "Tempat Berbayar: DP Rp 50.000 - Status: Menunggu Pembayaran" dengan tautan "Pembayaran DP" ke pembayaran-dp.html.
- Bagian "Contoh Tampilan: Validasi Kosong": "Jumlah orang tidak boleh kosong".
- Bagian "Contoh Tampilan: Jadwal Bentrok": "Jadwal Bentrok - Maaf, slot tersebut sudah dipesan orang lain." dengan tautan "Pilih Jadwal Lain" ke ketersediaan.html.
- Tautan simulasi: "Kirim (simulasi)" ke hasil-reservasi.html.

### hasil-reservasi.html - Hasil Reservasi (Wildzan)
Tiga bagian terpisah:
1. **Sukses Gratis**: "Reservasi Terkonfirmasi - Tempat berhasil dipesan. Reservasimu sudah terkonfirmasi." Ringkasan (Ruang Diskusi, tanggal dan jam, Terkonfirmasi, GRATIS). Tautan "Lihat Riwayat" dan "Kembali ke Beranda".
2. **Menunggu Pembayaran**: "Reservasi Tercatat - Menunggu pembayaran DP." Ringkasan (Aula Mini, tanggal dan jam, Menunggu Pembayaran, Status DP: Belum Bayar). Tautan "Bayar DP Sekarang" ke pembayaran-dp.html dan "Lihat Riwayat".
3. **DP Lunas**: "Reservasi Berhasil - Pembayaran DP diterima." Ringkasan (Aula Mini, Terkonfirmasi, Status DP: Lunas). Tautan "Lihat Riwayat" dan "Kembali ke Beranda".

### pembayaran-dp.html - Pembayaran DP (Firsty)
- Tautan Kembali, `h1` "Pembayaran DP".
- Teks pengingat batas waktu, contoh: "Selesaikan pembayaran dalam 23:59:41" (teks statis).
- `h2` "Rincian Biaya" (tabel): Biaya tempat Rp 150.000, DP Rp 50.000, Sisa dibayar di tempat Rp 100.000, Bayar sekarang (DP) Rp 50.000.
- `h2` "Metode Pembayaran": pilihan radio, dua metode yang berbeda (contoh: QRIS dan Transfer Bank). Samakan dengan versi Figma terbaru.
- Label dan input `type="file"` untuk "Unggah bukti pembayaran" (JPG atau PNG, maks. 2 MB).
- Tombol "Kirim Bukti & Konfirmasi" dan tautan simulasi ke hasil-reservasi.html.

### riwayat.html - Riwayat Reservasi (Deva)
- `h1` "Riwayat Reservasi", tab Semua, Aktif, Selesai (daftar tautan).
- Tabel dengan kolom: Tempat, Tanggal dan Jam, Status, Status DP, Aksi.
  - Baris contoh: Ruang Diskusi (Terkonfirmasi, tanpa label DP, tombol Batalkan), Aula Mini (Menunggu Pembayaran, Belum Bayar, tombol Batalkan), reservasi lama (Selesai, tanpa tombol Batalkan).
- Bagian "Contoh Tampilan: Dialog Konfirmasi Batal": "Batalkan reservasi?" dan "Reservasi yang dibatalkan tidak dapat dikembalikan." dengan tombol "Tidak" dan "Ya, Batalkan".
- Bagian "Contoh Tampilan: Pembatalan Ditolak": "Tindakan Ditolak - Pembatalan ditolak: reservasi sudah berlangsung atau selesai."
- Bagian "Contoh Tampilan: Riwayat Kosong": "Belum ada reservasi", "Anda belum memiliki riwayat reservasi di Teras JTI.", tautan "Pesan Tempat Sekarang" ke dashboard.html.
- Navigasi seragam.

### profil.html - Profil (Deva)
- `h1` "Profil", avatar (`img` + `alt`), nama dan email contoh (`dl`).
- Daftar menu: Ubah Profil, Pusat Bantuan, Syarat & Ketentuan, Keluar (tautan ke index.html).
- Navigasi seragam.

---

## 8. Data Contoh Baku

Semua anggota memakai data ini agar halaman saling cocok. Jangan membuat versi sendiri.

| Data | Nilai |
|------|-------|
| Tempat gratis | Ruang Diskusi (label GRATIS) |
| Tempat berbayar | Aula Mini (label DP Rp 50.000) |
| Tanggal contoh | Rabu, 28 Okt 2026 |
| Slot jam | 08:00 Kosong, 10:00 Terisi, 13:00 Kosong |
| Jadwal dipesan | 13:00 sampai 15:00 |
| Jumlah orang contoh | 4 orang |
| Biaya tempat Aula Mini | Rp 150.000 |
| DP | Rp 50.000 |
| Sisa dibayar di tempat | Rp 100.000 |
| Fasilitas | Wi-Fi, Proyektor, Stop kontak, AC |
| Jam operasional | Senin sampai Jumat 08:00 - 16:00, Sabtu 08:00 - 12:00, Minggu Tutup |
| Pengguna contoh | Budi Santoso, budi@example.com |
| Status reservasi | Menunggu Pembayaran, Terkonfirmasi, Dibatalkan, Selesai |
| Status DP | Belum Bayar, Lunas |

---

## 9. Aturan Konsistensi

Beberapa ketidakkonsistenan sudah ditemukan di laporan Minggu 10 dan sebaiknya tidak terulang di HTML:

1. **Nama tempat**: pakai Ruang Diskusi dan Aula Mini (versi Figma), bukan Meja Diskusi atau Ruang Rapat (versi wireframe lama).
2. **Menu bawah**: tiga tab (Beranda, Riwayat, Profil), bukan dua.
3. **Nominal DP**: selalu Rp 50.000.
4. **Penulisan label**: huruf besar di awal tiap kata untuk label dan tombol ("Jumlah Orang", "Kirim Reservasi"). Pada kalimat pesan, kata "Anda" ditulis dengan huruf besar A.
5. **Tombol**: pakai kata kerja ("Lihat Jadwal", "Pesan Slot Terpilih", "Kirim Reservasi", "Batalkan").
6. **Status**: tulis teksnya, jangan hanya warna.
7. **Heading**: satu `h1` per halaman, lalu berurutan.
8. **Indentasi**: 2 spasi, tag penutup sejajar dengan tag pembukanya.
9. **Setiap halaman**: punya `title` yang berbeda, `lang="id"`, meta charset, dan meta viewport.

Perbedaan dengan Figma yang boleh terjadi karena CSS belum dipelajari: warna, font Inter, jarak, kartu dan tombol berwarna, ikon, slot berarsir, kalender bulanan, dialog melayang. Catat di Lembar Kerja, jangan dipaksakan.

---

## 10. Rencana 7 Hari

Tujuan akhir: semua anggota paham alur Git dan menulis HTML sendiri, dan website berjalan dari Login sampai kembali ke Beranda. Sesuaikan hari dengan tenggat dari dosen.

| Hari | Fokus belajar | Yang dikerjakan | Kamu paham kalau bisa |
|------|---------------|-----------------|-----------------------|
| 1 | Git dasar dan kerangka HTML | Setup Git, clone repo, isi namamu di README (lewat Deva) atau file latihan, buat file halaman milikmu berisi kerangka HTML5 + heading | Menjelaskan beda pull, commit, push dan membuka file di browser |
| 2 | Teks, daftar, tautan, gambar, semantik | Isi header, main, footer, navigasi seragam, dan judul tiap halaman | Menulis `a href` yang benar dan menjelaskan fungsi `header`, `nav`, `main`, `footer` |
| 3 | Formulir | Firsty: Login, Registrasi. Wildzan: form reservasi | Menghubungkan `label for` dengan `input id`, memilih `type` yang tepat |
| 4 | Tabel | Achmad: tabel slot. Deva: tabel riwayat. Firsty: tabel rincian biaya | Menjelaskan `thead`, `tbody`, `th`, `td`, `caption` |
| 5 | Menyelesaikan isi halaman | Semua halaman terisi sesuai bagian 7, data contoh sesuai bagian 8 | Menjelaskan alasan memilih elemen HTML di halamanmu (Lembar Kerja 3) |
| 6 | Integrasi dan pengujian | Samakan navigasi, klik semua tautan, perbaiki tautan rusak, isi Lembar Kerja 4, 6, 7 | Menemukan dan memperbaiki tautan 404 dan memakai `git pull` tanpa panik |
| 7 | Perapian dan laporan | Demo alur penuh, rapikan folder, tulis Hasil dan Pembahasan dan Kesimpulan, kumpulkan | Mendemokan alur Login sampai kembali ke Beranda dan menjelaskan struktur proyek |

Hari 1 sebaiknya dikerjakan bersama (share screen) agar semua anggota berhasil melakukan satu siklus lengkap: pull, edit, add, commit, push. Anggota yang gagal di hari 1 dibantu sebelum lanjut.

Latihan kecil tiap hari (10 menit): setiap anggota membuat satu commit dengan pesan yang jelas, walau hanya perubahan kecil.

---

## 11. Papan Progres

Deva memperbarui tabel ini. Status: Belum, Proses, Selesai, Direview.

| File | PIC | Status | Catatan |
|------|-----|--------|---------|
| index.html | Firsty | Selesai | |
| registrasi.html | Firsty | Selesai | |
| dashboard.html | Farrel | Selesai | |
| detail-tempat.html | Achmad | Selesai | |
| ketersediaan.html | Achmad | Selesai | |
| reservasi.html | Wildzan | Selesai | |
| hasil-reservasi.html | Wildzan | Selesai | |
| pembayaran.html | Firsty | Selesai | |
| riwayat.html | Deva | Selesai | |
| profil.html | Deva | Selesai | |

### Definisi selesai untuk satu halaman

Halaman dianggap selesai kalau semua poin ini benar:
- [ ] Ada DOCTYPE, `lang="id"`, meta charset UTF-8, meta viewport, dan `title`
- [ ] Memakai elemen semantik (`header`, `main`, `footer`, dan `nav` bila setelah login)
- [ ] Isi sesuai spesifikasi bagian 7 dan data bagian 8
- [ ] Heading berurutan, ada satu `h1`
- [ ] Setiap `input` punya `label` yang terhubung
- [ ] Setiap `img` punya `alt`
- [ ] Semua tautan sudah diklik dan tidak ada yang rusak
- [ ] Tidak ada data pribadi asli
- [ ] Sudah di-push dan dicek Achmad (QA)

---

## 12. Pengujian Akhir

Achmad (QA) memimpin, dan semua anggota ikut mencoba. Ini adalah gabungan Lembar Kerja 7 modul dengan skenario walkthrough Minggu 10.

### Skenario alur

| No | Skenario | Langkah | Hasil yang diharapkan | Hasil aktual |
|----|----------|---------|------------------------|--------------|
| 1 | Buka halaman awal | Buka index.html | Halaman Login tampil | |
| 2 | Pindah ke Registrasi | Klik "Belum punya akun? Daftar" | registrasi.html tampil, ada tautan kembali ke Login | |
| 3 | Masuk | Klik tautan simulasi Login | dashboard.html tampil | |
| 4 | Pesan tempat gratis | Beranda, Lihat Jadwal (Ruang Diskusi), Pilih Jadwal, Pesan Slot Terpilih, Kirim Reservasi | Berakhir di hasil "Reservasi Terkonfirmasi" | |
| 5 | Pesan tempat berbayar | Beranda, Lihat Jadwal (Aula Mini), slot 13:00, Kirim Reservasi, Bayar DP Sekarang, Kirim Bukti | Berakhir di hasil "Reservasi Berhasil" (DP lunas) | |
| 6 | Batalkan reservasi | Riwayat, lihat contoh dialog dan penolakan | Teks dialog dan "Tindakan Ditolak" terbaca | |
| 7 | Menu navigasi | Klik Beranda, Riwayat, Profil dari tiap halaman | Semua menu mengarah benar | |
| 8 | Keluar | Profil, Keluar | Kembali ke index.html | |
| 9 | Struktur | Periksa tabel, label, heading, `alt` | Terbaca dan terstruktur | |

### Pemeriksaan teknis

- Buka tiap halaman dan perhatikan tab browser: judul tab sesuai halaman.
- Klik semua tautan. Catat yang menghasilkan "tidak ditemukan".
- Pastikan nama file di `href` sama persis (huruf besar/kecil dan ekstensi).
- Pastikan tidak ada tulisan "Placeholder" atau teks contoh sisa yang tidak jelas.

---

## 13. Hasil yang Dikumpulkan ke Dosen

Dari modul Minggu 11, Deva mengoordinasi:

| Hasil | Penanggung jawab | Keterangan |
|-------|------------------|------------|
| Folder proyek terstruktur dan file HTML | Seluruh anggota | Repo ini (bisa dikumpulkan sebagai ZIP atau undang akun dosen) |
| Halaman Tentang Kami (tugas individu Acara 1) | Tiap anggota | Konfirmasikan ke dosen apakah bentuknya profil pribadi atau kelompok. Usulan lokasi: folder individu/ dengan nama tentang-namamu.html |
| Lembar Kerja 1 dan 2 (struktur halaman dan pemeriksaan dokumen) | Deva dan Farrel | Acara 1 |
| Lembar Kerja 3 dan 4 (pemetaan komponen dan pengujian Login/Dashboard) | Firsty, Farrel, Achmad | Acara 2 |
| Lembar Kerja 5 dan 6 (struktur halaman layanan dan pemeriksaan tabel) | Achmad dan Deva | Acara 3 |
| Lembar Kerja 7 (pengujian navigasi dan struktur) | Achmad | Acara 4, memakai bagian 12 |
| Hasil dan Pembahasan | Deva dengan masukan semua | Jelaskan alasan memilih elemen HTML pada tiap komponen |
| Kesimpulan | Deva dengan masukan semua | Tentang teks, daftar, tautan, gambar, formulir, semantik, tabel |

Catatan penting untuk Hasil dan Pembahasan: sebutkan bahwa Form Login belum melakukan autentikasi, dan sebutkan bagian tampilan yang belum sama dengan Figma karena CSS belum dipelajari.

### Tindak lanjut revisi Minggu 10 yang menyentuh HTML

Beberapa temuan di Lembar Kerja 5 Minggu 10 masih berstatus "Direncanakan" dan relevan saat menulis HTML:

| Temuan | Penerapan di HTML |
|--------|-------------------|
| Penulisan label tidak seragam, "anda" huruf kecil | Ikuti aturan bagian 9 |
| Jalur kembali antarlayar belum dicek | Setiap halaman turunan punya tautan Kembali dan navigasi (bagian 6.3) |
| Alur DP: bukti ditolak dan batas waktu habis belum ada layarnya | Belum dibuat di HTML, catat sebagai pekerjaan lanjutan |
| Pemeriksaan kontras warna belum dilakukan | Terkait CSS, dikerjakan saat tahap CSS |

---

## 14. Masalah yang Sering Terjadi

### Git

| Pesan atau gejala | Artinya | Solusi |
|-------------------|---------|--------|
| `Need to specify how to reconcile divergent branches` | Riwayat di laptop dan GitHub berbeda, Git minta dipilih cara menggabung | `git config pull.rebase false`, lalu `git pull` |
| `You have not concluded your merge (MERGE_HEAD exists)` | Ada merge yang belum diselesaikan | `git status`, selesaikan konflik jika ada, `git add` filenya, lalu `git commit -m "gabung perubahan"` |
| `cannot do a partial commit during a merge` | Perintah commit salah ketik | Pakai `git commit -m "pesan"` (jangan lupa `-m`) |
| `rejected ... non-fast-forward` atau `behind its remote` | Ada perubahan di GitHub yang belum kamu ambil | `git pull`, lalu `git push` lagi |
| `Authentication failed` | Login GitHub bermasalah | Login ulang (GitHub Desktop, `gh auth login`, atau token) |
| `unable to lock database` pada pacman (Arch) | Sisa proses pacman | Pastikan tidak ada pacman jalan, lalu `sudo rm /var/lib/pacman/db.lck` |
| Prompt menampilkan "main into main" | Merge belum selesai | Selesaikan dengan commit |

### Menyelesaikan konflik (conflict)

Konflik terjadi kalau dua orang mengubah baris yang sama. Karena satu orang satu file, ini jarang terjadi. Kalau terjadi, VS Code menandai file dengan:

```
<<<<<<< HEAD
versi milikmu
=======
versi dari GitHub
>>>>>>> origin/main
```

Langkah:
1. Buka file itu di VS Code. Akan ada tombol di atas tanda konflik: Accept Current Change (versimu), Accept Incoming Change (dari GitHub), atau Accept Both Changes.
2. Pilih yang benar, pastikan tanda `<<<<<<<`, `=======`, `>>>>>>>` hilang semua.
3. Simpan, lalu `git add namafile.html` dan `git commit -m "selesaikan konflik"`.
4. `git push`.

Kalau ragu, jangan memilih sembarangan. Hubungi Farrel atau Deva.

### HTML

| Masalah | Penyebab dan solusi |
|---------|---------------------|
| Perubahan tidak muncul di browser | Belum disimpan (Ctrl+S) atau belum refresh (F5) |
| Klik menu muncul "tidak ditemukan" | Nama di `href` tidak sama persis dengan nama file. Periksa huruf, tanda hubung, dan .html |
| Tulisan menjadi simbol aneh | Tidak ada `<meta charset="UTF-8">` di `head` |
| Gambar tidak tampil | Lokasi di `src` salah atau file belum di-push. Periksa folder assets/images |
| Teks tampil di luar tempatnya | Ada tag yang lupa ditutup. Periksa pasangan tag pembuka dan penutup |
| Tombol tidak pindah halaman | Wajar, `button` butuh JavaScript. Pakai tautan simulasi sementara |
| Tabel berantakan | Jumlah `td` per baris tidak sama dengan jumlah `th` |

---

## 15. Catatan untuk Pengembangan Mobile

Teras JTI dirancang sebagai **aplikasi mobile** (layar ponsel, menu bawah, target sentuh 44 px). Versi web di repo ini dibuat untuk menyelesaikan tugas Workshop Desain Aplikasi sampai akhir, sehingga:
- Struktur halaman, alur, dan data contoh dibuat mengikuti Figma agar bisa dipakai ulang.
- Tag `meta viewport` sudah dipasang sejak sekarang agar halaman siap dibuat responsif.
- Rencana pengembangan mobile (teknologi, backend, dan tahapannya) akan ditulis di bagian ini setelah kelompok memutuskan arah berikutnya.

Fitur lain dari laporan perancangan (pengelola, mini cafe, laporan, batas waktu pembayaran otomatis, verifikasi DP) juga menjadi pekerjaan tahap berikutnya.

---

## 16. Kamus Istilah dan Referensi

| Istilah | Artinya |
|---------|---------|
| Repository (repo) | Folder proyek yang disimpan di GitHub |
| Clone | Menyalin repo dari GitHub ke laptop |
| Pull | Mengambil perubahan terbaru dari GitHub |
| Add | Memilih file yang akan disimpan di commit berikutnya |
| Commit | Menyimpan perubahan lengkap dengan catatan |
| Push | Mengirim commit ke GitHub |
| Merge | Menggabungkan dua riwayat perubahan |
| Conflict | Dua orang mengubah baris yang sama sehingga Git minta kamu memilih |
| Tag | Penanda HTML seperti `<p>`, biasanya berpasangan pembuka dan penutup |
| Atribut | Informasi tambahan di dalam tag, contoh `href="krs.html"` |
| Semantik | Elemen yang namanya menjelaskan perannya (`header`, `nav`, `main`, `footer`) |
| PIC | Penanggung jawab |
| DP | Uang muka reservasi tempat berbayar |
| QA | Quality Assurance, pengujian kualitas |

Referensi belajar:
- MDN Web Docs (Bahasa Indonesia): https://developer.mozilla.org/id/docs/Learn/HTML
- W3Schools HTML: https://www.w3schools.com/html/
- Dokumentasi Git: https://git-scm.com/doc
- Modul BKPM Minggu 11 dari dosen dan Laporan Perancangan Teras JTI (folder docs)
