# Planify --- Design System & UI/UX Specification

**Versi:** 1.0\
**Status:** Design direction untuk MVP\
**Produk:** Personal Event Planning & Management Platform\
**Visual direction:** Modern Minimalist dengan sentuhan editorial\
**Referensi:** Astro Association Template (`README(1).md`, `demo.tsx`,
`demo-dark.tsx`, `demo-custom.tsx`)

------------------------------------------------------------------------

## 1. Design Overview

Planify menggunakan pendekatan modern minimalis yang mengutamakan
keterbacaan, hierarki informasi, dan navigasi yang jelas. Antarmuka
harus terasa ringan untuk penggunaan sehari-hari, tetapi tetap memiliki
karakter visual yang kuat.

### 1.1 Tujuan Desain

-   Membuat pengguna cepat memahami jadwal dan prioritas.
-   Menjadikan pembuatan dan pengelolaan acara terasa sederhana.
-   Menampilkan informasi penting tanpa memenuhi layar dengan dekorasi.
-   Menjaga konsistensi pada dashboard, kalender, detail acara, dan
    form.
-   Memberikan pengalaman yang baik pada desktop dan mobile.

### 1.2 Prinsip Desain

1.  **Clarity first:** informasi acara, tanggal, status, dan tugas harus
    mudah dipindai.
2.  **Strong hierarchy:** judul halaman besar, label ringkas, dan konten
    tersusun jelas.
3.  **Quiet interface:** gunakan ruang kosong untuk mengurangi kepadatan
    visual.
4.  **Consistent interaction:** tombol, form, dialog, dan status
    memiliki perilaku konsisten.
5.  **Responsive by default:** layout menyesuaikan ukuran layar.
6.  **Motion with purpose:** animasi hanya membantu orientasi dan
    feedback, bukan menjadi gangguan.

------------------------------------------------------------------------

## 2. Design Reference Analysis

Referensi yang diberikan berisi komponen `AstroAssociationTemplate`
dengan pendekatan visual editorial/poster.

### 2.1 Elemen Referensi yang Dipertahankan sebagai Inspirasi

-   Navigasi sticky dengan efek frosted.
-   Tipografi display berukuran besar.
-   Penggunaan palet warna yang dapat dikustomisasi.
-   Dukungan tema terang dan gelap.
-   Pembagian halaman ke dalam section yang jelas.
-   Interaksi hover dan animasi ringan.
-   Layout responsif dengan navigasi mobile.
-   Dukungan `prefers-reduced-motion`.
-   Font display geometris seperti Poppins atau Montserrat.

### 2.2 Elemen yang Tidak Diadopsi Secara Literal

Elemen berikut merupakan identitas template klub astronomi dan tidak
digunakan sebagai fitur Planify:

-   Bubble field dan bubble popping.
-   Moon phase dan sky tonight.
-   Membership tiers.
-   RSVP dan seat counter.
-   Project dossier untuk klub.
-   Wordmark astronomi dan dekorasi observatorium.

### 2.3 Adaptasi ke Planify

  -----------------------------------------------------------------------
  Referensi                           Adaptasi Planify
  ----------------------------------- -----------------------------------
  Sticky frosted navigation           Sidebar dashboard dan topbar yang
                                      ringkas

  Oversized hero typography           Judul dashboard dan sapaan pengguna

  Palette switcher                    Design tokens light/dark

  Section projects                    Kartu acara mendatang

  Event nights list                   Daftar jadwal acara

  Interactive stats                   Ringkasan jumlah acara dan
                                      checklist

  Tier cards                          Kartu ringkasan anggaran atau
                                      kategori

  Responsive menu                     Sidebar yang berubah menjadi drawer
                                      pada mobile
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 3. Visual Direction

### 3.1 Karakter Visual

-   Modern.
-   Minimalis.
-   Editorial.
-   Geometris.
-   Hangat namun profesional.
-   Tidak terlalu dekoratif.

### 3.2 Rekomendasi Palet Warna

Gunakan palet **Planify Indigo** sebagai default. Warna dapat
disesuaikan setelah implementasi awal.

#### Light Theme

  Token               Warna       Penggunaan
  ------------------- ----------- -------------------------------
  `--background`      `#F7F8FC`   Latar utama
  `--surface`         `#FFFFFF`   Card dan panel
  `--surface-muted`   `#F0F2F8`   Area sekunder
  `--foreground`      `#171A2B`   Teks utama
  `--muted`           `#74798C`   Teks sekunder
  `--border`          `#E5E7EF`   Border
  `--primary`         `#5655D9`   Tombol dan aksen utama
  `--primary-hover`   `#4544C4`   Hover tombol
  `--accent`          `#B8B7FF`   Aksen dekoratif
  `--success`         `#23865B`   Status selesai
  `--warning`         `#C58A25`   Status perlu perhatian
  `--danger`          `#C94D58`   Error dan tindakan destruktif

