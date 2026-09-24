# Jawaban Pertanyaan - Praktikum 1 Pemrograman Web

| | |
|---|---|
| **Nama** | Rafa Muhammad Fauzan |
| **NIM** | 312510277 |
| **Kelas** | I251C |
| **Program Studi** | Teknik Informatika |
| **Mata Kuliah** | Pemrograman Web |

## 1. Apa fungsi deklarasi `<!DOCTYPE html>` pada dokumen HTML?

`<!DOCTYPE html>` adalah deklarasi tipe dokumen yang ditulis di baris paling awal file HTML. Fungsinya memberi tahu browser bahwa dokumen ini ditulis dengan standar **HTML5**, sehingga browser menampilkannya dalam *standards mode*. Tanpa deklarasi ini, browser bisa masuk ke *quirks mode*, yaitu mode kompatibilitas lama yang membuat tampilan halaman tidak konsisten antarbrowser. `<!DOCTYPE html>` bukan tag HTML, melainkan instruksi untuk browser, dan tidak memiliki tag penutup.

## 2. Apa perbedaan antara tag, elemen, dan atribut pada HTML?

| Istilah | Pengertian | Contoh |
|---|---|---|
| **Tag** | Penanda yang ditulis di dalam tanda kurung sudut `< >`. Ada tag pembuka dan tag penutup (yang diawali `/`). | `<p>` dan `</p>` |
| **Elemen** | Satu kesatuan utuh yang terdiri dari tag pembuka, isi (konten), dan tag penutup. | `<p>Halo dunia</p>` |
| **Atribut** | Informasi tambahan pada sebuah elemen, ditulis di dalam tag pembuka dengan format `nama="nilai"`. | `href="index.html"` |

Contoh gabungan dari kode praktikum:

```html
<a href="index.html">Beranda</a>
```

- `<a>` dan `</a>` adalah **tag**.
- `href="index.html"` adalah **atribut**.
- Keseluruhan `<a href="index.html">Beranda</a>` adalah **elemen**.

## 3. Apa perbedaan `<p>` dengan `<br>`? Jelaskan penggunaannya.

| | `<p>` | `<br>` |
|---|---|---|
| **Fungsi** | Membuat satu **paragraf**. | Membuat **baris baru** (*line break*). |
| **Tag penutup** | Ada (`</p>`). | Tidak ada (*void element*). |
| **Jarak** | Browser otomatis memberi jarak di atas dan di bawah paragraf. | Hanya pindah baris, tanpa jarak tambahan. |
| **Sifat** | Elemen *block*. | Elemen *inline*. |

Gunakan `<p>` untuk memisahkan paragraf yang berbeda. Gunakan `<br>` bila perlu pindah baris di dalam paragraf yang sama, misalnya pada alamat atau bait puisi:

```html
<p>
    Jl. Contoh No. 1<br>
    Bandung<br>
    Jawa Barat
</p>
```

`<br>` tidak sebaiknya dipakai untuk memberi jarak antarparagraf. Untuk keperluan itu gunakan `<p>`, atau CSS untuk mengatur jarak.

## 4. Apa fungsi atribut `href` pada tag `<a>`?

`href` (*hypertext reference*) menentukan **tujuan tautan**. Ketika pengguna mengklik teks di dalam tag `<a>`, browser membuka alamat yang tertulis di `href`. Nilainya bisa berupa:

- halaman lain di proyek yang sama: `href="halaman2.html"`
- website lain: `href="https://www.google.com"`
- bagian tertentu di halaman: `href="#keahlian"`
- alamat email: `href="mailto:nama@contoh.com"`

Tanpa atribut `href`, tag `<a>` tidak berfungsi sebagai tautan.

## 5. Apa perbedaan hyperlink ke halaman internal dengan hyperlink ke website eksternal?

