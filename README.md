# ASJAIROBI_2210010643_PENGELOLAANKRS

# Pengelolaan KRS

## Deskripsi Proyek

Aplikasi **Pengelolaan KRS** ini dirancang untuk membantu pengelolaan data mahasiswa dan proses pengambilan KRS (Kartu Rencana Studi). Aplikasi ini memiliki antarmuka berbasis Swing dan menggunakan MySQL sebagai database backend.

### Fitur Utama

- Manajemen data mahasiswa:
  - Tambah, edit, dan hapus data mahasiswa.
  - Lihat daftar mahasiswa dalam tabel.
- Manajemen KRS:
  - Tambah, edit, dan hapus data pengambilan KRS.
  - Lihat daftar KRS dalam tabel.
- Fitur pencetakan untuk data mahasiswa dan KRS.

## Struktur File

- **PengelolaanKRS.java**: File utama yang berisi implementasi logika aplikasi dan pengaturan antarmuka pengguna.
- **PengelolaanKRS.form**: File pendukung untuk desain GUI menggunakan NetBeans GUI Builder.

## Persyaratan Sistem

- **Java Development Kit (JDK)**: Versi 8 atau lebih baru.
- **Database**: MySQL Server.
- **IDE**: Direkomendasikan menggunakan NetBeans IDE untuk memanfaatkan GUI Builder.

## Cara Menggunakan

### 1. Persiapan Database

1. Pastikan MySQL Server terinstal dan berjalan.
2. Buat database dengan nama `pengelolaan_krs`.
3. Jalankan skrip berikut untuk membuat tabel yang diperlukan:

```sql
CREATE TABLE mahasiswa (
    npm VARCHAR(15) PRIMARY KEY,
    nama VARCHAR(100),
    tanggal_lahir DATE,
    jurusan VARCHAR(50),
    no_telepon VARCHAR(15),
    email VARCHAR(100)
);

CREATE TABLE pengambilan_krs (
    id_pengambilan INT AUTO_INCREMENT PRIMARY KEY,
    npm VARCHAR(15),
    kode_mata_kuliah VARCHAR(10),
    nama_mata_kuliah VARCHAR(100),
    sks INT,
    semester VARCHAR(10),
    tahun_akademik INT,
    nama_dosen VARCHAR(100),
    FOREIGN KEY (npm) REFERENCES mahasiswa(npm)
);
```

4. Perbarui informasi koneksi database di dalam file `PengelolaanKRS.java`:

```java
String url = "jdbc:mysql://localhost:3306/pengelolaan_krs";
String user = "root"; // Ganti dengan username MySQL Anda.
String password = ""; // Ganti dengan password MySQL Anda.
```

### 2. Menjalankan Aplikasi

1. Buka proyek ini menggunakan NetBeans IDE.
2. Pastikan semua dependensi telah terpenuhi.
3. Jalankan file `PengelolaanKRS.java`.

## Panduan Penggunaan

### A. Modul Mahasiswa

1. Isi data mahasiswa pada formulir.
2. Klik tombol **Tambah** untuk menambahkan data baru.
3. Pilih data dari tabel mahasiswa, lalu klik **Edit** untuk memperbarui atau **Hapus** untuk menghapus data.

### B. Modul KRS

1. Pilih NPM dari daftar dropdown yang tersedia.
2. Isi data mata kuliah dan informasi lainnya.
3. Klik tombol **Tambah** untuk menambahkan KRS baru.
4. Pilih data dari tabel KRS, lalu klik **Edit** untuk memperbarui atau **Hapus** untuk menghapus data.

### C. Pencetakan

- Klik tombol **Cetak** pada modul mahasiswa atau KRS untuk mencetak data yang ditampilkan pada tabel.

## Catatan Penting

- Pastikan semua input telah diisi dengan benar sebelum menyimpan data.
- Perhatikan format tanggal lahir (`YYYY-MM-DD`) pada modul mahasiswa.
- Periksa koneksi database jika aplikasi tidak dapat memuat data atau menyimpan perubahan.