#### Dark Theme

  Token               Warna       Penggunaan
  ------------------- ----------- -------------------------------
  `--background`      `#111321`   Latar utama
  `--surface`         `#191D30`   Card dan panel
  `--surface-muted`   `#222740`   Area sekunder
  `--foreground`      `#F3F4FA`   Teks utama
  `--muted`           `#A1A6BB`   Teks sekunder
  `--border`          `#303650`   Border
  `--primary`         `#9290FF`   Tombol dan aksen utama
  `--primary-hover`   `#AAA8FF`   Hover tombol
  `--accent`          `#5552A8`   Aksen dekoratif
  `--success`         `#5CC995`   Status selesai
  `--warning`         `#E5B65E`   Status perlu perhatian
  `--danger`          `#F07882`   Error dan tindakan destruktif

**Aturan warna:** - Warna primer digunakan untuk aksi utama dan elemen
terpilih. - Warna status harus konsisten dan tidak hanya dibedakan
melalui warna; sertakan label atau ikon. - Jangan menggunakan terlalu
banyak warna aksen dalam satu layar. - Pastikan kontras teks tetap
terbaca.

### 3.3 Tipografi

Referensi menggunakan font geometris seperti Poppins dan Montserrat.
Planify dapat menggunakan:

-   **Display / heading:** Poppins atau Plus Jakarta Sans.
-   **Body:** Inter atau Plus Jakarta Sans.
-   **Numeric / metadata:** Inter dengan tabular numerals jika tersedia.

Skala tipografi:

  Style       Ukuran desktop Penggunaan
  --------- ---------------- ------------------------------
  Display          40--48 px Judul utama halaman tertentu
  H1                   32 px Judul halaman
  H2                   24 px Judul section
  H3               18--20 px Judul card
  Body             14--16 px Konten utama
  Small            12--13 px Label dan metadata
  Micro                11 px Caption terbatas

Gunakan weight 400 untuk body, 500 untuk label, 600 untuk heading kecil,
dan 700 untuk judul utama.

------------------------------------------------------------------------

## 4. Layout System

### 4.1 Desktop Application Shell

Gunakan struktur dashboard dengan sidebar di kiri dan area konten di
kanan.

``` text
┌──────────────────────────────────────────────────────────────┐
│ Sidebar       │ Topbar: Search / Theme / Profile              │
│               ├──────────────────────────────────────────────┤
│ Planify       │ Page title                         + New Event │
│               │                                              │
│ Dashboard     │ Main content                                 │
│ Calendar      │                                              │
│ My Events     │ Cards / Calendar / Lists                     │
│ Categories    │                                              │
│               │                                              │
│ Settings      │                                              │
└──────────────────────────────────────────────────────────────┘
```

Rekomendasi ukuran: - Sidebar: 240--260 px. - Topbar: 64--72 px. -
Konten utama: maksimal 1440 px. - Padding konten desktop: 28--36 px. -
Jarak antar section: 24--32 px.

### 4.2 Tablet

-   Sidebar dapat diciutkan menjadi icon rail atau drawer.
-   Grid kartu berubah menjadi dua kolom jika ruang mencukupi.
-   Kalender tetap menampilkan tujuh kolom dengan label hari yang
    ringkas.
-   Form menggunakan satu kolom bila lebar terbatas.

### 4.3 Mobile

-   Sidebar berubah menjadi drawer atau bottom navigation sederhana.
-   Konten utama satu kolom.
-   Tombol aksi utama mudah dijangkau.
-   Kalender dapat memakai tampilan ringkas dengan agenda tanggal
    terpilih.
-   Form menggunakan lebar penuh.
-   Hindari tabel lebar yang memerlukan scroll horizontal jika dapat
    diganti dengan list card.

### 4.4 Responsive Breakpoints

  Breakpoint           Ukuran Perilaku
  ------------ -------------- ------------------------------------
  Mobile            `< 640px` Single column, drawer/bottom nav
  Tablet         `640–1023px` Sidebar collapsible, grid 2 kolom
  Desktop         `>= 1024px` Sidebar penuh, multi-column layout
  Wide            `>= 1440px` Konten dibatasi max-width

