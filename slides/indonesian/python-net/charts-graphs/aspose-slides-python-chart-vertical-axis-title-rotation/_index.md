---
"date": "2025-04-23"
"description": "Pelajari cara menyesuaikan sudut rotasi judul bagan dalam presentasi menggunakan Aspose.Slides untuk Python, meningkatkan keterbacaan dan estetika."
"title": "Cara Mengatur Rotasi Judul Sumbu Vertikal Bagan di Aspose.Slides untuk Python"
"url": "/id/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Mengatur Rotasi Judul Sumbu Vertikal Bagan di Aspose.Slides untuk Python

## Perkenalan

Dalam presentasi data, meningkatkan keterbacaan bagan sangatlah penting. Menyesuaikan sudut rotasi judul sumbu vertikal bagan Anda menggunakan Aspose.Slides for Python dapat membuat judul pas dan menonjol di slide Anda. Tutorial ini memandu Anda dalam mengatur sudut rotasi ini untuk meningkatkan fungsionalitas dan daya tarik visual.

**Apa yang Akan Anda Pelajari:**
- Cara memasang dan mengonfigurasi Aspose.Slides untuk Python.
- Langkah-langkah untuk menambahkan dan menyesuaikan bagan dalam slide Anda.
- Teknik untuk mengatur sudut rotasi judul bagan.
- Aplikasi dunia nyata untuk fitur-fitur ini dalam visualisasi data.

Mari kita mulai dengan membahas prasyarat sebelum terjun ke implementasi.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:
- **Lingkungan Python**: Instal Python 3.x dari [python.org](https://www.python.org/).
- **Pustaka Aspose.Slides**: Instal melalui pip untuk memanipulasi presentasi secara efektif.
- **Pengetahuan Dasar Pemrograman Python**:Keakraban dengan sintaksis Python dan operasi file akan membantu Anda mengikutinya.

## Menyiapkan Aspose.Slides untuk Python

Untuk menggunakan Aspose.Slides, instal menggunakan pip. Buka terminal atau command prompt dan jalankan:

```bash
pip install aspose.slides
```

### Langkah-langkah Memperoleh Lisensi

Aspose menawarkan berbagai pilihan lisensi:
- **Uji Coba Gratis**: Unduh versi uji coba dari [Halaman rilis Aspose](https://releases.aspose.com/slides/python-net/).
- **Lisensi Sementara**: Dapatkan lisensi sementara untuk fitur yang diperluas melalui [portal pembelian](https://purchase.aspose.com/temporary-license/).
- **Pembelian**: Pertimbangkan untuk membeli jika Anda merasa alat ini sangat diperlukan, tersedia dari [Halaman pembelian Aspose](https://purchase.aspose.com/buy).

#### Inisialisasi dan Pengaturan Dasar

Berikut cara menginisialisasi Aspose.Slides dalam skrip Python Anda:

```python
import aspose.slides as slides

# Membuat objek presentasi
def main():
    with slides.Presentation() as pres:
        # Kode Anda akan berada di sini
        pass

if __name__ == "__main__":
    main()
```

## Panduan Implementasi

### Menambahkan dan Menyesuaikan Bagan

#### Ringkasan

Di bagian ini, kita akan menambahkan bagan kolom berkelompok ke slide Anda dan menyesuaikannya dengan mengatur sudut rotasi judul sumbu vertikal.

#### Tangga:

##### Langkah 1: Tambahkan Bagan Kolom Berkelompok

Mulailah dengan menambahkan bagan pada koordinat tertentu dengan dimensi yang ditentukan:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Tambahkan bagan kolom berkelompok ke slide 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Langkah 2: Konfigurasikan Judul Sumbu Vertikal

Aktifkan dan atur sudut rotasi untuk judul sumbu vertikal:

```python
def configure_chart(chart):
    # Aktifkan judul sumbu vertikal
    chart.axes.vertical_axis.has_title = True
    
    # Atur sudut rotasi menjadi 90 derajat
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Langkah 3: Simpan Presentasi Anda

Terakhir, simpan presentasi Anda dengan perubahan:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Simpan presentasi
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}