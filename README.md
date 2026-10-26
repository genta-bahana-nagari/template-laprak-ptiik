# Template Laporan Praktikum LaTeX

Template LaTeX untuk menyusun laporan praktikum dengan struktur yang rapi dan terorganisir.

## Struktur Proyek

- `main.tex`: File utama tempat mengatur metadata, package, dan struktur isi laporan.
- `references.bib`: File BibTeX untuk menyimpan referensi daftar pustaka.
- `images/`: Folder untuk menyimpan aset gambar (format `.png`, `.jpg`, `.pdf`).
- `chapters/`: Folder untuk memisahkan konten per bab agar file `main.tex` tetap bersih (misal: `pendahuluan.tex`, `pembahasan.tex`).

## Panduan Penggunaan

### 1. Persiapan
Pastikan sistem Anda memiliki distribusi LaTeX (TeX Live, MiKTeX, atau MacTeX). Jika menggunakan VS Code, disarankan menginstal ekstensi **LaTeX Workshop**.

### 2. Mengatur Laporan (`main.tex`)
- Buka `main.tex`.
- Edit bagian `\title`, `\author`, dan `\date` sesuai data laporan Anda.
- Gunakan perintah `\input{chapters/nama_file.tex}` untuk memanggil file konten yang tersimpan di dalam folder `chapters/`.

### 3. Mengelola Referensi (`references.bib`)
- Masukkan entri sitasi Anda ke dalam file `references.bib` menggunakan format BibTeX.
- Contoh:
  ```bibtex
  @online{sumber1,
    author = {Penulis},
    title  = {Judul Artikel},
    year   = {2026},
    url    = {https://contoh.com}
  }
  ```
- Panggil sitasi di teks dengan perintah `\cite{namaSumber}` atau `\parencite{namaSumber}`.

### 4. Menambahkan Gambar
- Simpan gambar ke folder `images/`.
- Masukkan gambar ke dalam laporan menggunakan perintah:
  ```latex
  \begin{figure}[H]
      \centering
      \includegraphics[width=0.8\textwidth]{images/nama_gambar.png}
      \caption{Keterangan Gambar}
  \end{figure}
  ```

### 5. Kompilasi
- **Lokal:** Jalankan kompilasi menggunakan alur `pdflatex` -> `biber` -> `pdflatex` (2x) untuk memastikan referensi dan TOC terupdate.
- **Overleaf:** Unggah seluruh isi folder ke proyek baru, pastikan file `main.tex` terpilih sebagai file utama, lalu klik tombol **Recompile**.
