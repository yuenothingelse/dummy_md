 <div align="center">

# Supermarket App

**Aplikasi Manajemen Supermarket Berbasis Java Swing dan CLI**

<p>
  <img src="https://img.shields.io/badge/Java-17%2B-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java 17+" />
  <img src="https://img.shields.io/badge/Java%20Swing-GUI-007396?style=for-the-badge&logo=java&logoColor=white" alt="Java Swing" />
  <img src="https://img.shields.io/badge/CLI-Console-5382A1?style=for-the-badge" alt="CLI" />
  <img src="https://img.shields.io/badge/OOP-Project-6C63FF?style=for-the-badge" alt="OOP Project" />
</p>

Aplikasi pengelolaan supermarket yang dikembangkan menggunakan **Java** dengan dua pilihan antarmuka, yaitu **Graphical User Interface (GUI)** menggunakan Java Swing dan **Command Line Interface (CLI)**.

Proyek ini menyediakan fitur pengelolaan produk, pengguna, keranjang belanja, checkout, dan transaksi dengan dua peran pengguna, yaitu **Admin** dan **Customer**.

</div>

## ✨ Features

| Feature | Description |
| -------------------------------- | ---------------------------------------------- |
| 🔐 Authentication | Login untuk Admin dan Customer |
| 👤 User Management | Admin dapat melihat daftar pengguna |
| 📦 Product Management | Admin dapat menambah, melihat, mengubah, dan menghapus produk |
| 🛍️ Product Catalog | Customer dapat melihat daftar produk yang tersedia |
| 🔎 Product Search | Mencari produk berdasarkan informasi produk |
| ↕️ Product Sorting | Mengurutkan produk berdasarkan harga |
| 🛒 Shopping Cart | Menambahkan produk ke keranjang dan mengelola jumlah pembelian |
| 💳 Checkout | Membuat transaksi dengan metode pembayaran yang tersedia |
| 🧾 Transaction History | Customer dapat melihat riwayat dan detail transaksi |
| ✅ Transaction Verification | Admin dapat memeriksa dan memverifikasi transaksi |
| 🖥️ Multiple Interfaces | Menggunakan GUI Java Swing atau CLI |
| 🧱 Layered Structure | Memisahkan model, repository, service, dan antarmuka aplikasi |

---

## 🔀 Application Workflow

### 👤 Admin

Admin memiliki akses untuk mengelola data utama dan memantau transaksi pada aplikasi.

1. Admin melakukan login menggunakan akun Admin.
2. Admin melihat daftar produk yang tersedia.
3. Admin dapat menambahkan, mengubah, atau menghapus produk.
4. Admin dapat melihat daftar pengguna yang terdaftar.
5. Admin memeriksa transaksi yang dibuat oleh Customer.
6. Admin memverifikasi transaksi dan melihat detail transaksi.

### 🛒 Customer

Customer menggunakan aplikasi untuk melihat produk dan melakukan pembelian.

1. Customer melakukan login menggunakan akun Customer.
2. Customer melihat katalog produk.
3. Customer dapat mencari dan mengurutkan produk.
4. Customer menambahkan produk ke keranjang belanja.
5. Customer mengatur isi keranjang dan melanjutkan checkout.
6. Customer memilih metode pembayaran yang tersedia.
7. Customer dapat melihat riwayat serta detail transaksi.

---

## 🔗 Technologies

| Technology | Usage |
| -------------------------------- | -------------------------------- |
| Java 17+ | Bahasa pemrograman utama |
| Java Swing | Pengembangan antarmuka grafis |
| Java AWT | Komponen antarmuka dan penanganan event |
| Java Collections (`HashMap`) | Penyimpanan data sementara di memori |
| SQLite (schema draft) | Rancangan skema database pada `db/schema.sql` |
| `javac` / `java` | Kompilasi dan menjalankan aplikasi |

**Catatan:** Aplikasi saat ini menggunakan repository berbasis in-memory (`HashMap`). File `db/schema.sql` merupakan rancangan skema SQLite dan belum dihubungkan dengan implementasi aplikasi.

---

## 🗂️ Project Structure

```text
supermarket-app/
├── db/
│   └── schema.sql
│
├── src/
│   └── supermarket/
│       ├── Main.java
│       ├── AppContext.java
│       │
│       ├── exception/
│       │   ├── AppException.java
│       │   ├── AuthenticationException.java
│       │   ├── DataNotFoundException.java
│       │   └── OutOfStockException.java
│       │
│       ├── model/
│       │   ├── Admin.java
│       │   ├── Customer.java
│       │   ├── Product.java
│       │   ├── Transaction.java
│       │   ├── TransactionItem.java
│       │   ├── User.java
│       │   └── ...
│       │
│       ├── repository/
│       │   ├── Repository.java
│       │   ├── ProductRepository.java
│       │   ├── TransactionRepository.java
│       │   ├── UserRepository.java
│       │   └── memory/
│       │
│       ├── service/
│       │   ├── ProductService.java
│       │   ├── TransactionService.java
│       │   └── UserService.java
│       │
│       ├── ui/                 # CLI
│       │   ├── AdminMenu.java
│       │   ├── CustomerMenu.java
│       │   └── ...
│       │
│       └── gui/                # Java Swing Interface
│           ├── MainGUI.java
│           ├── LoginFrame.java
│           ├── AdminFrame.java
│           ├── CustomerFrame.java
│           └── ...
│
├── run-gui.bat
├── README.md
└── LICENSE
```

---

## 📋 Requirements

Sebelum menjalankan proyek, pastikan perangkat telah memiliki:

