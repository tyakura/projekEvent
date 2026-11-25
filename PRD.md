# Planify --- Product Requirements Document (PRD)

**Versi:** 1.0\
**Status:** Draft untuk MVP\
**Produk:** Personal Event Planning & Management Platform\
**Platform:** Web Application\
**Target pengembangan:** 1--2 developer, 7 hari\
**Stack:** Laravel REST API, React + Vite, MySQL

------------------------------------------------------------------------

## 1. Ringkasan Produk

Planify adalah aplikasi web untuk membantu individu membuat, mengatur,
dan memantau acara pribadi melalui satu tempat. Pengguna dapat mengelola
detail acara, melihat jadwal pada kalender bulanan, menyusun checklist
persiapan, mencatat anggaran, mengatur pengingat, dan menyimpan
dokumentasi.

Planify berfokus pada pengalaman personal. Pada versi awal, setiap akun
hanya dapat mengakses dan mengelola acara miliknya sendiri. Fitur
kolaborasi antar pengguna tidak termasuk dalam MVP.

### 1.1 Visi Produk

Membantu pengguna merencanakan acara pribadi secara lebih teratur, mudah
dipantau, dan tidak tersebar di berbagai catatan atau aplikasi.

### 1.2 Masalah yang Ingin Diselesaikan

-   Informasi acara sering tersebar di catatan, kalender, dan aplikasi
    berbeda.
-   Pengguna dapat lupa jadwal atau tugas persiapan.
-   Pengeluaran acara sulit dipantau jika tidak dicatat secara terpusat.
-   Dokumentasi acara tidak tersusun berdasarkan acara.

### 1.3 Solusi

Planify menyediakan dashboard personal yang menghubungkan data acara,
kalender, checklist, anggaran, pengingat, dan dokumentasi dalam satu
aplikasi.

------------------------------------------------------------------------

## 2. Sasaran dan Tujuan Produk

### 2.1 Tujuan

1.  Memungkinkan pengguna membuat dan mengelola acara pribadi.
2.  Memudahkan pengguna melihat jadwal acara melalui kalender bulanan.
3.  Membantu pengguna memantau persiapan melalui checklist.
4.  Menyediakan pencatatan anggaran dan pengeluaran per acara.
5.  Menyediakan pengingat dan dokumentasi yang terkait dengan acara.

### 2.2 Indikator Keberhasilan

MVP dinyatakan berhasil apabila:

-   Pengguna dapat mendaftar, login, dan logout.
-   Pengguna dapat membuat, melihat, mengubah, dan menghapus acara.
-   Acara milik pengguna tampil pada tanggal yang sesuai di kalender.
-   Pengguna dapat mengelola kategori dan checklist acara.
-   Sistem membatasi akses sehingga pengguna tidak dapat mengakses data
    akun lain.
-   Alur utama dapat digunakan pada desktop dan perangkat mobile.
-   Tidak terdapat bug kritis pada alur autentikasi dan pengelolaan
    acara.

------------------------------------------------------------------------

## 3. Target Pengguna dan Persona

### 3.1 Target Utama

Individu yang ingin merencanakan kegiatan atau acara pribadi, misalnya:

-   Pelajar yang mengatur kegiatan sekolah.
-   Seseorang yang merencanakan ulang tahun.
-   Individu yang mengatur rapat atau kegiatan pribadi.
-   Pengguna yang merencanakan perjalanan atau liburan.

### 3.2 Persona

**Nama:** Personal Planner\
**Kebutuhan:** Mengelola beberapa acara dan persiapannya dari satu
dashboard.\
**Kendala:** Sulit mengingat tanggal, tugas, dan anggaran jika informasi
tersebar.\
**Tujuan:** Mengetahui acara mendatang, tugas yang belum selesai, dan
kondisi anggaran dengan cepat.

------------------------------------------------------------------------

## 4. Ruang Lingkup Produk

### 4.1 In Scope

