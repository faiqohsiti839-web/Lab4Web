# Lab4Web
Tugas post test praktikum 4

# Lab4Web - Praktikum 4: CSS Layout

| | |
|---|---|
| **Nama** | Siti Faiqoh Almarufi |
| **NIM** | 312510168 |
| **Program Studi** | Teknik Informatika, Fakultas Teknik |
| **Kampus** | Universitas Pelita Bangsa |
| **Mata Kuliah** | Pemrograman Web |

## Tujuan Praktikum

1. Memahami struktur dasar pembuatan layout.
2. Memahami konsep box element.
3. Memahami CSS Floating.
4. Memahami HTML5 Semantic Element.
5. Membuat layout web sederhana.

## Struktur Folder

```
Lab4Web/
├── README.md
├── screenshots/
├── lab4_box/
│   └── lab4_box.html
└── lab4_layout/
    ├── home.html
    ├── artikel.html
    ├── about.html      (Tugas 1)
    ├── kontak.html     (Tugas 2)
    └── style.css
```

---

## Bagian 1 - Box Element dan CSS Float (`lab4_box.html`)

### Langkah 1: Membuat dokumen HTML dasar
Dibuat file `lab4_box.html` berisi struktur HTML5 dasar (`DOCTYPE`, `head`, `body`) dengan elemen semantik `<header>` yang berisi judul `<h1>Box Element</h1>`.

### Langkah 2: Membuat box element
Di dalam `<section>` ditambahkan tiga elemen `<div>` (`div1`, `div2`, `div3`). Tanpa float, setiap `div` tampil menumpuk ke bawah karena merupakan elemen block.

```html
<section>
    <div class="div1">Div 1</div>
    <div class="div2">Div 2</div>
    <div class="div3">Div 3</div>
</section>
```

### Langkah 3: CSS Float Property
Pada `<style>` ditambahkan `float: left` dan `padding: 10px` untuk semua `div`, serta warna latar berbeda untuk tiap kelas. Hasilnya, ketiga `div` tampil berdampingan secara horizontal dan lebarnya menyesuaikan isi.

```css
div {
    float: left;
    padding: 10px;
}
.div1 { background: red; }
.div2 { background: yellow; }
.div3 { background: green; }
```
<img width="638" height="350" alt="Screenshot 2026-10-18 214044" src="https://github.com/user-attachments/assets/70a42310-0edc-449e-a485-02e2532e1b08" />


### Langkah 4: Mengatur Clearfix
Ditambahkan `div4`. Karena `div1` sampai `div3` mengambang, `div4` akan ikut naik ke samping jika tidak diatur. Property `clear: left` dan `float: none` membuat `div4` turun ke baris baru di bawah elemen float.

```css
.div4 {
    background-color: blue;
    clear: left;
    float: none;
}
```

<img width="638" height="356" alt="Screenshot 2026-10-18 214329" src="https://github.com/user-attachments/assets/b3d6d54a-60f2-43b9-80cd-2d0a51ab6066" />
### Eksperimen nilai `clear`

| Nilai | Efek |
|---|---|
| `left` | Elemen turun di bawah elemen yang float ke **kiri** (dipakai pada latihan ini). |
| `right` | Elemen hanya menghindari elemen float ke **kanan**; karena `div1-3` float kiri, `div4` tidak turun dan tampil di samping/menumpuk dengan elemen float. |
| `both` | Elemen turun di bawah elemen float **kiri maupun kanan**. Paling aman dipakai (misalnya pada footer). |
| `none` | Default; elemen tidak dipengaruhi float sebelumnya. |

---

## Bagian 2 - Layout Web Sederhana (`lab4_layout`)

### Langkah 1: Membuat folder dan file
Dibuat folder `lab4_layout` berisi `home.html` dan `style.css`. File HTML menghubungkan CSS dengan `<link rel="stylesheet" href="style.css">` dan seluruh isi dibungkus `<div id="container">`.

