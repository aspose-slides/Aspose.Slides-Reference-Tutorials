---
"description": "Pelajari cara membuat Bagan Histogram dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber untuk visualisasi data."
"linktitle": "Grafik Histogram dalam Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Grafik Histogram dalam Slide Java"
"url": "/id/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafik Histogram dalam Slide Java


## Pengenalan Grafik Histogram di Java Slides menggunakan Aspose.Slides

Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan Bagan Histogram dalam presentasi PowerPoint menggunakan API Aspose.Slides for Java. Bagan Histogram digunakan untuk merepresentasikan distribusi data pada interval berkelanjutan.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.Slides for Java. Anda dapat mengunduhnya dari [Situs web Aspose](https://releases.aspose.com/slides/java/).

## Langkah 1: Inisialisasi Proyek Anda

Buat proyek Java dan sertakan pustaka Aspose.Slides dalam dependensi proyek Anda.

## Langkah 2: Impor Pustaka yang Diperlukan

```java
import com.aspose.slides.*;
```

## Langkah 3: Muat Presentasi yang Ada

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Pastikan untuk mengganti `"Your Document Directory"` dengan jalur sebenarnya ke dokumen PowerPoint Anda.

## Langkah 4: Buat Bagan Histogram

Sekarang, mari membuat Bagan Histogram pada slide presentasi.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Tambahkan titik data ke seri
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Tetapkan jenis agregasi sumbu horizontal ke Otomatis
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Simpan presentasi
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Dalam kode ini, pertama-tama kita menghapus kategori dan seri yang ada dari bagan. Kemudian, kita menambahkan titik data ke seri menggunakan `getDataPoints().addDataPointForHistogramSeries` metode. Terakhir, kami tetapkan jenis agregasi sumbu horizontal ke Otomatis dan simpan presentasinya.

## Source Code Lengkap Untuk Histogram Chart di Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kami telah mempelajari cara membuat Bagan Histogram dalam presentasi PowerPoint menggunakan API Aspose.Slides for Java. Bagan Histogram merupakan alat yang berharga untuk memvisualisasikan distribusi data dalam interval berkelanjutan, dan dapat menjadi tambahan yang hebat untuk presentasi Anda, terutama saat menangani konten statistik atau analitis.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menginstal Aspose.Slides untuk Java?

Anda dapat mengunduh pustaka Aspose.Slides untuk Java dari [Di Sini](https://releases.aspose.com/slides/java/)Ikuti petunjuk instalasi yang tersedia di situs web mereka.

### Apa kegunaan grafik Histogram?

Bagan Histogram digunakan untuk memvisualisasikan distribusi data pada interval kontinu. Bagan ini umumnya digunakan dalam statistik untuk menggambarkan distribusi frekuensi.

### Bisakah saya menyesuaikan tampilan Bagan Histogram?

Ya, Anda dapat menyesuaikan tampilan bagan, termasuk warna, label, dan sumbu, menggunakan API Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}