-   Registrasi, login, dan logout.
-   Dashboard personal.
-   CRUD acara.
-   Kategori acara.
-   Kalender bulanan.
-   Checklist tugas per acara.
-   Pengingat dalam aplikasi.
-   Anggaran dan pencatatan pengeluaran.
-   Upload dan penghapusan dokumentasi acara.
-   Isolasi data berdasarkan pemilik akun.

### 4.2 Out of Scope

-   Kolaborasi atau undangan anggota.
-   Role dan permission tim.
-   Integrasi Google Calendar.
-   Email atau push notification otomatis.
-   Pembayaran online.
-   Rekomendasi acara berbasis AI.
-   Aplikasi native Android/iOS.
-   Ekspor laporan PDF.
-   Sinkronisasi lintas platform.

------------------------------------------------------------------------

## 5. Prioritas MVP

Karena target pengerjaan hanya tujuh hari oleh satu atau dua developer,
fitur dibagi berdasarkan prioritas.

### 5.1 Must Have --- Wajib

  Modul              Ruang lingkup MVP
  ------------------ -------------------------------------------------
  Authentication     Register, login, logout
  Dashboard          Ringkasan jumlah acara dan acara mendatang
  Event Management   CRUD acara
  Categories         Kategori acara bawaan atau CRUD sederhana
  Monthly Calendar   Kalender bulanan dan daftar acara per tanggal
  Checklist          Tambah, ubah, hapus, dan tandai tugas selesai
  Authorization      Setiap pengguna hanya mengakses datanya sendiri

### 5.2 Should Have --- Jika Waktu Memungkinkan

  Modul           Ruang lingkup
  --------------- -----------------------------------------
  Reminder        Pengingat yang tampil di dalam aplikasi
  Budget          Anggaran acara dan daftar pengeluaran
  Documentation   Upload, tampilkan, dan hapus foto acara

### 5.3 Could Have --- Setelah MVP

-   Email reminder terjadwal.
-   Push notification.
-   Grafik anggaran.
-   Galeri dokumentasi yang lebih lengkap.
-   Ekspor acara ke PDF.
-   Integrasi kalender eksternal.
-   Kolaborasi antar pengguna.

**Aturan scope:** fitur Must Have harus stabil sebelum Should Have
dikerjakan. Jika waktu tersisa kurang dari satu hari, fitur tambahan
tidak boleh menghambat penyelesaian alur utama.

------------------------------------------------------------------------

## 6. Functional Requirements

### FR-01 --- Authentication

-   FR-01.1: Pengguna dapat membuat akun menggunakan nama, email, dan
    password.
-   FR-01.2: Sistem memvalidasi email unik dan format input.
-   FR-01.3: Pengguna dapat login menggunakan kredensial yang valid.
-   FR-01.4: Pengguna dapat logout.
-   FR-01.5: Endpoint privat hanya dapat diakses dengan autentikasi yang
    valid.

### FR-02 --- Dashboard

-   FR-02.1: Menampilkan jumlah acara milik pengguna.
-   FR-02.2: Menampilkan acara mendatang.
-   FR-02.3: Menampilkan acara yang sedang berlangsung atau telah
    selesai jika relevan.
-   FR-02.4: Menampilkan ringkasan checklist.
-   FR-02.5: Menampilkan ringkasan anggaran jika modul anggaran telah
    diaktifkan.

### FR-03 --- Event Management

-   FR-03.1: Pengguna dapat membuat acara.
-   FR-03.2: Pengguna dapat melihat daftar acara miliknya.
-   FR-03.3: Pengguna dapat melihat detail acara.
-   FR-03.4: Pengguna dapat mengubah acara miliknya.
-   FR-03.5: Pengguna dapat menghapus acara miliknya.
-   FR-03.6: Pengguna dapat menentukan nama, deskripsi, lokasi,
    kategori, tanggal mulai, tanggal selesai, dan status acara.