------------------------------------------------------------------------

## 5. Navigation & Information Architecture

### 5.1 Navigasi Utama

1.  Dashboard
2.  Calendar
3.  My Events
4.  Categories
5.  Settings

Aksi `Create Event` ditampilkan sebagai tombol utama yang mudah
ditemukan.

### 5.2 Route Frontend yang Disarankan

  Route                Halaman            Akses
  -------------------- ------------------ ---------------
  `/login`             Login              Guest
  `/register`          Register           Guest
  `/dashboard`         Dashboard          Authenticated
  `/calendar`          Monthly Calendar   Authenticated
  `/events`            Daftar acara       Authenticated
  `/events/new`        Buat acara         Authenticated
  `/events/:id`        Detail acara       Authenticated
  `/events/:id/edit`   Edit acara         Authenticated
  `/categories`        Kategori           Authenticated
  `/settings`          Pengaturan         Authenticated

------------------------------------------------------------------------

## 6. Page Specifications

### 6.1 Login & Register

**Tujuan:** memberikan akses masuk yang sederhana dan jelas.

Komponen: - Brand mark Planify. - Heading dan deskripsi singkat. - Input
email. - Input password. - Tombol submit. - Link pindah
login/register. - Pesan validasi dan error.

Perilaku: - Validasi format email. - Password tidak ditampilkan secara
default. - Tampilkan loading saat request berlangsung. - Tampilkan
feedback jika kredensial salah.

### 6.2 Dashboard

**Tujuan:** memberikan ringkasan kondisi perencanaan pengguna.

Susunan konten: 1. Greeting dan tanggal saat ini. 2. Tombol
`Create Event`. 3. Summary cards: - Total Events. - Upcoming Events. -
Tasks Completed. - Budget Overview (jika modul budget tersedia). 4.
Upcoming Events list. 5. Mini calendar atau agenda singkat. 6. Task
overview.

Contoh struktur:

``` text
Good morning, [Name]                    [ + Create Event ]

[ Total Events ] [ Upcoming ] [ Tasks ] [ Budget ]

Upcoming Events
┌───────────────────────────┐
│ Event card                │
│ Title, date, category     │
└───────────────────────────┘

Your Tasks                 Mini Calendar
- Confirm venue             [Monthly view]
- Prepare invitation        [Selected date]
```

Empty state: - Jika belum ada acara, tampilkan ilustrasi atau ikon
sederhana, penjelasan singkat, dan CTA `Create your first event`.

### 6.3 My Events

**Tujuan:** menampilkan seluruh acara milik pengguna.

Komponen: - Judul halaman. - Tombol tambah acara. - Search input. -
Filter kategori. - Filter status. - Event cards atau list. - Empty
state.

Informasi event card: - Nama acara. - Tanggal. - Lokasi. - Kategori. -
Status. - Progress checklist jika tersedia. - Menu edit dan delete.

### 6.4 Create / Edit Event

Field: - Event title (required). - Description (optional). - Category
(required atau default). - Location (optional). - Start date
(required). - End date (required). - Status (default: planned).

Perilaku: - Validasi field wajib. - End date tidak boleh sebelum start
date. - Tombol submit menampilkan loading. - Berikan toast atau inline
feedback setelah berhasil. - Konfirmasi sebelum meninggalkan form dengan
perubahan yang belum disimpan, jika implementasi memungkinkan.

### 6.5 Event Detail

Susunan: - Breadcrumb atau tombol kembali. - Nama acara, kategori,
status. - Tanggal dan lokasi. - Deskripsi. - Tombol edit dan delete. -
Tab atau section: Overview, Checklist, Budget, Reminders, Documentation.

Untuk MVP, tab yang belum diimplementasikan tidak perlu ditampilkan
sebagai fitur aktif. Checklist menjadi bagian detail yang wajib.

### 6.6 Monthly Calendar

**Tujuan:** membantu pengguna memahami jadwal acara per bulan.

Komponen: - Nama bulan dan tahun. - Tombol previous / next month. -
Tombol Today. - Grid kalender tujuh kolom. - Indikator acara pada
tanggal. - Panel agenda untuk tanggal terpilih.

Perilaku: - Klik tanggal untuk melihat agenda pada tanggal tersebut. -
Klik item acara untuk membuka detail. - Acara multi-hari harus memiliki
representasi yang jelas. - Warna kategori dapat digunakan sebagai
penanda, tetapi sertakan teks atau label agar tidak bergantung pada
warna saja.

### 6.7 Checklist