- ☕ **Java Development Kit (JDK) 17 atau versi lebih baru**
- 💻 Terminal / Command Prompt atau IDE seperti Visual Studio Code
- 🖥️ Lingkungan desktop yang mendukung Java Swing (untuk mode GUI)

Periksa instalasi Java melalui perintah berikut:

```bash
java -version
javac -version
```

---

## ▶️ Run the Project

Jalankan seluruh perintah dari direktori utama proyek (direktori yang berisi folder `src/`).

### macOS / Linux

**1. Kompilasi source code**

```bash
mkdir -p out
javac --release 17 -d out $(find src -name "*.java")
```

**2. Jalankan mode GUI**

```bash
java -cp out supermarket.gui.MainGUI
```

**Atau jalankan mode CLI**

```bash
java -cp out supermarket.Main
```

### Windows (PowerShell)

**1. Kompilasi source code**

```powershell
New-Item -ItemType Directory -Force out
javac --release 17 -d out (Get-ChildItem -Path src -Recurse -Filter *.java).FullName
```

**2. Jalankan mode GUI**

```powershell
java -cp out supermarket.gui.MainGUI
```

**Atau jalankan mode CLI**

```powershell
java -cp out supermarket.Main
```

### Windows (Command Prompt)

```bat
if not exist out mkdir out
dir /s /b src\*.java > sources.txt
javac --release 17 -d out @sources.txt
java -cp out supermarket.gui.MainGUI
```

Untuk menjalankan mode CLI, ganti perintah terakhir dengan:

```bat
java -cp out supermarket.Main
```

### 💠 Windows GUI Script

Pengguna Windows juga dapat menjalankan aplikasi versi GUI melalui file berikut:

```text
run-gui.bat
```

---

## 🔑 Demo Accounts

Aplikasi menyediakan beberapa akun contoh yang diinisialisasi secara otomatis saat aplikasi dijalankan.

| Role | Username | Password |
| ---------------- | ---------------- | ---------------- |
| 👤 Admin | `admin` | `admin123` |
| 🛒 Customer | `budi` | `budi123` |

Data produk contoh juga akan diinisialisasi secara otomatis oleh aplikasi.

> **Penting:** Akun tersebut hanya digunakan untuk keperluan demonstrasi dan pengembangan. Jangan gunakan kredensial ini pada lingkungan produksi.

---

## 💾 Data Storage

Aplikasi saat ini menyimpan data menggunakan **in-memory repository berbasis `HashMap`**.

Artinya:

- Data contoh akan diinisialisasi setiap kali aplikasi dijalankan.
- Perubahan data selama aplikasi berjalan hanya disimpan sementara di memori.
- Perubahan produk dan transaksi tidak akan tersimpan setelah aplikasi ditutup.

File `db/schema.sql` berisi rancangan skema SQLite untuk struktur data aplikasi. Namun, SQLite **belum diintegrasikan** dengan implementasi Java saat ini.

---

## 👥 Development Team

Proyek ini dikembangkan secara kolaboratif oleh enam anggota tim dengan pembagian tugas sebagai berikut:

| GitHub | Nama | Pembagian Tugas |
| -------------------------------- | ---------------- | -------------------------------- |
| [@nailasyakira](https://github.com/nailasyakira) | Naila Syakira Bahri | Membuat folder `db` dan file `run-gui.bat`. Berkoordinasi serta membantu anggota lain ketika mengalami kendala. |
| [@PutriRahmatulUlya](https://github.com/PutriRahmatulUlya) | Putri Rahmatul 'Ulya | Membuat package `ui`, `Main.java`, dan `AppContext.java`. Membantu integrasi antarbagian program. |
| [@abrarMuda](https://github.com/abrarMuda) | Abrar Muda | Membuat package `model` dan `exception`. Memastikan setiap fitur berjalan sesuai fungsinya. |
| [@yuenothingelse](https://github.com/yuenothingelse) | Mirza Nur Akhyar | Membuat dokumentasi proyek melalui `README.md` serta memperbaiki error yang ditemukan selama pengujian. |
| [@xanxanhub](https://github.com/xanxanhub) | M. Ihsan Syahni | Membuat package `repository` dan `service`. Melakukan verifikasi serta pengujian akhir aplikasi. |
| [@Hafidhfrr](https://github.com/Hafidhfrr) | M. Hafidh Farras | Membuat package `gui` serta melakukan pengecekan dan pengujian program. |

---

## 📦 Repository Maintainer

**Naila Syakira Bahri**

GitHub: [@nailasyakira](https://github.com/nailasyakira)

Repository ini dikelola oleh Naila untuk mengatur, mengoordinasikan, dan memublikasikan source code proyek.

---

## 📌 Purpose

Proyek ini dikembangkan sebagai tugas kelompok pemrograman untuk menerapkan konsep **Object-Oriented Programming (OOP)** melalui pembuatan aplikasi manajemen supermarket.

Melalui proyek ini, anggota tim mempraktikkan beberapa hal berikut:

- 🧩 Menerapkan konsep pemrograman berorientasi objek.
- 🏗️ Merancang class, object, dan hubungan antarkomponen Java.
- 🗃️ Memisahkan logika aplikasi menggunakan model, repository, dan service.
- 🎨 Mengembangkan antarmuka desktop menggunakan Java Swing.
- ⌨️ Membangun antarmuka berbasis command line.
- 🔐 Menerapkan autentikasi dan pembagian hak akses berdasarkan peran pengguna.
- 🛒 Mengelola produk, keranjang belanja, dan transaksi.
- 🤝 Berkolaborasi dalam pengembangan proyek menggunakan Git dan GitHub.

<div align="center">

## Made with Java ☕ and teamwork

</div>
