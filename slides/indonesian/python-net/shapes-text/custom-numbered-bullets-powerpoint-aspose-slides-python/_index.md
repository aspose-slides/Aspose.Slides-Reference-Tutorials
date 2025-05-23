---
"date": "2025-04-24"
"description": "Pelajari cara membuat daftar poin bernomor khusus di PowerPoint dengan Aspose.Slides untuk Python. Sempurnakan presentasi Anda dengan format yang unik."
"title": "Daftar Poin Bernomor Kustom di PowerPoint Menggunakan Aspose.Slides untuk Python"
"url": "/id/python-net/shapes-text/custom-numbered-bullets-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Daftar Poin Bernomor Kustom di PowerPoint menggunakan Aspose.Slides untuk Python

## Perkenalan
Apakah Anda ingin meningkatkan daya tarik visual presentasi PowerPoint Anda melampaui poin-poin standar? Baik untuk laporan perusahaan, kuliah akademis, atau rapat bisnis, daftar poin yang disesuaikan dapat menarik dan mempertahankan perhatian audiens Anda dengan lebih efektif. Dengan **Aspose.Slides untuk Python**, Anda memiliki fleksibilitas untuk menyesuaikan poin-poin bernomor menurut kebutuhan pemformatan unik Anda.

Dalam panduan lengkap ini, kami akan menunjukkan cara menyiapkan poin-poin bernomor khusus menggunakan Aspose.Slides di PowerPoint dengan Python. Dengan mengintegrasikan fitur ini ke dalam presentasi Anda, Anda dapat memperoleh tampilan yang profesional dan memukau.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan Aspose.Slides untuk Python
- Membuat daftar poin bernomor khusus
- Mengonfigurasi pengaturan peluru secara terprogram
- Mengoptimalkan kinerja dan memecahkan masalah umum

Mari kita mulai! Pastikan Anda telah menyiapkan segalanya untuk melanjutkan.

## Prasyarat
Sebelum menerapkan poin-poin bernomor khusus dengan Aspose.Slides untuk Python, pastikan Anda memiliki:

### Pustaka yang dibutuhkan:
- **Aspose.Slides untuk Python**: Pustaka yang tangguh untuk membuat dan memanipulasi presentasi PowerPoint.

### Pengaturan Lingkungan:
- Python 3.x terinstal di sistem Anda.
- Pemahaman dasar tentang konsep pemrograman Python sangat membantu namun tidak wajib.

## Menyiapkan Aspose.Slides untuk Python
Untuk memulai, instal `aspose.slides` perpustakaan menggunakan pip:

```bash
pip install aspose.slides
```

### Akuisisi Lisensi:
Aspose.Slides adalah produk komersial yang menawarkan uji coba gratis untuk menguji kemampuannya. Anda dapat memperoleh lisensi sementara atau membeli lisensi untuk penggunaan berkelanjutan.

- **Uji Coba Gratis**: Akses fungsionalitas dasar tanpa batasan.
- **Lisensi Sementara**: Permintaan pada situs web Aspose untuk mendapatkan akses penuh sementara.
- **Pembelian**Pertimbangkan untuk membeli lisensi untuk proyek jangka panjang.

### Inisialisasi Dasar:
Setelah terinstal, inisialisasi presentasi Anda sebagai berikut:

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Kode Anda di sini...
```

Pengaturan ini mempersiapkan lingkungan untuk menambahkan poin-poin bernomor khusus ke slide PowerPoint Anda.

## Panduan Implementasi
Mari kita mulai membuat daftar poin bernomor khusus. Setiap langkah dirinci agar lebih jelas dan mudah diterapkan.

### Menambahkan Bentuk Persegi Panjang dengan Bingkai Teks
#### Ringkasan:
Pertama, tambahkan bentuk yang akan berisi bingkai teks untuk poin-poin penting.

```python
# Tambahkan bentuk persegi panjang ke slide pertama
shape = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 200, 200, 400, 200)
```
- **Parameter Dijelaskan**: : Itu `add_auto_shape` metode mengambil parameter untuk jenis bentuk (persegi panjang), posisi (koordinat x dan y), dan dimensi (lebar dan tinggi).

### Mengonfigurasi Bingkai Teks
#### Ringkasan:
Akses bingkai teks persegi panjang untuk menambahkan poin-poin penting.

```python
# Akses bingkai teks dari bentuk otomatis yang dibuat
text_frame = shape.text_frame

# Hapus paragraf default yang ada jika ada
text_frame.paragraphs.clear()
```
- **Tujuan**: Memastikan keadaan bersih sebelum menambahkan poin-poin penting yang kustom.

### Menambahkan Poin Bernomor Kustom
#### Ringkasan:
Tambahkan paragraf dengan pengaturan poin tertentu:

```python
# Tambahkan paragraf dengan poin bernomor khusus
for start_number, bullet_text in [(2, "bullet 2"), (3, "bullet 3"), (7, "bullet 7")]:
    paragraph = slides.Paragraph()
    paragraph.text = bullet_text
    paragraph.paragraph_format.depth = 4
    paragraph.paragraph_format.bullet.numbered_bullet_start_with = start_number
    paragraph.paragraph_format.bullet.type = slides.BulletType.NUMBERED
    text_frame.paragraphs.add(paragraph)
```
- **Konfigurasi**: Setiap paragraf dimulai dengan nomor tertentu, menawarkan fleksibilitas dan kontrol atas format presentasi.

### Menyimpan Presentasi
Terakhir, simpan presentasi yang telah Anda konfigurasikan:

```python
# Simpan presentasi\presentation.save("DIREKTORI_KELUARAN_ANDA/text_set_custom_bullets_number_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}