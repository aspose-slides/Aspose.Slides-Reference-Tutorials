---
"date": "2025-04-22"
"description": "Pelajari cara membuat dan menyesuaikan diagram Pie of Pie dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Python, untuk meningkatkan keterampilan visualisasi data Anda."
"title": "Cara Membuat Diagram Lingkaran di PowerPoint Menggunakan Aspose.Slides untuk Python"
"url": "/id/python-net/charts-graphs/aspose-slides-python-pie-of-pie-chart-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Diagram Lingkaran di PowerPoint Menggunakan Aspose.Slides untuk Python

Membuat bagan yang menarik secara visual seperti bagan Pie of Pie dapat meningkatkan presentasi PowerPoint Anda secara signifikan dengan membuat informasi yang kompleks lebih mudah dicerna. Tutorial ini memandu Anda membuat bagan Pie of Pie menggunakan Aspose.Slides untuk Python.

## Apa yang Akan Anda Pelajari

- Menyiapkan Aspose.Slides untuk Python
- Langkah-langkah untuk membuat presentasi PowerPoint dengan diagram Pie of Pie
- Mengonfigurasi label data dan opsi grup seri untuk keterbacaan yang lebih baik
- Aplikasi praktis diagram Pie dalam presentasi

Mari mulai menyiapkan lingkungan Anda dan menerapkan fitur-fitur ini.

### Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- **Python Terpasang**: Python 3.6 atau yang lebih tinggi direkomendasikan.
- **Aspose.Slides untuk Python**: Instal menggunakan pip:
  ```bash
  pip install aspose.slides
  ```
- **Lisensi**: Dapatkan lisensi uji coba gratis dari Aspose untuk menjelajahi fitur lengkap tanpa batasan.

#### Prasyarat Pengetahuan

Pemahaman dasar tentang pemrograman Python dan presentasi PowerPoint akan sangat bermanfaat. Jika Anda baru dalam hal ini, pertimbangkan untuk mempelajari sumber daya pengantar terlebih dahulu.

### Menyiapkan Aspose.Slides untuk Python

Untuk memulai Aspose.Slides untuk Python, ikuti langkah-langkah sederhana berikut:

1. **Instalasi**: Gunakan pip untuk menginstal pustaka:
   ```bash
   pip install aspose.slides
   ```

2. **Akuisisi Lisensi**: 
   - Mengunjungi [Halaman Pembelian Aspose](https://purchase.aspose.com/buy) untuk membeli lisensi atau mendapatkan uji coba gratis sementara.
   - Terapkan lisensi Anda menggunakan potongan kode berikut di proyek Anda:
     ```python
     import aspose.slides as slides

     # Muat file lisensi
     license = slides.License()
     license.set_license("path_to_your_license.lic")
     ```

3. **Inisialisasi Dasar**:
   Mulailah dengan mengimpor Aspose.Slides dan memulai objek presentasi.

### Panduan Implementasi

#### Fitur 1: Buat Presentasi dengan Bagan

Fitur ini akan menunjukkan cara membuat presentasi PowerPoint dan menambahkan diagram Pie of Pie ke slide pertama.

##### Menambahkan Bagan

Mulailah dengan membuat presentasi baru dan menambahkan diagram Pie of Pie pada posisi (50, 50) pada slide pertama:

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Tambahkan diagram 'Pie of Pie' dengan dimensi yang ditentukan
    chart = presentation.slides[0].shapes.add_chart(
        slides.charts.ChartType.PIE_OF_PIE, 50, 50, 500, 400)
```

##### Mengonfigurasi Label Data

Untuk meningkatkan keterbacaan, konfigurasikan label data untuk menampilkan nilai:

```python
# Aktifkan tampilan nilai dalam label data untuk kejelasan yang lebih baik
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```

##### Pengaturan Opsi Pie of Pie

Konfigurasikan properti tertentu untuk bagan Pie of Pie, seperti ukuran pai kedua dan posisi split:

```python
# Tetapkan ukuran pai kedua dan properti pemisahan
chart.chart_data.series[0].parent_series_group.second_pie_size = 149
chart.chart_data.series[0].parent_series_group.pie_split_by = slides.charts.PieSplitType.BY_PERCENTAGE
chart.chart_data.series[0].parent_series_group.pie_split_position = 53
```

##### Menyimpan Presentasi

Terakhir, simpan presentasi Anda ke direktori yang diinginkan:

```python
# Simpan presentasi dengan bagan
presentation.save("YOUR_OUTPUT_DIRECTORY/charts_second_plot_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### Aplikasi Praktis

Bagan Pai bersifat serbaguna dan dapat digunakan dalam berbagai skenario:

1. **Laporan Bisnis**: Visualisasikan distribusi data di berbagai departemen atau produk.
2. **Proyek Akademik**: Menyajikan hasil survei yang menunjukkan tema-tema utama di samping temuan-temuan yang kurang signifikan.
3. **Analisis Keuangan**Bandingkan biaya utama dengan biaya sekunder dalam laporan anggaran.

### Pertimbangan Kinerja

Untuk kinerja optimal saat menggunakan Aspose.Slides:

- Minimalkan jumlah slide dan bagan jika memungkinkan untuk mengurangi penggunaan memori.
- Bersihkan sumber daya atau referensi yang tidak digunakan dalam kode Anda secara teratur.
- Gunakan pengumpulan sampah bawaan Python (`gc` modul) untuk mengelola memori secara efektif.

### Kesimpulan

Anda telah mempelajari cara membuat presentasi PowerPoint dengan diagram Pie of Pie menggunakan Aspose.Slides untuk Python. Keterampilan ini dapat meningkatkan daya tarik visual dan efektivitas presentasi Anda. Pertimbangkan untuk menjelajahi lebih banyak fitur di Aspose.Slides, seperti menambahkan animasi atau mengintegrasikan elemen multimedia.

### Langkah Berikutnya

- Bereksperimenlah dengan berbagai jenis bagan yang tersedia di Aspose.Slides.
- Integrasikan fitur ini ke dalam alur kerja otomatisasi presentasi yang lebih besar.

### Bagian FAQ

**T: Dapatkah saya menyesuaikan warna diagram Pie of Pie?**
A: Ya, Anda dapat menyesuaikan warna grafik menggunakan `fill_format` properti untuk setiap segmen.

**T: Bagaimana cara menangani kumpulan data besar dengan Aspose.Slides?**
A: Optimalkan masukan data Anda dan pertimbangkan untuk membaginya menjadi potongan-potongan yang lebih kecil untuk menjaga kinerja.

**T: Apakah ada cara untuk mengotomatiskan penambahan beberapa grafik sekaligus?**
A: Ya, ulangi set data Anda dan gunakan `add_chart` metode dalam konteks presentasi tunggal.

### Sumber daya

- **Dokumentasi**:Jelajahi panduan terperinci di [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/python-net/).
- **Unduh**:Dapatkan versi terbaru dari [Rilis](https://releases.aspose.com/slides/python-net/).
- **Pembelian dan Uji Coba Gratis**:Akses opsi lisensi di [Aspose Pembelian](https://purchase.aspose.com/buy) atau coba [Uji Coba Gratis](https://releases.aspose.com/slides/python-net/).
- **Mendukung**: Bergabunglah dalam diskusi di [Forum Aspose](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}