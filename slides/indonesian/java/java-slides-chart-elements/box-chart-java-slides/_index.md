---
title: Bagan Kotak di Slide Java
linktitle: Bagan Kotak di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat Bagan Kotak dalam presentasi Java dengan Aspose.Slides. Panduan langkah demi langkah dan kode sumber disertakan untuk visualisasi data yang efektif.
weight: 10
url: /id/java/chart-elements/box-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bagan Kotak di Slide Java


## Pengantar Bagan Kotak di Aspose.Slide untuk Java

Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan Bagan Kotak menggunakan Aspose.Slides untuk Java. Bagan kotak berguna untuk memvisualisasikan data statistik dengan berbagai kuartil dan outlier. Kami akan memberikan petunjuk langkah demi langkah beserta kode sumber untuk membantu Anda memulai.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Aspose.Slides untuk perpustakaan Java diinstal dan dikonfigurasi.
- Lingkungan pengembangan Java telah disiapkan.

## Langkah 1: Inisialisasi Presentasi

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Pada langkah ini, kita menginisialisasi objek presentasi menggunakan jalur ke file PowerPoint yang ada ("test.pptx" dalam contoh ini).

## Langkah 2: Buat Bagan Kotak

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Pada langkah ini, kita membuat bentuk Bagan Kotak pada slide pertama presentasi. Kami juga menghapus semua kategori dan rangkaian yang ada dari bagan.

## Langkah 3: Tentukan Kategori

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

 Pada langkah ini, kita menentukan kategori untuk Bagan Kotak. Kami menggunakan`IChartDataWorkbook` untuk menambahkan kategori dan memberi label yang sesuai.

## Langkah 4: Buat Seri

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Di sini, kita membuat rangkaian BoxAndWhisker untuk bagan dan mengonfigurasi berbagai opsi seperti metode kuartil, garis rata-rata, penanda rata-rata, titik dalam, dan titik outlier.

## Langkah 5: Tambahkan Poin Data

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

Pada langkah ini, kami menambahkan titik data ke seri BoxAndWhisker. Titik data ini mewakili data statistik untuk grafik.

## Langkah 6: Simpan Presentasi

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Terakhir, kami menyimpan presentasi dengan Box Chart ke file PowerPoint baru bernama "BoxAndWhisker.pptx."

Selamat! Anda telah berhasil membuat Bagan Kotak menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan bagan lebih lanjut dengan menyesuaikan berbagai properti dan menambahkan lebih banyak titik data sesuai kebutuhan.

## Kode Sumber Lengkap Untuk Bagan Kotak di Slide Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara membuat Bagan Kotak menggunakan Aspose.Slides untuk Java. Bagan Kotak adalah alat yang berharga untuk memvisualisasikan data statistik, termasuk kuartil dan outlier. Kami menyediakan panduan langkah demi langkah bersama dengan kode sumber untuk membantu Anda mulai membuat Bagan Kotak di aplikasi Java Anda.

## FAQ

### Bagaimana cara mengubah tampilan Bagan Kotak?

Anda dapat menyesuaikan tampilan Bagan Kotak dengan memodifikasi properti seperti gaya garis, warna, dan font. Lihat dokumentasi Aspose.Slides untuk Java untuk detail tentang penyesuaian bagan.

### Bisakah saya menambahkan rangkaian data tambahan ke Bagan Kotak?

 Ya, Anda dapat menambahkan beberapa seri data ke Bagan Kotak dengan membuat tambahan`IChartSeries` objek dan menambahkan titik data ke dalamnya.

### Apa yang dimaksud dengan QuartileMethodType.Exclusive?

 Itu`QuartileMethodType.Exclusive` pengaturan menetapkan bahwa penghitungan kuartil harus dilakukan menggunakan metode eksklusif. Anda dapat memilih metode penghitungan kuartil yang berbeda bergantung pada data dan kebutuhan Anda.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