<img width="640" height="359" alt="Screenshot 2026-10-18 215422" src="https://github.com/user-attachments/assets/c17fb6de-d199-435c-b2e3-c595cc989a0f" />

### Langkah 2: Kerangka layout dengan semantic element
Kerangka halaman disusun dengan elemen semantik HTML5:

| Elemen | Fungsi |
|---|---|
| `<header>` | Judul/kepala situs |
| `<nav>` | Menu navigasi (Home, Artikel, About, Kontak) |
| `<section id="hero">` | Panel utama/banner |
| `<section id="wrapper">` | Pembungkus main content dan sidebar |
| `<section id="main">` | Konten utama |
| `<aside id="sidebar">` | Konten samping (widget) |
| `<footer>` | Kaki halaman |


### Langkah 3: CSS dasar dan header
Ditambahkan import Google Font *Open Sans*, reset CSS (`* { margin: 0; padding: 0; }`), gaya `body`, `#container` (lebar 980px, `margin: 0 auto` agar di tengah, dengan `box-shadow`), serta gaya `header`.

<img width="638" height="357" alt="Screenshot 2026-10-18 215922" src="https://github.com/user-attachments/assets/23c753ca-b3c4-4013-9f88-26d220aa84ee" />

### Langkah 4: Navigasi
`nav` diberi latar biru. Tautan `nav a` dibuat `display: inline-block` dengan padding sehingga tampil mendatar, dan `nav a.active, nav a:hover` diberi warna lebih terang.

<img width="637" height="356" alt="Screenshot 2026-10-18 220423" src="https://github.com/user-attachments/assets/71ee36d0-b0ef-4155-8379-9faf00e34194" />

### Langkah 5: Hero Panel
Ditambahkan `<section id="hero">` berisi judul, paragraf, dan tombol *Learn more*. CSS memberi latar abu-abu, padding, serta ukuran font.

<img width="638" height="358" alt="Screenshot 2026-10-18 221126" src="https://github.com/user-attachments/assets/8593ce8d-f626-4d07-82e5-9f7aaf21a9a7" />

### Langkah 6: Layout Main dan Sidebar
`#main` (lebar 640px) dan `#sidebar` (lebar 260px) sama-sama diberi `float: left` sehingga tampil berdampingan. Total lebar 640 + 260 + padding 2 x (20 + 20) = 980px, sama dengan lebar container.

### Langkah 7: Sidebar Widget
Ditambahkan dua `div.widget-box` di dalam `<aside>`: satu berisi daftar link, satu berisi teks. CSS memberi border, judul berlatar biru, dan efek hover pada tiap link.

<img width="634" height="355" alt="Screenshot 2026-10-18 222050" src="https://github.com/user-attachments/assets/d8641ad3-f4dd-498b-bec7-53c8038230f6" />

### Langkah 8: Footer
`footer` diberi `clear: both` agar berada di bawah elemen float (main dan sidebar), lengkap dengan latar gelap dan teks terang.

<img width="638" height="359" alt="Screenshot 2026-10-18 222316" src="https://github.com/user-attachments/assets/b4aa87ab-8236-42e1-8be5-289552824eef" />

### Langkah 9: Elemen pada Main Content
Di `#main` ditambahkan `div.row` berisi tiga `div.box` (gambar bulat, heading, deskripsi, tombol *View detail*). Setiap `.box` memakai `width: 33.333333%` dan `float: left` agar membentuk tiga kolom. Pseudo-element `.row:after { clear: both; }` (teknik **clearfix**) menjaga agar tinggi `.row` tetap mengikuti isinya.

<img width="635" height="356" alt="Screenshot 2026-10-18 223735" src="https://github.com/user-attachments/assets/502d63cf-8b88-4afc-a9af-caed310fcc3f" />