-   FR-03.7: Sistem memvalidasi bahwa tanggal selesai tidak lebih awal
    dari tanggal mulai.

### FR-04 --- Categories

-   FR-04.1: Acara dapat memiliki satu kategori.
-   FR-04.2: Pengguna dapat memilih kategori saat membuat atau mengubah
    acara.
-   FR-04.3: Daftar acara dapat difilter berdasarkan kategori.
-   FR-04.4: Kategori bawaan disediakan agar pengguna dapat langsung
    menggunakan aplikasi.

### FR-05 --- Monthly Calendar

-   FR-05.1: Menampilkan kalender dalam format bulanan.
-   FR-05.2: Pengguna dapat berpindah ke bulan sebelumnya dan
    berikutnya.
-   FR-05.3: Acara ditampilkan pada tanggal yang sesuai.
-   FR-05.4: Pengguna dapat membuka detail acara dari kalender.
-   FR-05.5: Kalender hanya menampilkan acara milik pengguna yang sedang
    login.

### FR-06 --- Checklist

-   FR-06.1: Pengguna dapat menambahkan tugas pada acara.
-   FR-06.2: Pengguna dapat mengubah judul, deskripsi, dan tenggat
    tugas.
-   FR-06.3: Pengguna dapat menghapus tugas.
-   FR-06.4: Pengguna dapat menandai tugas selesai atau belum selesai.
-   FR-06.5: Sistem menampilkan progres penyelesaian tugas per acara.

### FR-07 --- Reminder

-   FR-07.1: Pengguna dapat menentukan waktu pengingat untuk acara.
-   FR-07.2: Pengingat ditampilkan di dalam aplikasi.
-   FR-07.3: Pengguna dapat melihat pengingat yang akan datang.
-   FR-07.4: Pengingat hanya dapat dikelola oleh pemilik acara.

**Batasan MVP:** pengingat tidak menjanjikan notifikasi email, push,
atau proses otomatis ketika browser ditutup. Implementasi awal dapat
berupa daftar pengingat dan indikator pengingat yang sudah waktunya saat
aplikasi dibuka.

### FR-08 --- Budget

-   FR-08.1: Pengguna dapat menetapkan anggaran untuk acara.
-   FR-08.2: Pengguna dapat menambahkan catatan pengeluaran.
-   FR-08.3: Pengguna dapat mengubah dan menghapus catatan pengeluaran.
-   FR-08.4: Sistem menghitung total pengeluaran.
-   FR-08.5: Sistem menghitung sisa anggaran = anggaran - total
    pengeluaran.

### FR-09 --- Documentation

-   FR-09.1: Pengguna dapat mengunggah foto dokumentasi ke acara.
-   FR-09.2: Pengguna dapat melihat dokumentasi acara.
-   FR-09.3: Pengguna dapat menghapus dokumentasi miliknya.
-   FR-09.4: Sistem memvalidasi tipe dan ukuran file.
-   FR-09.5: File disimpan menggunakan storage Laravel dan metadata
    disimpan di database.

------------------------------------------------------------------------

## 7. User Stories

  -----------------------------------------------------------------------
  ID                                  User Story
  ----------------------------------- -----------------------------------
  US-01                               Sebagai pengguna, saya ingin
                                      mendaftar agar dapat menyimpan
                                      rencana acara secara pribadi.

  US-02                               Sebagai pengguna, saya ingin login
                                      agar dapat mengakses dashboard
                                      saya.

  US-03                               Sebagai pengguna, saya ingin
                                      membuat acara agar kegiatan saya
                                      terorganisasi.

  US-04                               Sebagai pengguna, saya ingin
                                      mengubah atau menghapus acara jika
                                      rencana berubah.

  US-05                               Sebagai pengguna, saya ingin
                                      melihat kalender bulanan agar mudah
                                      mengetahui jadwal.

  US-06                               Sebagai pengguna, saya ingin
                                      mengelompokkan acara berdasarkan
                                      kategori.

  US-07                               Sebagai pengguna, saya ingin
                                      membuat checklist agar persiapan
                                      acara lebih teratur.

  US-08                               Sebagai pengguna, saya ingin
                                      menerima pengingat dalam aplikasi
                                      agar tidak melewatkan acara.

  US-09                               Sebagai pengguna, saya ingin
                                      mencatat pengeluaran agar anggaran
                                      terkontrol.

  US-10                               Sebagai pengguna, saya ingin
                                      menyimpan foto dokumentasi agar
                                      arsip acara tersusun.
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 8. Business Rules

