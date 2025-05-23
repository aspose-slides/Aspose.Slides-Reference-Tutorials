---
"description": "Pelajari cara membuat Bagan Corong dalam presentasi PowerPoint dengan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber untuk visualisasi data yang efektif."
"linktitle": "Bagan Corong dalam Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Bagan Corong dalam Slide Java"
"url": "/id/java/chart-data-manipulation/funnel-chart-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Bagan Corong dalam Slide Java


## Pengantar Pembuatan Bagan Corong di Aspose.Slides untuk Java

Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan Bagan Corong dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Bagan corong berguna untuk memvisualisasikan data yang secara progresif menyempit atau "bercorong" melalui berbagai tahap atau kategori. Kami akan memberikan petunjuk langkah demi langkah beserta kode sumber untuk membantu Anda mencapainya.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

- Aspose.Slides untuk pustaka Java terinstal dan disiapkan dalam proyek Anda.
- Berkas presentasi PowerPoint (PPTX) tempat Anda ingin menyisipkan Bagan Corong.

## Langkah 1: Impor Aspose.Slides untuk Java

Pertama, Anda perlu mengimpor pustaka Aspose.Slides for Java ke dalam proyek Java Anda. Pastikan Anda telah menambahkan dependensi yang diperlukan ke konfigurasi build Anda.

```java
import com.aspose.slides.*;
```

## Langkah 2: Inisialisasi Presentasi dan Bagan

Pada langkah ini, kami menginisialisasi presentasi dan menambahkan Bagan Corong ke slide.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    // Tambahkan Bagan Corong ke slide pertama pada koordinat (50, 50) dengan dimensi (500, 400).
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Langkah 3: Tentukan Data Bagan

Selanjutnya, kami mendefinisikan data untuk Bagan Corong kami. Anda dapat menyesuaikan kategori dan titik data sesuai dengan kebutuhan Anda.

```java
// Hapus data bagan yang ada.
wb.clear(0);

// Tentukan kategori untuk bagan.
chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));

// Tambahkan titik data untuk seri Bagan Corong.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## Langkah 4: Simpan Presentasi

Terakhir, kami menyimpan presentasi dengan Funnel Chart ke file yang ditentukan.

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

Selesai! Anda telah berhasil membuat Bagan Corong menggunakan Aspose.Slides untuk Java dan memasukkannya ke dalam presentasi PowerPoint.

## Source Code Lengkap Untuk Funnel Chart di Java Slides

```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
            pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Kesimpulan

Dalam panduan langkah demi langkah ini, kami telah menunjukkan cara membuat Bagan Corong dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Bagan corong merupakan alat yang berharga untuk memvisualisasikan data yang mengikuti pola perkembangan atau penyempitan, sehingga memudahkan penyampaian informasi secara efektif. 

## Pertanyaan yang Sering Diajukan

### Bagaimana saya dapat menyesuaikan tampilan Bagan Corong?

Anda dapat menyesuaikan tampilan Bagan Corong dengan memodifikasi berbagai properti bagan seperti warna, label, dan gaya. Lihat dokumentasi Aspose.Slides untuk informasi terperinci tentang opsi penyesuaian bagan.

### Bisakah saya menambahkan lebih banyak titik data atau kategori ke Bagan Corong?

Ya, Anda dapat menambahkan titik data dan kategori tambahan ke Bagan Corong dengan memperluas kode yang diberikan pada Langkah 3. Cukup tambahkan lebih banyak label kategori dan titik data sesuai kebutuhan.

### Bagaimana cara mengubah posisi dan ukuran Bagan Corong pada slide?

Anda dapat menyesuaikan posisi dan ukuran Bagan Corong dengan mengubah koordinat dan dimensi yang diberikan saat menambahkan bagan ke slide pada Langkah 2. Perbarui nilai (50, 50, 500, 400) sebagaimana mestinya.

### Dapatkah saya mengekspor bagan ke format lain, seperti PDF atau gambar?

Ya, Aspose.Slides untuk Java memungkinkan Anda mengekspor presentasi dengan Bagan Corong ke berbagai format, termasuk PDF, format gambar, dan lainnya. Anda dapat menggunakan `SaveFormat` opsi untuk menentukan format keluaran yang diinginkan saat menyimpan presentasi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}