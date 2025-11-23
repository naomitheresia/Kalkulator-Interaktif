# Nowmee Kalkulator

Sebuah aplikasi kalkulator berbasis web yang modern dan responsif, dibangun menggunakan JavaScript murni dan Tailwind CSS. Menyediakan fitur penyimpanan memori, catatan histori operasi, kontrol penuh via keyboard, serta mendukung operasi matematis kompleks dengan urutan prioritas yang tepat.

## Keunggulan Aplikasi

- **Kalkulasi Matematis Lengkap**: Mendukung operasi tambah (+), kurang (−), kali (×), dan bagi (÷)
- **Sistem Perhitungan Cerdas**: Menerapkan aturan prioritas operator PEMDAS/BODMAS secara otomatis
  - Misal: `5 + 3 × 2` menghasilkan `11` (perkalian dikerjakan terlebih dahulu)
  - Misal: `20 ÷ 4 + 5` menghasilkan `10` (pembagian didahulukan sebelum penjumlahan)
- **Sistem Penyimpanan Memori**:
  - **M+** - Menambah nilai aktif ke dalam memori
  - **M−** - Mengurangi nilai aktif dari memori
  - **MR** - Mengambil nilai tersimpan dari memori
  - **MC** - Mengosongkan memori
- **Panel Histori**: Mencatat hingga 5 operasi terakhir di sisi kiri layar
- **Kontrol via Keyboard**: Semua tombol dapat diakses menggunakan keyboard
- **Tampilan Adaptif**: Otomatis menyesuaikan dengan berbagai ukuran layar perangkat
- **Proteksi Error**: Menangani kasus pembagian nol dan input tidak valid

## Stack Teknologi

- HTML5
- CSS3 dengan framework Tailwind CSS (CDN)
- JavaScript Vanilla (tanpa library eksternal)
- Google Fonts - Inter
- Heroicons untuk ikon SVG

## Panduan Instalasi

### Akses Langsung

Cukup buka file `index.html` menggunakan browser modern seperti Chrome, Firefox, Safari, atau Edge.

### Setup Lokal

1. Clone repositori ini

```bash
git clone https://github.com/naomitheresia/Kalkulator-Interaktif.git
```

2. Navigasi ke folder project

```bash
cd Kalkulator-Interaktif
```

3. Jalankan file HTML

```bash
# Buka TA5_ppw.html dengan browser pilihan Anda
```

## Pintasan Keyboard

- **Tombol 0-9**: Memasukkan angka
- **Simbol (+, -, \*, /)**: Melakukan operasi
- **Enter atau =**: Menjalankan kalkulasi
- **Escape**: Menghapus semua (Clear All)
- **Backspace**: Menghapus karakter terakhir
- **.**: Memasukkan desimal

## Panduan Fitur Memori

### M+ (Tambah ke Memori)

Menyimpan atau menambahkan angka di layar ke dalam memori.

**Ilustrasi**: Jika layar menunjukkan 25, tekan M+, maka memori akan menyimpan 25. Bila memori sudah berisi 15, total memori menjadi 40.

### M− (Kurangi dari Memori)

Mengurangi angka di layar dari nilai yang tersimpan di memori.

**Ilustrasi**: Memori berisi 80, layar menampilkan 20, tekan M−, memori berubah menjadi 60.

### MR (Panggil Memori)

Menampilkan nilai yang tersimpan di memori ke layar utama.

**Ilustrasi**: Jika memori menyimpan 200, tekan MR, layar akan menampilkan 200.

### MC (Hapus Memori)

Mengosongkan atau mereset nilai memori kembali ke 0.

## Fitur Panel Histori

Panel histori berada di **sisi kiri** aplikasi dengan kemampuan:

- Mencatat **5 operasi terbaru** secara otomatis
- Menampilkan **rumus lengkap** beserta **hasilnya**
- Menggunakan **font monospace** untuk keterbacaan maksimal
- Tombol **Hapus Semua** untuk membersihkan catatan

## Arsitektur Kode

### Komponen HTML

- **Area Display**: Menampilkan angka input, ekspresi matematis, dan hasil
- **Indikator Memori**: Menunjukkan nilai tersimpan dengan ikon visual
- **Tombol Memori**: Baris khusus berisi MC, MR, M+, M−
- **Grid Kalkulator**: Susunan 4 kolom berisi semua tombol operasi
- **Panel Histori**: Sidebar kiri untuk tracking operasi sebelumnya

### Fungsi JavaScript Utama

#### Fungsi Input

- `inputNumber(num)` - Menangani input angka
- `inputDecimal()` - Menambahkan titik desimal
- `inputOperator(operator)` - Memproses operator matematis

#### Fungsi Kalkulasi

- `calculate()` - Mengeksekusi perhitungan dengan urutan prioritas benar
- `evaluateExpression(expr)` - Mengevaluasi string ekspresi matematis

#### Fungsi Tampilan

- `updateDisplay()` - Memperbarui tampilan layar
- `clearAll()` - Menghapus seluruh input (C)
- `clearEntry()` - Menghapus entry terakhir (CE)
- `deleteDigit()` - Menghapus satu digit terakhir

#### Fungsi Memori

- `memoryAdd()` - Operasi M+
- `memorySubtract()` - Operasi M−
- `memoryRecall()` - Operasi MR
- `memoryClear()` - Operasi MC

#### Fungsi Histori

- `addToHistory(calculation, result)` - Menyimpan operasi ke histori
- `renderHistory()` - Menampilkan ulang daftar histori
- `clearHistory()` - Menghapus seluruh histori

### Styling CSS

- **Desain minimalis** dengan palet warna netral
- **Efek hover interaktif** pada setiap tombol
- **Layout grid responsif** untuk semua perangkat
- **Typography monospace** untuk angka dan hasil
- **Shadow halus** untuk kedalaman visual

## Logika Prioritas Operator

Aplikasi ini menerapkan standar matematis internasional (PEMDAS/BODMAS):

1. **Perkalian (×) dan Pembagian (÷)** - Dikerjakan lebih dulu
2. **Penjumlahan (+) dan Pengurangan (−)** - Dikerjakan kemudian

### Contoh Operasi Berantai

```
5 + 3 × 2
= 5 + (3 × 2)
= 5 + 6
= 11 ✓

10 - 2 × 3
= 10 - (2 × 3)
= 10 - 6
= 4 ✓

20 ÷ 4 + 5
= (20 ÷ 4) + 5
= 5 + 5
= 10 ✓
```

## Penanganan Error

- **Pembagian nol**: Menampilkan peringatan dan mereset kalkulator
- **Ekspresi invalid**: Alert notifikasi error
- **Desimal ganda**: Mencegah input titik desimal berulang
- **Validasi input**: Memeriksa semua input sebelum eksekusi

## Kompatibilitas Browser

- ✅ Chrome (Disarankan)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ✅ Opera

**Persyaratan Minimum**: Browser modern dengan dukungan ES6+ JavaScript

## Desain Responsif

- **Layar Besar** (≥1024px): Tata letak 2 kolom, histori di sebelah kiri
- **Layar Sedang** (768px-1023px): Tata letak adaptif
- **Layar Kecil** (<768px): Tata letak vertikal, histori di bagian atas

## Lisensi

Proyek ini dikembangkan sebagai bagian dari tugas praktikum Pemrograman Web.

## Pengembang

Dibuat untuk memenuhi Tugas Akhir Percobaan 5: JavaScript Dasar pada Praktikum Pemrograman Web.

---

**Penting**: Aplikasi memerlukan koneksi internet untuk memuat Tailwind CSS dari CDN guna tampilan optimal.
