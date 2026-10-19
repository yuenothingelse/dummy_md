# 🧮 NewtonLab — Kalkulator Penyelesaian Persamaan Nonlinier

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Tkinter](https://img.shields.io/badge/GUI-Tkinter-8B7CFF?style=for-the-badge)
![SymPy](https://img.shields.io/badge/Math-SymPy-3B5526?style=for-the-badge)
![NumPy](https://img.shields.io/badge/Compute-NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Plot-Matplotlib-11557C?style=for-the-badge)

**NewtonLab** adalah aplikasi kalkulator berbasis antarmuka grafis (GUI) menggunakan bahasa pemrograman Python untuk mencari akar penyelesaian persamaan nonlinier dengan **Metode Newton-Raphson**. Aplikasi ini dikembangkan sebagai **Project UTS Praktikum Komputasi Numerik C**.

---

## 📌 Daftar Isi
* [✨ Fitur Utama](#-fitur-utama)
* [👥 Tim Pengembang](#-tim-pengembang)
* [🛠️ Teknologi & Library](#️-teknologi--library)
* [🚀 Panduan Penggunaan & Sintaks Input](#-panduan-penggunaan--sintaks-input)
* [💻 Bedah Kode Interaktif (main.py)](#-bedah-kode-interaktif-mainpy)
* [📸 Tampilan Aplikasi (Screenshot)](#-tampilan-aplikasi-screenshot)

---

## ✨ Fitur Utama

Aplikasi ini dirancang dengan tema dark mode modern (`#101522` & `#8B7CFF`) dan memenuhi seluruh ketentuan teknis projek:

| Fitur | Deskripsi Implementasi |
| :--- | :--- |
| **Input Dinamis Pengguna** | Pengguna bebas memasukkan fungsi f(x), tebakan awal (x₀), batas toleransi error, dan jumlah iterasi maksimum. |
| **Turunan Simbolik Otomatis** | Menghitung turunan pertama f'(x) secara otomatis di balik layar menggunakan `SymPy` tanpa perlu dihitung manual oleh pengguna. |
| **Tabel Transparansi Iterasi** | Menampilkan tahapan perhitungan secara rinci pada setiap iterasi (n, xₙ, f(xₙ), f'(xₙ), xₙ₊₁, dan nilai Error) dengan presisi 8 angka di belakang koma (`:.8f`). |
| **Kriteria Berhenti Ganda** | Perhitungan berhenti otomatis saat nilai error mencapai batas toleransi (`error <= tolerance`) atau saat mencapai batas iterasi maksimum. |
| **Visualisasi Grafik Interaktif** | Menggambar kurva fungsi f(x) pada rentang `root - 5` hingga `root + 5` beserta penanda titik potong akarnya pada garis y = 0. |
| **Validasi & Penanganan Error** | Mendeteksi input fungsi kosong, kesalahan sintaks matematika, toleransi <= 0, iterasi maksimum < 1, hingga kondisi turunan mendekati nol (`abs(dfx) < 1e-12`) melalui jendela pop-up `messagebox`. |

---

## 👥 Tim Pengembang

Project ini dikerjakan secara berkelompok untuk implementasi **Metode Newton-Raphson** pada **Praktikum Komputasi Numerik C**:

| No | Nama Lengkap | NIM | Peran |
| :-: | :--- | :---: | :--- |
| 1 | *(Nama Anggota 1)* | *(NIM)* | Developer / UI & Algoritma |
| 2 | *(Nama Anggota 2)* | *(NIM)* | Dokumentasi & Pengujian |
| 3 | *(Nama Anggota 3)* | *(NIM)* | Materi Presentasi & Analisis |

---

## 🛠️ Teknologi & Library

Program ini dibangun menggunakan library Python berikut:
* **`tkinter` (`tk`, `ttk`, `messagebox`)** — Membangun antarmuka pengguna bertema `"clam"`, tabel iterasi (`Treeview`), dan dialog pesan peringatan error.
* **`sympy`** — Melakukan parsing string matematika menjadi ekspresi simbolik (`sympify`), mencari turunan pertama (`diff`), dan mengonversi ekspresi ke fungsi numerik (`lambdify`).
* **`numpy`** — Mengolah komputasi numerik dan membangkitkan 500 titik koordinat sumbu-x (`linspace`) untuk kebutuhan pembuatan grafik.
* **`matplotlib` (`Figure`, `FigureCanvasTkAgg`)** — Merender grafik fungsi f(x) dan titik akarnya langsung ke dalam kanvas jendela aplikasi Tkinter.

<details>
<summary><b>📦 Klik untuk melihat cara instalasi Library & Menjalankan Program</b></summary>
<br>

1. Pastikan Python sudah terinstal di perangkat Anda.
2. Instal library eksternal yang dibutuhkan melalui terminal:
   ```bash
   pip install numpy sympy matplotlib