| | Hyperlink internal | Hyperlink eksternal |
|---|---|---|
| **Tujuan** | Halaman lain di dalam website atau proyek yang sama. | Halaman di website lain. |
| **Penulisan alamat** | Cukup nama berkas atau *path* relatif. | URL lengkap beserta `https://`. |
| **Contoh** | `<a href="halaman2.html">Profil Mahasiswa</a>` | `<a href="https://www.google.com">Website Eksternal</a>` |
| **Ketergantungan** | Berada di bawah kendali kita sendiri dan tetap bisa dibuka tanpa internet. | Bergantung pada website lain. Jika alamatnya berubah atau website mati, tautan rusak. |

## 6. Apa fungsi atribut `src` dan `alt` pada tag `<img>`?

- **`src`** (*source*) berisi lokasi (path atau URL) berkas gambar yang akan ditampilkan. Tanpa `src`, tidak ada gambar yang dimuat.
- **`alt`** (*alternative text*) berisi teks pengganti yang memiliki tiga fungsi:
  1. Ditampilkan jika gambar gagal dimuat.
  2. Dibaca oleh *screen reader* sehingga pengguna tunanetra memahami isi gambar.
  3. Membantu mesin pencari memahami isi gambar (SEO).

```html
<img src="Image/Logo.png" alt="Logo Atos Family" width="250" height="200">
```

## 7. Apa perbedaan penggunaan `<ul>` dan `<ol>`?

| | `<ul>` (*unordered list*) | `<ol>` (*ordered list*) |
|---|---|---|
| **Penanda** | Bullet (titik). | Angka atau huruf berurutan. |
| **Dipakai untuk** | Item yang urutannya tidak penting. | Item yang urutannya penting, seperti langkah atau peringkat. |
| **Contoh di praktikum** | Daftar Keahlian (HTML, CSS, JavaScript). | Urutan Belajar dan Target Belajar. |

Keduanya memakai tag `<li>` untuk setiap item di dalamnya.

## 8. Apa yang terjadi jika path gambar pada atribut `src` salah?

Gambar tidak dapat dimuat. Browser menampilkan **ikon gambar rusak** (*broken image*) dan teks dari atribut `alt` sebagai penggantinya. Ruang gambar tetap disediakan sesuai `width` dan `height` jika ukuran ditulis, tetapi isinya kosong.

Penyebab umum path salah:

- nama folder atau file salah ketik;
- huruf besar dan kecil tidak sama, misalnya `image/` dan `Image/`. Ini penting di GitHub karena bersifat *case-sensitive*;
- ekstensi tidak sesuai, misalnya `.jpg` dan `.jpeg`;
- gambar belum dipindahkan ke folder yang dituju;
- file gambar belum ikut di-commit dan di-push.

## 9. Mengapa struktur heading `h1` sampai `h6` perlu digunakan secara terstruktur?

Heading membentuk kerangka (*outline*) dokumen, mirip judul, bab, dan subbab pada buku. `<h1>` adalah judul utama, `<h2>` sub-bagian, `<h3>` bagian di bawah `<h2>`, dan seterusnya. Struktur yang berurutan diperlukan karena:

1. **Keterbacaan:** pembaca mudah memahami hierarki dan alur isi halaman.
2. **Aksesibilitas:** pengguna *screen reader* sering berpindah antarheading untuk menavigasi halaman.
3. **SEO:** mesin pencari memakai heading untuk memahami topik dan bagian penting halaman.
4. **Pemeliharaan:** struktur yang jelas memudahkan pengembangan dan penataan tampilan dengan CSS.

Karena itu, heading dipilih berdasarkan **tingkat kepentingan**, bukan berdasarkan ukuran huruf. Sebaiknya hanya ada satu `<h1>` per halaman dan tingkatnya tidak dilompati (misalnya dari `<h1>` langsung ke `<h4>`). Untuk mengubah ukuran tampilan, gunakan CSS.

## 10. Apa fungsi komentar `<!-- ... -->` dalam kode HTML?

Komentar adalah catatan di dalam kode yang **tidak ditampilkan di browser** dan diabaikan saat halaman dirender. Fungsinya:

1. Memberi penjelasan pada bagian kode agar mudah dipahami, misalnya `<!-- Judul Utama -->`.
2. Menandai bagian-bagian halaman agar mudah dicari.
3. Menonaktifkan sementara sebagian kode tanpa menghapusnya.

