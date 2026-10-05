# Laporan Praktikum 3: CSS Dasar
**Mata Kuliah:** Pemrograman Web  
**Dosen Pengampu:** Agung Nugroho, S.Kom., M.Kom.  
**Universitas Pelita Bangsa**

---

## 👨‍💻 Data Diri Mahasiswa
* **Nama:** Guntur Cahyadewangga
* **NIM:** 312510265
* **Program Studi:** Teknik Informatika
* **Kelas / Semester:** I251C / Semester 3

---

## 📝 Jawaban Pertanyaan Modul

1. **Lakukan eksperimen dengan mengubah dan menambah properti dan nilai pada kode CSS dengan mengacu pada CSS Cheat Sheet yang diberikan pada file terpisah dari modul ini.**
   * **Penjelasan Eksperimen:**
     * Mengubah warna latar belakang navigasi pada `nav` menjadi warna hijau (`#20A759`).
     * Menambahkan efek `:hover` pada link navigasi (`nav a:hover`) sehingga warna background berubah saat diarahkan oleh kursor.
     * Mengubah warna tombol pada kelas `.btn-primary` menjadi warna merah (`#e73c3c`) dan menambahkan properti `border-radius` agar sudut tombol terlihat lebih melengkung.

2. **Apa perbedaan pendeklarasian CSS elemen `h1 {...}` dengan `#intro h1 {...}`? Berikan penjelasannya!**
   * `h1 {...}`: Merupakan **Element Selector**. Aturan CSS ini akan berlaku secara umum pada **seluruh** elemen `<h1>` yang ada di dalam dokumen HTML.
   * `#intro h1 {...}`: Merupakan **Descendant Selector**. Aturan CSS ini **hanya** berlaku spesifik pada elemen `<h1>` yang berada **di dalam** elemen pembungkus ber-ID `intro` (`<div id="intro">`). Selector ini memiliki tingkat spesifisitas yang lebih tinggi daripada `h1` biasa.

3. **Apabila ada deklarasi CSS secara internal, lalu ditambahkan CSS eksternal dan inline CSS pada elemen yang sama. Deklarasi manakah yang akan ditampilkan pada browser? Berikan penjelasan dan contohnya!**
   * **Jawaban:** Deklarasi **Inline CSS** yang akan ditampilkan pada browser.
   * **Penjelasan:** Inline CSS memiliki tingkat prioritas (*specificity*) paling tinggi dibandingkan Internal CSS maupun Eksternal CSS karena dituliskan langsung pada tag elemen HTML bersangkutan.
   * **Contoh:**
     * *Internal CSS pada `<head>`:* `p { color: blue; }`
     * *Inline CSS pada tag `<p>`:* `<p style="color: red;">Teks ini</p>`
     * *Hasil:* Teks akan berwarna **MERAH** karena inline CSS mengabaikan aturan warna biru dari internal/eksternal CSS.

4. **Pada sebuah elemen HTML terdapat ID dan Class, apabila masing-masing selector tersebut terdapat deklarasi CSS, maka deklarasi manakah yang akan ditampilkan pada browser? Berikan penjelasan dan contohnya! (`<p id="paragraf-1" class="text-paragraf">`)**
   * **Jawaban:** Deklarasi CSS pada **ID Selector** yang akan ditampilkan.
   * **Penjelasan:** ID Selector (`#`) memiliki bobot spesifisitas (*specificity weight*) yang lebih tinggi daripada Class Selector (`.`). Browser akan memprioritaskan aturan yang ditulis pada ID selector.
   * **Contoh:**
     ```css
     #paragraf-1 { color: red; }       /* ID Selector (Menang) */
     .text-paragraf { color: blue; }   /* Class Selector */
     ```
     ```html
     <p id="paragraf-1" class="text-paragraf">Teks ini akan berwarna merah.</p>
     ```

---

## 🛠️ Langkah-Langkah Praktikum di `lab2_css_dasar.html` & `style_eksternal.css`

### Langkah 1: Membuat Dokumen HTML Dasar
* **Penjelasan:** Membuat struktur dasar HTML pada file `lab2_css_dasar.html` yang mencakup tag `<header>`, `<nav>`, serta elemen pembungkus `<div id="intro">` beserta tautan navigasi dan teks konten awal.
* **Screenshot Hasil:**  
  ![Langkah 1](image/L1.png)

### Langkah 2: Mendeklarasikan CSS Internal
* **Penjelasan:** Menambahkan tag `<style>` pada bagian `<head>` dokumen untuk mengatur tampilan font `body`, tata letak `<header>`, warna teks `<h1>`, serta pengaturan tampilan tag miring `<i>` di dalam judul.
* **Screenshot Hasil:**  
  ![Langkah 2](image/L2.png)

### Langkah 3: Menambahkan Inline CSS
* **Penjelasan:** Menyisipkan atribut `style="..."` langsung pada elemen `<p>` untuk mengatur posisi teks menjadi rata tengah (*center*) atau rata kanan-kiri (*justify*) serta menyesuaikan warna teksnya.
* **Screenshot Hasil:**  
  ![Langkah 3](image/L3.png)

### Langkah 4: Membuat CSS Eksternal
* **Penjelasan:** Membuat file baru `style_eksternal.css` untuk mengatur navigasi `<nav>` dan tautannya (`nav a`), kemudian menghubungkan file tersebut ke dokumen HTML menggunakan tag `<link rel="stylesheet" href="style_eksternal.css">` pada bagian `<head>`.
* **Screenshot Hasil:**  
  ![Langkah 4](image/L4.png)

### Langkah 5: Menambahkan CSS Selector (ID dan Class)
* **Penjelasan:** Menambahkan ID selector (`#intro` dan `#intro h1`) untuk latar belakang area konten utama, serta Class selector (`.button` dan `.btn-primary`) pada file `style_eksternal.css` untuk memformat tampilan tombol tautan "Informasi selengkapnya.".
* **Screenshot Hasil Tampilan Akhir:**  
  ![Screenshot Hasil Akhir](image/L5.png)