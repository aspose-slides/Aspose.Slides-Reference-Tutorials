---
title: Bagan Histogram di Slide Java
linktitle: Bagan Histogram di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat Bagan Histogram dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber untuk visualisasi data.
weight: 19
url: /id/java/chart-data-manipulation/histogram-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengenalan Bagan Histogram di Java Slides menggunakan Aspose.Slides

Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan Bagan Histogram dalam presentasi PowerPoint menggunakan Aspose.Slides for Java API. Bagan Histogram digunakan untuk mewakili distribusi data dalam interval kontinu.

## Prasyarat

 Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.Slides untuk Java. Anda dapat mengunduhnya dari[Asumsikan situs web](https://releases.aspose.com/slides/java/).

## Langkah 1: Inisialisasi Proyek Anda

Buat proyek Java dan sertakan pustaka Aspose.Slides dalam dependensi proyek Anda.

## Langkah 2: Impor Perpustakaan yang Diperlukan

```java
import com.aspose.slides.*;
```

## Langkah 3: Muat Presentasi yang Ada

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Pastikan untuk mengganti`"Your Document Directory"` dengan jalur sebenarnya ke dokumen PowerPoint Anda.

## Langkah 4: Buat Bagan Histogram

Sekarang, mari kita membuat Bagan Histogram pada slide presentasi.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Tambahkan titik data ke rangkaian
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Atur jenis agregasi sumbu horizontal ke Otomatis
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Simpan presentasi
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 Dalam kode ini, pertama-tama kita menghapus semua kategori dan rangkaian yang ada dari bagan. Kemudian, kita menambahkan titik data ke rangkaian tersebut menggunakan`getDataPoints().addDataPointForHistogramSeries` metode. Terakhir, kami mengatur jenis agregasi sumbu horizontal ke Otomatis dan menyimpan presentasi.

## Kode Sumber Lengkap Untuk Bagan Histogram di Slide Java

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

Dalam tutorial ini, kita telah menjelajahi cara membuat Bagan Histogram dalam presentasi PowerPoint menggunakan Aspose.Slides for Java API. Bagan Histogram adalah alat yang berharga untuk memvisualisasikan distribusi data dalam interval yang berkesinambungan, dan dapat menjadi tambahan yang berguna untuk presentasi Anda, terutama ketika berhubungan dengan konten statistik atau analitis.

## FAQ

### Bagaimana cara menginstal Aspose.Slides untuk Java?

 Anda dapat mengunduh perpustakaan Aspose.Slides untuk Java dari[Di Sini](https://releases.aspose.com/slides/java/). Ikuti petunjuk instalasi yang disediakan di situs web mereka.

### Untuk apa Bagan Histogram digunakan?

Bagan Histogram digunakan untuk memvisualisasikan distribusi data dalam interval berkelanjutan. Ini biasanya digunakan dalam statistik untuk mewakili distribusi frekuensi.

### Bisakah saya menyesuaikan tampilan Bagan Histogram?

Ya, Anda dapat menyesuaikan tampilan bagan, termasuk warna, label, dan sumbunya, menggunakan Aspose.Slides API.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
