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

Proyek ini menyediakan fitur pengelolaan produk, pengguna, keranjang belanja, checkout, dan transaksi dengan dua peran pengguna: **Admin** dan **Customer**.

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

## 🔄 Application Workflow

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

## 🛠️ Technologies

| Technology | Usage |
| -------------------------------- | -------------------------------- |
| ☕ Java 17+ | Programming language |
| 🖼️ Java Swing | Graphical User Interface |
| ⚙️ Java AWT | UI components and event handling |
| 🧰 Java Collections (`HashMap`) | Penyimpanan data sementara di memori |
| 🗄️ SQLite (schema draft) | Rancangan skema database pada `db/schema.sql` |
| 🛠️ `javac` / `java` | Compilation and execution |

**Note:** Aplikasi saat ini menggunakan repository berbasis in-memory (`HashMap`). File `db/schema.sql` merupakan rancangan skema SQLite dan belum dihubungkan ke implementasi aplikasi.

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

## 📋 Requirements

Before running the project, make sure you have:

- ☕ **Java Development Kit (JDK) 17 or newer**
- 💻 Terminal / Command Prompt, or an IDE such as Visual Studio Code
- 🖥️ Desktop environment that supports Java Swing (for GUI mode)

Check your Java installation:

```bash
java -version
javac -version
```

## 🚀 Run the Project

Run all commands from the project's root directory (the directory containing `src/`).

### 🍎 macOS / Linux

**1. Compile the source code**

```bash
mkdir -p out
javac --release 17 -d out $(find src -name "*.java")
```

**2. Run GUI mode**

```bash
java -cp out supermarket.gui.MainGUI
```

**Or run CLI mode**

```bash
java -cp out supermarket.Main
```

### 🪟 Windows (PowerShell)

**1. Compile the source code**

```powershell
New-Item -ItemType Directory -Force out
javac --release 17 -d out (Get-ChildItem -Path src -Recurse -Filter *.java).FullName
```

**2. Run GUI mode**

```powershell
java -cp out supermarket.gui.MainGUI
```

**Or run CLI mode**

```powershell
java -cp out supermarket.Main
```

### 🪟 Windows (Command Prompt)

```bat
if not exist out mkdir out
dir /s /b src\*.java > sources.txt
javac --release 17 -d out @sources.txt
java -cp out supermarket.gui.MainGUI
```

To run CLI mode, replace the last command with:

```bat
java -cp out supermarket.Main
```

### ⚡ Windows GUI Script

You can also run the GUI version on Windows by executing:

```text
run-gui.bat
```

## 🔑 Demo Accounts

The application initializes sample accounts when it starts.

| Role | Username | Password |
| ---------------- | ---------------- | ---------------- |
| 🛠️ Admin | `admin` | `admin123` |
| 🛒 Customer | `budi` | `budi123` |

Sample products are also initialized automatically by the application.

> **Important:** These credentials are for demonstration and development purposes only. Do not use them in a production environment.

## 💾 Data Storage

The current application stores data using **in-memory repositories based on `HashMap`**.

This means:

- Sample data is initialized when the application starts.
- Changes made during a session are stored temporarily in memory.
- Product and transaction changes are not retained after the application is closed.

The `db/schema.sql` file contains a draft SQLite schema for the application's data. However, SQLite has **not yet been integrated** with the Java application.

## 👥 Development Team

This project was developed collaboratively by:

| GitHub | Name |
| -------------------------------- | ---------------- |
| [@abrarMuda](https://github.com/abrarMuda) | Abrar |
| [@xanxanhub](https://github.com/xanxanhub) | Ihsan |
| [@Hafidhfrr](https://github.com/Hafidhfrr) | Hafidh |
| [@PutriRahmatulUlya](https://github.com/PutriRahmatulUlya) | Putri |
| [@nailasyakira](https://github.com/nailasyakira) | Naila |
| [@yuenothingelse](https://github.com/yuenothingelse) | Mirza |

## 📦 Repository Maintainer

**Naila**

GitHub: [@nailasyakira](https://github.com/nailasyakira)

The repository is maintained by Naila to organize, manage, and publish the project source code.

## 🎯 Purpose

This project was developed as a programming group project to apply object-oriented programming concepts through the development of a supermarket management application.

Through this project, the development team practiced:

- 🧩 Applying object-oriented programming concepts.
- 🏗️ Designing Java classes, objects, and relationships.
- 🗃️ Separating application logic using model, repository, and service layers.
- 🎨 Developing desktop interfaces with Java Swing.
- ⌨️ Building a command-line interface.
- 🔐 Implementing authentication and role-based access.
- 🛒 Managing products, shopping carts, and transactions.
- 🤝 Collaborating through Git and GitHub.

<div align="center">

## Made with Java ☕ and teamwork

</div>