Komponen: - Daftar tugas. - Checkbox status. - Judul tugas. - Due date
jika ada. - Tombol tambah tugas. - Progress indicator.

Perilaku: - Menandai tugas selesai memperbarui progress. - Tugas selesai
dapat diberi gaya teks sekunder atau strikethrough. - Pengguna dapat
mengubah dan menghapus tugas.

### 6.8 Reminder

Untuk MVP: - Tampilkan daftar pengingat pada halaman atau dashboard. -
Tampilkan tanggal dan waktu pengingat. - Bedakan upcoming dan due. -
Jangan menjanjikan push notification jika belum ada service worker atau
backend scheduler.

### 6.9 Budget

Komponen: - Total budget. - Total expenses. - Remaining budget. -
Progress bar pemakaian anggaran. - Daftar transaksi pengeluaran. - Form
tambah pengeluaran.

Format angka: - Gunakan format Rupiah. - Contoh: `Rp250.000`. - Pastikan
perhitungan dilakukan di backend atau dihitung dari data tervalidasi,
bukan mempercayai angka total dari client.

### 6.10 Documentation

Komponen: - Upload area. - Preview gambar. - Nama file atau tanggal
upload. - Tombol hapus. - Empty state.

Perilaku: - Validasi tipe dan ukuran file. - Tampilkan progress upload
jika tersedia. - Konfirmasi penghapusan. - Jangan menampilkan file milik
acara pengguna lain.

------------------------------------------------------------------------

## 7. Component Library

Komponen reusable yang disarankan:

### Layout

-   `AppShell`
-   `Sidebar`
-   `Topbar`
-   `MobileNavigation`
-   `PageHeader`
-   `ContentContainer`

### Data Display

-   `StatCard`
-   `EventCard`
-   `EventList`
-   `CategoryBadge`
-   `StatusBadge`
-   `TaskItem`
-   `BudgetSummary`
-   `ReminderItem`
-   `EmptyState`

### Form

-   `TextInput`
-   `TextArea`
-   `SelectInput`
-   `DateInput`
-   `TimeInput`
-   `FileUpload`
-   `FormField`

### Feedback

-   `Toast`
-   `Modal`
-   `ConfirmDialog`
-   `LoadingSpinner`
-   `Skeleton`
-   `ErrorState`

### Calendar

-   `CalendarHeader`
-   `CalendarGrid`
-   `CalendarDay`
-   `CalendarEvent`
-   `SelectedDateAgenda`

------------------------------------------------------------------------

## 8. Interaction & Motion

### 8.1 Motion Direction

Ambil inspirasi dari referensi yang memiliki hover interaction, marquee,
reveal, dan pointer response, tetapi gunakan gerakan yang lebih tenang
untuk aplikasi produktivitas.

Rekomendasi: - Transisi warna tombol: 150--200 ms. - Hover card:
perubahan border/shadow ringan. - Dropdown dan popover: fade/scale
singkat. - Modal: fade dengan sedikit translate. - Page content: fade-in
ringan jika tidak mengganggu navigasi.

### 8.2 Interaksi

-   Button memiliki hover, active, focus, dan disabled state.
-   Card yang dapat diklik memiliki affordance yang jelas.
-   Form menampilkan error dekat field terkait.
-   Delete action membutuhkan konfirmasi.
-   Loading state mencegah submit berulang.
-   Toast digunakan untuk feedback sukses atau gagal.

### 8.3 Reduced Motion

Hormati `prefers-reduced-motion: reduce`. Jika aktif: - Nonaktifkan
animasi dekoratif. - Kurangi transisi yang tidak penting. - Jangan
menggunakan parallax atau gerakan pointer yang berlebihan. - Pastikan
semua informasi tetap tersedia tanpa animasi.

------------------------------------------------------------------------

## 9. Theme System

Sediakan Light dan Dark Theme.

### 9.1 Theme Behavior

-   Default mengikuti preferensi sistem atau Light Theme.
-   Pengguna dapat mengganti tema melalui menu profil atau topbar.
-   Gunakan CSS variables agar warna komponen konsisten.
-   Jangan meng-hardcode warna berbeda pada setiap komponen.

### 9.2 Theme Tokens

Gunakan token semantik: - `background` - `surface` - `surface-muted` -
`foreground` - `muted` - `border` - `primary` - `primary-hover` -
`success` - `warning` - `danger`

Tema Nebula pada referensi dapat menjadi inspirasi untuk dark theme,
tetapi warna Planify tetap mengikuti palet Indigo yang lebih tenang.

