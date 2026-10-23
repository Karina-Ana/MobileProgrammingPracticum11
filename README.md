# Tasbih Digital – Flutter GetX

## 📝 Deskripsi Singkat

Tasbih Digital merupakan aplikasi berbasis Flutter yang menerapkan **GetX** untuk mengelola state secara reaktif. Aplikasi ini memungkinkan pengguna menambah hitungan tasbih melalui tombol sidik jari dan mengatur ulang hitungan menggunakan tombol reset.

Nilai hitungan dan progress bar diperbarui secara otomatis setiap kali pengguna berinteraksi dengan aplikasi. Pengelolaan logika dilakukan melalui controller sehingga terpisah dari tampilan antarmuka.

## ✨ Fitur Utama

- **Penghitung Tasbih:** Menampilkan jumlah hitungan yang sedang berjalan.
- **Tombol Tambah:** Menambah hitungan melalui ikon sidik jari hingga maksimal 33.
- **Progress Bar:** Menampilkan perkembangan hitungan menuju target 33.
- **Tombol Reset:** Mengembalikan hitungan dan progress bar ke nilai awal.
- **Pembaruan Real-Time:** Memperbarui tampilan secara otomatis ketika nilai state berubah.
- **Pengelolaan State dengan GetX:** Memisahkan logika penghitung dari tampilan aplikasi.

## 🛠️ Teknologi yang Digunakan

- **Flutter & Dart** – Pengembangan aplikasi.
- **GetX** – Manajemen state reaktif.
- **simple_circular_progress_bar** – Dependency pendukung progress bar pada konfigurasi proyek praktikum.

## 📂 Struktur Proyek

```text
tasbih_getx/
├── lib/
│   ├── main.dart
│   ├── model/
│   ├── view/
│   │   └── home.dart
│   └── viewmodel/
│       └── tasbih_controller.dart
├── pubspec.yaml
└── README.md
```

## ⚙️ Cara Kerja Aplikasi

1. Aplikasi menampilkan hitungan awal sebesar `0`.
2. Pengguna menekan ikon sidik jari untuk menambah hitungan.
3. `TasbihController` memperbarui nilai `counter` dan `progress` selama hitungan belum mencapai 33.
4. Widget `Obx` memantau perubahan nilai reaktif dan memperbarui tampilan secara otomatis.
5. Tombol reset memanggil `resetCounter()` untuk mengembalikan hitungan dan progress ke `0`.

## 📚 Konsep Flutter yang Dipelajari

- **GetMaterialApp:** Menggunakan konfigurasi aplikasi yang mendukung fitur GetX.
- **GetxController:** Mengelola data dan logika aplikasi secara terpisah dari UI.
- **Variabel Reaktif (`.obs`):** Memungkinkan perubahan nilai dipantau secara otomatis.
- **Obx:** Memperbarui bagian UI yang bergantung pada variabel reaktif.
- **Get.put():** Membuat dan mendaftarkan controller agar dapat digunakan oleh tampilan.
- **Manajemen State:** Memahami perbedaan pendekatan `setState()` dan manajemen state reaktif menggunakan GetX.

## 🚀 Cara Menjalankan

1. Pastikan Flutter SDK dan editor kode telah terpasang.
2. Buka proyek `tasbih_getx` melalui VS Code atau Android Studio.
3. Tambahkan dependency berikut pada bagian `dependencies` di file `pubspec.yaml`:

   ```yaml
   dependencies:
     flutter:
       sdk: flutter
     get: ^4.6.5
     simple_circular_progress_bar: ^1.0.2
   ```

4. Jalankan perintah berikut pada terminal:

   ```bash
   flutter pub get
   ```

5. Jalankan aplikasi menggunakan perintah:

   ```bash
   flutter run
   ```

## 📌 Kesimpulan

Aplikasi Tasbih Digital menerapkan manajemen state menggunakan GetX untuk mengelola perubahan hitungan dan progress secara reaktif. Variabel `.obs` dan widget `Obx` memungkinkan UI diperbarui tanpa pemanggilan `setState()` secara manual. Pemisahan logika ke dalam `TasbihController` juga membantu membuat struktur kode lebih terorganisasi dan mudah dipelihara.
