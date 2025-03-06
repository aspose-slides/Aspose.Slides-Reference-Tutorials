---
title: Opsi Plot Kedua untuk Bagan di Slide Java
linktitle: Opsi Plot Kedua untuk Bagan di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menyesuaikan bagan di Java Slides menggunakan Aspose.Slides for Java. Jelajahi opsi plot kedua dan tingkatkan presentasi Anda.
weight: 12
url: /id/java/chart-creation/second-plot-options-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengantar Opsi Plot Kedua untuk Bagan di Slide Java

Dalam tutorial ini, kita akan mempelajari cara menambahkan opsi plot kedua ke bagan menggunakan Aspose.Slides untuk Java. Opsi plot kedua memungkinkan Anda menyesuaikan tampilan dan perilaku bagan, khususnya dalam skenario seperti bagan Pie of Pie. Kami akan memberikan petunjuk langkah demi langkah dan contoh kode sumber untuk mencapai hal ini. 

## Prasyarat
Sebelum kita mulai, pastikan Anda telah menginstal dan menyiapkan Aspose.Slides for Java di proyek Java Anda.

## Langkah 1: Buat Presentasi
Mari kita mulai dengan membuat presentasi baru:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
```

## Langkah 2: Tambahkan Bagan ke Slide
Selanjutnya, kita akan menambahkan grafik ke slide. Dalam contoh ini, kita akan membuat diagram Pie of Pie:

```java
// Tambahkan grafik pada slide
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Langkah 3: Sesuaikan Properti Bagan
Sekarang, mari atur properti berbeda untuk bagan, termasuk opsi plot kedua:

```java
// Tampilkan label data untuk seri pertama
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Atur ukuran pai kedua (dalam persentase)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Bagi pai berdasarkan persentase
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Atur posisi perpecahan
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Langkah 4: Simpan Presentasi
Terakhir, simpan presentasi dengan bagan dan opsi plot kedua:

```java
// Tulis presentasi ke disk
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Kode Sumber Lengkap Untuk Opsi Plot Kedua

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
// Tambahkan grafik pada slide
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Tetapkan properti yang berbeda
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Tulis presentasi ke disk
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara menambahkan opsi plot kedua ke bagan di Java Slides menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan berbagai properti untuk menyempurnakan tampilan dan fungsionalitas bagan Anda, menjadikan presentasi Anda lebih informatif dan menarik secara visual.

## FAQ

### Bagaimana cara mengubah ukuran pai kedua dalam diagram Pie of Pie?

Untuk mengubah ukuran pai kedua dalam diagram Pie of Pie, gunakan`setSecondPieSize` metode seperti yang ditunjukkan pada contoh kode di atas. Sesuaikan nilainya untuk menentukan ukuran dalam persentase.

###  Apa artinya?`PieSplitBy` control in a Pie of Pie chart?

 Itu`PieSplitBy` properti mengontrol bagaimana diagram lingkaran dibagi. Anda dapat mengaturnya menjadi keduanya`PieSplitType.ByPercentage` atau`PieSplitType.ByValue` untuk membagi grafik berdasarkan persentase atau nilai tertentu.

### Bagaimana cara mengatur posisi pemisahan pada diagram Pie of Pie?

 Anda dapat mengatur posisi pemisahan dalam diagram Pie of Pie menggunakan`setPieSplitPosition` metode. Sesuaikan nilainya untuk menentukan posisi yang diinginkan.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
