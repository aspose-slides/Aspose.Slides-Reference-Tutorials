---
"date": "2025-04-22"
"description": "Pelajari cara mudah menampilkan label persentase pada bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Python. Sempurna untuk meningkatkan visualisasi data."
"title": "Cara Menampilkan Label Persentase pada Grafik Menggunakan Aspose.Slides untuk Python&#58; Panduan Lengkap"
"url": "/id/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menampilkan Label Persentase pada Grafik Menggunakan Aspose.Slides untuk Python

## Perkenalan

Memvisualisasikan data secara efektif sangat penting dalam presentasi dan laporan, terutama saat Anda ingin menyorot proporsi atau distribusi dengan jelas. Namun, bagaimana jika Anda ingin persentase tersebut ditampilkan langsung pada diagram Anda? Panduan lengkap ini akan memandu Anda menggunakan **Aspose.Slides untuk Python** untuk menampilkan nilai persentase sebagai label pada bagan dengan mudah.

### Apa yang Akan Anda Pelajari:
- Cara membuat dan menyematkan bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Python.
- Menampilkan titik data sebagai label persentase pada bagan Anda.
- Menyimpan dan mengelola presentasi PowerPoint secara efisien.

Siap untuk mulai menambahkan visual yang mendalam ke data Anda? Mari kita lihat dulu apa yang Anda butuhkan sebelum menyelami kodenya!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:
- **Aspose.Slides untuk Python**:Pustaka ini penting untuk membuat dan memanipulasi presentasi PowerPoint secara terprogram.
- **Lingkungan Python**: Pemahaman dasar tentang pemrograman Python dan pengaturan lingkungan.
- **Manajer Paket PIP**: Digunakan untuk menginstal Aspose.Slides.

## Menyiapkan Aspose.Slides untuk Python

Untuk mulai menggunakan Aspose.Slides, Anda harus menginstalnya terlebih dahulu:

```bash
pip install aspose.slides
```

### Langkah-langkah Memperoleh Lisensi:
Anda dapat memulai dengan uji coba gratis atau memperoleh lisensi sementara untuk menjelajahi kemampuan penuh Aspose.Slides. Untuk penggunaan lebih lama, pertimbangkan untuk membeli langganan.

#### Inisialisasi dan Pengaturan Dasar

Setelah terinstal, Anda akan menginisialisasi lingkungan presentasi Anda seperti ini:

```python
import aspose.slides as slides

# Inisialisasi objek Presentasi
def create_presentation():
    with slides.Presentation() as presentation:
        # Kode Anda di sini
```

## Panduan Implementasi

Sekarang setelah semua siap, mari kita mulai menampilkan persentase pada grafik.

### Membuat Bagan dan Menambahkan Data

#### Ringkasan
Kita akan membuat bagan kolom bertumpuk dengan label persentase untuk setiap titik data, yang memungkinkan pemirsa melihat proporsi yang tepat secara sekilas.

##### Langkah 1: Tambahkan Bagan ke Slide Anda

```python
# Akses slide pertama dalam presentasi Anda
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Tambahkan bagan kolom bertumpuk
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Potongan kode ini menambahkan bagan dasar ke slide pertama. `add_chart` metode menentukan jenis bagan dan posisi serta ukurannya.

##### Langkah 2: Hitung Nilai Total untuk Kategori

```python
def calculate_totals(chart):
    total_for_category = []
    # Jumlahkan nilai di semua seri untuk setiap kategori
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Lingkaran ini menghitung total semua titik data di seluruh seri, yang krusial untuk kalkulasi persentase.

#### Mengatur Label Persentase

##### Langkah 3: Konfigurasikan Titik Data Seri

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Tetapkan opsi label default untuk menyembunyikan info yang tidak penting
        series.labels.default_data_label_format.show_legend_key = False
        
        # Hitung dan atur label persentase
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Buat bagian teks dengan nilai persentase
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Hapus label yang ada dan tambahkan label persentase baru
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Sembunyikan elemen label data lainnya
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Segmen ini memproses setiap titik data untuk menghitung persentasenya terhadap total dan menetapkannya sebagai label.

### Menyimpan Presentasi Anda

```python
def save_presentation(presentation, output_directory):
    # Simpan presentasi Anda dengan modifikasi
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}