------------------------------------------------------------------------

## 10. Accessibility & Usability

-   Semua input memiliki label.
-   Tombol icon-only memiliki accessible name.
-   Navigasi dapat digunakan dengan keyboard.
-   Focus ring terlihat jelas.
-   Kontras teks memadai.
-   Status tidak hanya ditunjukkan melalui warna.
-   Gambar dokumentasi memiliki alt text yang sesuai.
-   Kalender menyediakan label tanggal yang dapat dibaca screen reader.
-   Dialog mengelola fokus dengan benar.
-   Area klik pada kontrol mobile cukup besar.

------------------------------------------------------------------------

## 11. Frontend Architecture Suggestion

Contoh struktur folder React:

``` text
src/
├── app/
│   ├── router/
│   └── providers/
├── components/
│   ├── ui/
│   ├── layout/
│   ├── events/
│   ├── calendar/
│   └── checklist/
├── features/
│   ├── auth/
│   ├── dashboard/
│   ├── events/
│   ├── categories/
│   ├── calendar/
│   ├── tasks/
│   ├── reminders/
│   ├── budget/
│   └── documentation/
├── hooks/
├── lib/
│   ├── api.ts
│   └── utils.ts
├── styles/
│   └── globals.css
└── main.tsx
```

Catatan: - Pisahkan komponen UI generik dari komponen domain. - Simpan
komunikasi HTTP dalam service atau API module. - Gunakan route
protection untuk halaman privat. - Jangan menaruh semua logic halaman
dalam satu komponen besar.

------------------------------------------------------------------------

## 12. Frontend States

Setiap halaman data perlu menangani empat kondisi:

1.  **Loading:** data sedang dimuat.
2.  **Success:** data berhasil ditampilkan.
3.  **Empty:** belum ada data.
4.  **Error:** data gagal dimuat.

Setiap form perlu menangani: - Default. - Invalid. - Submitting. -
Success. - Server error.

------------------------------------------------------------------------

## 13. MVP Design Priority

  Prioritas   Halaman / Komponen
  ----------- -----------------------------------
  P0          Login dan Register
  P0          App Shell, Sidebar, Topbar
  P0          Dashboard
  P0          Event List dan Event Form
  P0          Event Detail
  P0          Monthly Calendar
  P0          Checklist
  P1          Reminder
  P1          Budget
  P1          Documentation
  P2          Theme customization lanjutan
  P2          Export, integrasi, dan kolaborasi

P0 harus selesai terlebih dahulu. P1 dikerjakan jika alur utama sudah
stabil.

------------------------------------------------------------------------

## 14. Design QA Checklist

### Visual

-   [ ] Warna mengikuti token tema.
-   [ ] Tipografi konsisten.
-   [ ] Spacing antar elemen konsisten.
-   [ ] Tidak ada overflow horizontal.
-   [ ] Empty state tersedia.

### Responsive

-   [ ] Sidebar bekerja pada mobile.
-   [ ] Kalender dapat digunakan pada layar kecil.
-   [ ] Form nyaman digunakan di mobile.
-   [ ] Card tersusun dengan benar pada tablet dan desktop.

### Interaction

-   [ ] Hover, focus, active, dan disabled state tersedia.
-   [ ] Loading dan error feedback tersedia.
-   [ ] Delete action memiliki konfirmasi.
-   [ ] Keyboard navigation dapat digunakan.
-   [ ] Reduced motion dihormati.

### Consistency

-   [ ] Komponen menggunakan token yang sama.
-   [ ] Status acara konsisten.
-   [ ] Format tanggal konsisten.
-   [ ] Format mata uang menggunakan IDR.

------------------------------------------------------------------------

## 15. Referensi File

Dokumen ini disusun dengan mempertimbangkan file yang diberikan:

-   `demo.tsx`: penggunaan dasar `AstroAssociationTemplate`.
-   `demo-dark.tsx`: contoh konfigurasi tema gelap dengan palet Nebula.
-   `demo-custom.tsx`: contoh custom brand, palette, hero, section, dan
    callback.
-   `README(1).md`: deskripsi struktur template, sticky navigation, hero
    typography, section, interaksi, responsive behavior, theme, font,
    dan reduced motion.

**Catatan implementasi:** Astro Association Template merupakan referensi
visual dan interaksi, bukan template aplikasi Planify yang harus
digunakan secara langsung. Bangun komponen dashboard Planify sesuai
kebutuhan produk dan gunakan prinsip desain yang relevan dari referensi
tersebut.
