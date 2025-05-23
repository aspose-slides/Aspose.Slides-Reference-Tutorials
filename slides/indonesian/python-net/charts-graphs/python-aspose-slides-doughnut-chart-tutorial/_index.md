---
"date": "2025-04-22"
"description": "Pelajari cara membuat diagram donat dengan Python dan Aspose.Slides. Panduan langkah demi langkah ini mencakup penyiapan, penyesuaian, dan praktik terbaik untuk menyempurnakan presentasi Anda."
"title": "Cara Membuat Diagram Donat di Python Menggunakan Aspose.Slides&#58; Panduan Langkah demi Langkah"
"url": "/id/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Diagram Donat di Python Menggunakan Aspose.Slides: Panduan Langkah demi Langkah

Dalam bidang visualisasi data, penyajian informasi yang efektif dapat berdampak signifikan pada pemahaman dan pengambilan keputusan. Baik Anda sedang menyusun presentasi bisnis atau menganalisis kumpulan data yang kompleks, bagan merupakan alat yang penting. Di antara berbagai jenis bagan, bagan donat menyediakan cara yang menarik untuk merepresentasikan data proporsional dengan lubang tengah yang intuitif. Panduan langkah demi langkah ini akan memandu Anda membuat bagan donat dalam Python menggunakan Aspose.Slides—pustaka yang hebat untuk memanipulasi presentasi.

## Apa yang Akan Anda Pelajari
- Cara mengatur dan menggunakan Aspose.Slides untuk Python
- Proses menambahkan diagram donat ke slide presentasi Anda
- Menyesuaikan seri dan kategori dalam bagan
- Menyesuaikan elemen visual seperti label, warna, dan efek ledakan
- Praktik terbaik untuk mengoptimalkan kinerja dengan Aspose.Slides

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:
- **Lingkungan Python**: Python 3.x terinstal di komputer Anda.
- **Aspose.Slides untuk Python**: Instal pustaka ini menggunakan pip.
- **Pemahaman Dasar Pemrograman Python**:Keakraban dengan loop dan pemrograman berorientasi objek akan sangat membantu.

## Menyiapkan Aspose.Slides untuk Python
Untuk memulai, instal pustaka Aspose.Slides melalui pip:

```bash
pip install aspose.slides
```

### Akuisisi Lisensi
Aspose menawarkan uji coba gratis untuk menguji fitur tanpa batasan selama waktu terbatas. Untuk mendapatkannya:
1. Kunjungi [Uji Coba Gratis](https://releases.aspose.com/slides/python-net/) halaman.
2. Ikuti petunjuk untuk mengunduh dan menerapkan lisensi sementara Anda.

Untuk penggunaan berkelanjutan, pertimbangkan untuk membeli langganan dari [Halaman Pembelian](https://purchase.aspose.com/buy).

### Inisialisasi Dasar
Setelah menyiapkan Aspose.Slides, inisialisasikan sebagai berikut:

```python
import aspose.slides as slides

# Buat contoh kelas Presentasi.
with slides.Presentation() as pres:
    # Kode Anda untuk memanipulasi presentasi ada di sini.

# Simpan presentasi setelah membuat perubahan.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Panduan Implementasi
Setelah Aspose.Slides disiapkan, ikuti langkah-langkah ini untuk menambahkan bagan donat ke slide presentasi Anda per slide.

### Membuat Presentasi Baru dan Menambahkan Slide
Mulailah dengan membuat contoh `Presentation` kelas:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Akses atau buat slide dalam konteks ini.
```

### Menambahkan Bagan Donat ke Slide Pertama
Akses slide pertama dan gunakan `add_chart` metode. Tentukan jenis grafik sebagai `DOUGHNUT`, beserta posisi dan ukurannya:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Mengonfigurasi Data Bagan
Hapus data yang ada dan konfigurasikan pengaturan seperti menyembunyikan legenda:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Menambahkan Seri dan Kategori
Tambahkan beberapa seri dan kategori untuk diagram donat. Berikut cara membuat 15 seri dengan properti tertentu:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

Tambahkan kategori dengan cara yang sama:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Tambahkan titik data untuk setiap seri.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Sesuaikan tampilan setiap titik data.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Konfigurasikan pengaturan label untuk seri terakhir.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### Menyimpan Presentasi
Terakhir, simpan presentasi Anda ke direktori yang ditentukan:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Aplikasi Praktis
Bagan donat bersifat serbaguna dan dapat digunakan dalam berbagai skenario seperti:
1. **Alokasi Anggaran**: Menampilkan bagaimana berbagai departemen menggunakan dana yang dialokasikan.
2. **Analisis Pangsa Pasar**: Membandingkan pangsa pasar produk atau perusahaan pesaing.
3. **Hasil Survei**: Memvisualisasikan respons terhadap pertanyaan survei tentang preferensi atau tingkat kepuasan.

## Pertimbangan Kinerja
Untuk memastikan kinerja optimal saat menggunakan Aspose.Slides:
- Minimalkan penggunaan memori dengan membuang objek dengan benar setelah digunakan.
- Muat presentasi ke memori hanya bila diperlukan, dan tutup sesegera mungkin.
- Pertimbangkan pemrosesan slide secara batch jika Anda bekerja dengan sejumlah besar diagram.

## Kesimpulan
Dengan mengikuti panduan ini, Anda telah mempelajari cara membuat bagan donat dinamis menggunakan Aspose.Slides untuk Python. Visualisasi ini dapat menyempurnakan presentasi Anda dengan membuat data lebih mudah dicerna dan menarik. Terus jelajahi fitur-fitur pustaka untuk menyesuaikan dan mengoptimalkan bagan Anda lebih lanjut.

## Bagian FAQ
1. **Bisakah saya menggunakan Aspose.Slides tanpa membeli lisensi?**
   - Ya, Anda dapat memulai dengan lisensi uji coba gratis untuk tujuan evaluasi.
2. **Bagaimana cara mengubah warna bagan di Aspose.Slides?**
   - Gunakan `fill_format` properti untuk mengatur warna yang diinginkan untuk elemen bagan Anda.
3. **Apakah mungkin untuk mengekspor grafik sebagai gambar?**
   - Ya, Anda dapat menyajikan slide yang berisi grafik ke dalam format gambar dengan menggunakan kemampuan penyajian yang disediakan perpustakaan.
4. **Apa saja masalah umum saat menambahkan grafik?**
   - Pastikan semua titik data dan kategori ditambahkan dengan benar sebelum mencoba menyimpan atau menampilkan bagan Anda.
5. **Dapatkah saya mengintegrasikan Aspose.Slides dengan pustaka Python lainnya?**
   - Tentu saja! Anda dapat menggunakannya bersama pustaka seperti Pandas untuk meningkatkan kemampuan manipulasi data.

## Sumber daya
- [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Unduh Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [Beli Lisensi](https://purchase.aspose.com/buy)
- [Uji Coba Gratis dan Lisensi Sementara](https://releases.aspose.com/slides/python-net/)
- [Forum Komunitas Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}