1.  Setiap acara wajib memiliki satu pemilik (`user_id`).
2.  Pengguna hanya dapat membaca, mengubah, atau menghapus acara
    miliknya.
3.  Setiap acara dapat memiliki satu kategori.
4.  Setiap acara dapat memiliki banyak checklist.
5.  Setiap checklist hanya terhubung ke satu acara.
6.  Tanggal selesai acara tidak boleh lebih awal daripada tanggal mulai.
7.  Total pengeluaran dihitung dari seluruh catatan pengeluaran acara.
8.  Sisa anggaran dihitung dari anggaran dikurangi total pengeluaran.
9.  Pengingat harus terhubung ke acara yang dimiliki pengguna.
10. Dokumentasi harus terhubung ke acara yang dimiliki pengguna.
11. Penghapusan acara harus menangani data turunannya melalui cascade
    atau proses penghapusan terkontrol.
12. Semua tanggal disimpan dan ditampilkan secara konsisten dengan zona
    waktu aplikasi.

------------------------------------------------------------------------

## 9. Non-Functional Requirements

  -----------------------------------------------------------------------
  ID                      Kategori                Requirement
  ----------------------- ----------------------- -----------------------
  NFR-01                  Security                Password disimpan
                                                  menggunakan hashing
                                                  yang aman.

  NFR-02                  Authorization           Semua operasi data
                                                  memverifikasi
                                                  kepemilikan resource.

  NFR-03                  Validation              Input divalidasi di
                                                  backend, bukan hanya
                                                  frontend.

  NFR-04                  Performance             Halaman utama
                                                  ditargetkan tampil
                                                  dalam 3 detik pada
                                                  lingkungan pengujian
                                                  normal.

  NFR-05                  Responsive              UI dapat digunakan pada
                                                  desktop, tablet, dan
                                                  smartphone.

  NFR-06                  Usability               Navigasi, form, dan
                                                  pesan error mudah
                                                  dipahami.

  NFR-07                  Data Integrity          Foreign key dan
                                                  constraint digunakan
                                                  untuk menjaga
                                                  konsistensi data.

  NFR-08                  Maintainability         Kode frontend dan
                                                  backend dipisahkan
                                                  berdasarkan tanggung
                                                  jawab.

  NFR-09                  Reliability             Sistem menampilkan
                                                  feedback ketika
                                                  permintaan berhasil
                                                  atau gagal.

  NFR-10                  Accessibility           Kontras, label form,
                                                  fokus keyboard, dan
                                                  reduced motion
                                                  diperhatikan.
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 10. Acceptance Criteria

  -----------------------------------------------------------------------
  Modul                               Kriteria
  ----------------------------------- -----------------------------------
  Authentication                      Register, login, dan logout bekerja
                                      dengan validasi.

  Dashboard                           Ringkasan hanya berisi data
                                      pengguna yang login.

  Event                               CRUD acara berjalan dan validasi
                                      tanggal diterapkan.

  Categories                          Acara dapat memiliki kategori yang
                                      valid.

  Calendar                            Acara tampil pada tanggal yang
                                      tepat dan dapat dibuka.

  Checklist                           Tugas dapat dibuat, diubah,
                                      dihapus, dan ditandai selesai.

  Authorization                       Pengguna A tidak dapat mengakses
                                      data pengguna B.

  Reminder                            Pengingat tersimpan dan tampil pada
                                      akun pemiliknya.

  Budget                              Total dan sisa anggaran dihitung
                                      dengan benar.

  Documentation                       File valid dapat diunggah,
                                      ditampilkan, dan dihapus oleh
                                      pemilik.
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 11. Rencana Pengembangan 7 Hari

  -----------------------------------------------------------------------
  Hari                    Fokus                   Hasil
  ----------------------- ----------------------- -----------------------
  1                       Planning & setup        ERD, setup
                                                  Laravel/React, koneksi
                                                  MySQL

  2                       Authentication          Register, login,
                                                  logout, proteksi API

  3                       Event & category        CRUD acara dan kategori

  4                       Dashboard & calendar    Ringkasan data dan
                                                  kalender bulanan

  5                       Checklist               CRUD tugas dan status
                                                  selesai

  6                       Fitur tambahan          Reminder, budget,
                                                  dokumentasi sesuai sisa
                                                  waktu

  7                       Testing & finalisasi    Pengujian, perbaikan
                                                  bug, dokumentasi, demo
  -----------------------------------------------------------------------

