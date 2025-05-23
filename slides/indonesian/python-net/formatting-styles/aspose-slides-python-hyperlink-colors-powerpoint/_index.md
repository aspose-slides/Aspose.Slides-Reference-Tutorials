---
"date": "2025-04-23"
"description": "Pelajari cara menyesuaikan warna hyperlink dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Python. Sempurnakan slide Anda dengan gaya tautan yang dipersonalisasi secara efisien."
"title": "Cara Mengatur Warna Hyperlink di PowerPoint Menggunakan Aspose.Slides untuk Python"
"url": "/id/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Mengatur Warna Hyperlink di PowerPoint Menggunakan Aspose.Slides untuk Python

## Perkenalan

Meningkatkan daya tarik visual presentasi PowerPoint Anda dengan menyesuaikan warna hyperlink mudah dilakukan dengan Aspose.Slides untuk Python. Panduan ini akan memandu Anda mengatur hyperlink dengan warna tertentu di slide Anda menggunakan Python.

**Apa yang Akan Anda Pelajari:**
- Cara mengatur warna hyperlink dalam bentuk teks di PowerPoint.
- Langkah-langkah yang terlibat dalam membuat presentasi yang menarik secara visual.
- Fitur utama Aspose.Slides untuk Python yang memfasilitasi penyesuaian ini.

Mari kita bahas prasyarat yang diperlukan sebelum memulai.

## Prasyarat

Sebelum memulai, pastikan lingkungan Anda siap dengan hal berikut:
- **Perpustakaan dan Versi:** Memasang `aspose.slides` pustaka. Pastikan Python telah terinstal di komputer Anda.
- **Persyaratan Pengaturan Lingkungan:** Tutorial ini mengasumsikan pengaturan dasar Python di Windows, Mac, atau Linux.
- **Prasyarat Pengetahuan:** Kemampuan dalam pemrograman Python akan bermanfaat.

## Menyiapkan Aspose.Slides untuk Python

Untuk mulai menggunakan Aspose.Slides untuk Python, instal paket melalui pip:

```bash
pip install aspose.slides
```

**Langkah-langkah Memperoleh Lisensi:**
- **Uji Coba Gratis:** Unduh versi uji coba dari [Halaman rilis Aspose](https://releases.aspose.com/slides/python-net/).
- **Lisensi Sementara:** Minta lisensi sementara di [halaman pembelian](https://purchase.aspose.com/temporary-license/) untuk akses lebih luas.
- **Pembelian:** Untuk membuka fitur sepenuhnya tanpa batasan, pertimbangkan untuk membeli lisensi dari [Halaman pembelian Aspose](https://purchase.aspose.com/buy).

**Inisialisasi Dasar:**
Setelah terinstal dan dilisensikan, impor Aspose.Slides dalam skrip Anda:

```python
import aspose.slides as slides
```

## Panduan Implementasi

Bagian ini memandu Anda dalam menetapkan warna hyperlink dalam presentasi PowerPoint.

### Atur Fitur Warna Hyperlink

#### Ringkasan

Sesuaikan warna hyperlink yang disematkan dalam bentuk teks menggunakan Aspose.Slides untuk Python. Ini meningkatkan keterbacaan dan daya tarik visual.

##### Langkah 1: Buat Presentasi Baru

Buat contoh presentasi:

```python
with slides.Presentation() as presentation:
    # Kode Anda di sini
```

##### Langkah 2: Tambahkan Bentuk dengan Teks

Tambahkan bentuk persegi panjang ke slide pertama dan sisipkan teks yang menyertakan hyperlink.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### Langkah 3: Tetapkan Properti Hyperlink

Tetapkan hyperlink dan atur warnanya. `hyperlink_click` Properti menentukan ke mana tautan harus menavigasi saat diklik.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# Tetapkan sumber warna untuk hyperlink ke format bagian dan tentukan jenis dan warna isian.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### Langkah 4: Simpan Presentasi

Simpan presentasi Anda ke direktori yang ditentukan:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}