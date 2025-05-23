---
"date": "2025-04-22"
"description": "Pelajari cara menyesuaikan font bagan dalam presentasi PowerPoint menggunakan Aspose.Slides dengan Python. Ikuti panduan ini untuk langkah-langkah terperinci dan aplikasi praktis."
"title": "Cara Menyesuaikan Font Bagan di PowerPoint Menggunakan Aspose.Slides untuk Python"
"url": "/id/python-net/charts-graphs/customize-chart-fonts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menyesuaikan Font Bagan di PowerPoint Menggunakan Aspose.Slides untuk Python

## Perkenalan
Apakah Anda ingin meningkatkan daya tarik visual grafik Anda dalam presentasi PowerPoint menggunakan Python? Anda tidak sendirian! Banyak pengembang menghadapi tantangan saat mencoba menyesuaikan font grafik secara terprogram. Panduan ini akan memandu Anda mengatur properti font untuk grafik di PowerPoint menggunakan **Aspose.Slides untuk Python**Dengan menguasai teknik-teknik ini, Anda dapat membuat slide yang menarik secara visual dan tampak profesional dengan mudah.

Dalam tutorial ini, kita akan membahas:
- Menyiapkan Aspose.Slides untuk Python
- Menyesuaikan font grafik dengan mudah
- Aplikasi praktis untuk proyek Anda

Mari kita mulai dengan memastikan Anda telah menyiapkan semuanya!

### Prasyarat
Sebelum memulai, pastikan Anda telah memenuhi prasyarat berikut:
1. **Lingkungan Python**Pastikan Anda telah menginstal Python (versi 3.6 atau lebih tinggi).
2. **Aspose.Slides untuk Python**Anda memerlukan pustaka ini untuk memanipulasi berkas PowerPoint.
3. **Pengetahuan Dasar**:Keakraban dengan pemrograman Python dan pemahaman dasar tentang cara bekerja dengan pustaka akan sangat membantu.

## Menyiapkan Aspose.Slides untuk Python
Untuk memulai, Anda perlu menginstal `aspose.slides` perpustakaan menggunakan pip:

```bash
pip install aspose.slides
```

### Langkah-langkah Memperoleh Lisensi
- **Uji Coba Gratis**: Unduh uji coba gratis dari [Situs resmi Aspose](https://releases.aspose.com/slides/python-net/).
- **Lisensi Sementara**:Untuk pengujian yang lebih luas, dapatkan lisensi sementara melalui mereka [halaman pembelian](https://purchase.aspose.com/temporary-license/).
- **Pembelian**:Jika Anda merasa alat ini sangat berharga untuk kebutuhan Anda, pertimbangkan untuk membeli lisensi penuh dari [Situs pembelian Aspose](https://purchase.aspose.com/buy).

Setelah terinstal dan dilisensikan, inisialisasi Aspose.Slides dalam Python:

```python
import aspose.slides as slides

# Inisialisasi objek Presentasi\dengan slides.Presentation() sebagai pres:
    # Kode Anda ada di sini
```

## Panduan Implementasi
Di bagian ini, kita akan menjelajahi cara mengatur properti font grafik langkah demi langkah.

### Menambahkan Bagan Kolom Berkelompok
Pertama, mari tambahkan bagan kolom berkelompok ke presentasi kita:

```python
# Tambahkan bagan kolom berkelompok pada posisi dan ukuran yang ditentukan.
chart = pres.slides[0].shapes.add_chart(
    slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 500, 400
)
```
**Penjelasan**: Cuplikan ini menambahkan bagan baru ke slide pertama presentasi Anda. `add_chart` Metode ini mengharuskan Anda menentukan jenis bagan dan posisi serta ukurannya pada slide.

### Mengatur Properti Font
Berikutnya, mari kita atur tinggi font untuk teks dalam bagan kita:

```python
# Mengatur tinggi font untuk teks dalam bagan.
chart.text_format.portion_format.font_height = 20
```
**Penjelasan**: Baris ini menyesuaikan ukuran font semua bagian teks dalam bagan Anda. `font_height` properti ditentukan dalam poin, dan Anda dapat menyesuaikan nilai ini agar sesuai dengan kebutuhan desain Anda.

### Menampilkan Label Data
Untuk meningkatkan keterbacaan, kami akan menampilkan nilai pada label data:

```python
# Menampilkan nilai pada label data seri pertama.
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```
**Penjelasan**: Pengaturan ini memastikan bahwa setiap titik data dalam seri pertama menunjukkan nilainya. Hal ini sangat berguna untuk menyampaikan informasi yang akurat secara sekilas.

### Menyimpan Presentasi Anda
Terakhir, simpan presentasi Anda ke lokasi yang diinginkan:

```python
# Simpan presentasi ke direktori keluaran yang ditentukan.
pres.save(
    "YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_chart_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}