### Pembagian Tugas untuk 2 Developer

**Developer 1 --- Backend** - Laravel REST API. - MySQL migration dan
relasi. - Authentication dan authorization. - Validasi dan business
logic. - Pengujian endpoint.

**Developer 2 --- Frontend** - React dan Tailwind CSS. - Layout dan
komponen UI. - Dashboard, kalender, form, dan detail acara. - Integrasi
API. - Responsive testing.

Keduanya menyepakati kontrak API dan melakukan pengujian integrasi
bersama.

------------------------------------------------------------------------

## 12. Risiko dan Mitigasi

  -----------------------------------------------------------------------
  Risiko                              Mitigasi
  ----------------------------------- -----------------------------------
  Scope terlalu besar                 Kunci prioritas Must Have sebelum
                                      mulai coding.

  Integrasi API terlambat             Definisikan endpoint dan format
                                      response sejak hari pertama.

  Masalah autentikasi                 Uji Sanctum lebih awal.

  Data pengguna bocor                 Terapkan ownership check pada
                                      setiap endpoint resource.

  Kalender menyita waktu              Gunakan library kalender React yang
                                      sudah tersedia.

  Upload file bermasalah              Jadikan dokumentasi fitur opsional
                                      dan validasi file di backend.

  Reminder tidak berjalan saat        Batasi klaim MVP pada pengingat
  browser tertutup                    dalam aplikasi.
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 13. Asumsi dan Keputusan

-   Produk adalah personal planner, bukan platform kolaborasi.
-   Setiap pengguna memiliki ruang data sendiri.
-   Satu acara memiliki satu kategori.
-   Kalender menggunakan tampilan bulanan.
-   Zona waktu awal aplikasi: `Asia/Jakarta`, dapat dikonfigurasi.
-   Mata uang awal: Rupiah (IDR).
-   Reminder MVP bersifat in-app.
-   Fitur dokumentasi menggunakan Laravel public disk untuk prototipe
    lokal; konfigurasi produksi perlu mempertimbangkan akses file
    privat.
-   Stack backend adalah Laravel REST API dan frontend React + Vite.
-   Versi Laravel dipilih berdasarkan versi PHP dan lingkungan
    pengembangan yang tersedia.

------------------------------------------------------------------------

## 14. Rencana Pengembangan Setelah MVP

1.  Email dan push notification.
2.  Integrasi Google Calendar.
3.  Ekspor laporan acara.
4.  Statistik dan visualisasi anggaran.
5.  Galeri dokumentasi.
6.  Kolaborasi dan berbagi acara.
7.  Aplikasi mobile.

**Dokumen ini menjadi acuan ruang lingkup dan prioritas pengembangan
Planify v1.0.**