### Langkah 10: Content Artikel
Ditambahkan dua `<article class="entry">`, dipisahkan `<hr class="divider">`. Gambar pada artikel pertama float kiri, sedangkan artikel kedua memakai class `right-img` agar gambar float kanan.

<img width="638" height="356" alt="Screenshot 2026-10-18 224640" src="https://github.com/user-attachments/assets/43680b68-39c5-470e-9e6e-b1899fac7d5c" />

### Catatan perbaikan kode modul
- Pada modul, HTML memakai `class="rightimg"` sedangkan CSS memakai `.right-img`, sehingga tidak cocok. Pada kode ini dipakai `right-img` di keduanya.
- Selector `box img` pada modul tidak memiliki titik; diperbaiki menjadi `.box img`.
- Class `.btn`, `.btn-large`, dan `.btn-default` dilengkapi CSS-nya agar tombol tampil seperti Gambar 4.7.

---

## Pertanyaan dan Tugas

### Tugas 1 - Layout menu About (`about.html`)
Halaman *single layout* dengan struktur yang sama (header, nav, hero, main, sidebar, footer). Konten utama berisi:
- **Deskripsi** diri (foto profil bulat + penjelasan singkat),
- **Keahlian** dalam bentuk daftar,
- **Portfolio** dalam tiga kolom (`.box` + float) yaitu Lab2Web, Lab3Web, dan Lab4Web.

Menu **About** diberi `class="active"` pada navigasi.

<img width="638" height="351" alt="Screenshot 2026-10-18 224950" src="https://github.com/user-attachments/assets/aec317c8-36ce-4732-b96d-75305b5cedac" />
<img width="639" height="359" alt="Screenshot 2026-10-18 224959" src="https://github.com/user-attachments/assets/8e650583-8390-4331-a066-fe8b12c69ba1" />

### Tugas 2 - Layout menu Contact (`kontak.html`)
Halaman berisi formulir dengan field:
- Nama (`text`), Email (`email`), No. Telepon (`tel`),
- Subjek (`select`),
- Message (`textarea`),
- Tombol **Kirim** (`submit`) dan **Reset**.

Field diberi atribut `required` untuk validasi dasar dan `label` dengan `for` yang terhubung ke `id` input. Sidebar berisi info kontak.

<img width="638" height="359" alt="Screenshot 2026-10-18 225122" src="https://github.com/user-attachments/assets/3935879c-81da-41fc-b87d-d31980ab637f" />
<img width="638" height="358" alt="Screenshot 2026-10-18 225130" src="https://github.com/user-attachments/assets/9748755d-7af5-4e69-9ddd-69ec0ad709c8" />

---

## Validasi
Seluruh dokumen HTML diperiksa melalui <http://validator.w3.org>.

<img width="1365" height="767" alt="WhatsApp Image 2026-10-18 at 22 52 08" src="https://github.com/user-attachments/assets/49abc7c5-c1f7-4ea8-bd72-d8136295a719" />
<img width="1364" height="767" alt="WhatsApp Image 2026-10-18 at 22 52 07" src="https://github.com/user-attachments/assets/733edcf2-8c2e-499e-a6c6-7f00504584f9" />

## Cara Menjalankan
1. Buka folder `Lab4Web` di VSCode.
2. Buka `lab4_box/lab4_box.html` atau `lab4_layout/home.html`, lalu jalankan dengan *Live Server* atau klik dua kali file tersebut.
3. Koneksi internet diperlukan untuk memuat Google Font dan gambar dari `dummyimage.com`.

## Kesimpulan
- Setiap elemen HTML adalah *box* (margin, border, padding, content).
- `float` memungkinkan elemen disusun berdampingan, sedangkan `clear` dan teknik clearfix mencegah elemen setelahnya ikut terpengaruh.
- Semantic element HTML5 (`header`, `nav`, `section`, `article`, `aside`, `footer`) membuat struktur halaman lebih jelas dan mudah dipahami.
