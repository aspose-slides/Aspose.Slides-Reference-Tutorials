---
"description": "Pelajari cara menyesuaikan grafik di Java Slides menggunakan Aspose.Slides untuk Java. Jelajahi opsi grafik kedua dan tingkatkan presentasi Anda."
"linktitle": "Opsi Plot Kedua untuk Bagan di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Opsi Plot Kedua untuk Bagan di Slide Java"
"url": "/id/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Opsi Plot Kedua untuk Bagan di Slide Java


## Pengenalan Opsi Plot Kedua untuk Bagan di Slide Java

Dalam tutorial ini, kita akan menjelajahi cara menambahkan opsi plot kedua ke bagan menggunakan Aspose.Slides untuk Java. Opsi plot kedua memungkinkan Anda untuk menyesuaikan tampilan dan perilaku bagan, khususnya dalam skenario seperti bagan Pie. Kami akan memberikan petunjuk langkah demi langkah dan contoh kode sumber untuk mencapainya. 

## Prasyarat
Sebelum memulai, pastikan Anda telah menginstal dan mengatur Aspose.Slides untuk Java di proyek Java Anda.

## Langkah 1: Buat Presentasi
Mari kita mulai dengan membuat presentasi baru:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
```

## Langkah 2: Tambahkan Bagan ke Slide
Selanjutnya, kita akan menambahkan diagram ke slide. Dalam contoh ini, kita akan membuat diagram Pie of Pie:

```java
// Tambahkan bagan pada slide
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Langkah 3: Sesuaikan Properti Bagan
Sekarang, mari kita tetapkan properti yang berbeda untuk bagan tersebut, termasuk opsi plot kedua:

```java
// Tampilkan label data untuk seri pertama
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Mengatur ukuran pai kedua (dalam persentase)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Membagi kue berdasarkan persentase
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Mengatur posisi split
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Langkah 4: Simpan Presentasi
Terakhir, simpan presentasi dengan opsi bagan dan plot kedua:

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
// Tambahkan bagan pada slide
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

Dalam tutorial ini, kita telah mempelajari cara menambahkan opsi plot kedua ke bagan di Java Slides menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan berbagai properti untuk meningkatkan tampilan dan fungsionalitas bagan, membuat presentasi Anda lebih informatif dan menarik secara visual.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah ukuran pai kedua pada diagram Pie of Pie?

Untuk mengubah ukuran pai kedua dalam bagan Pai, gunakan `setSecondPieSize` metode seperti yang ditunjukkan pada contoh kode di atas. Sesuaikan nilai untuk menentukan ukuran dalam persentase.

### Apa itu `PieSplitBy` kontrol dalam diagram Pie of Pie?

Itu `PieSplitBy` properti mengontrol bagaimana diagram pai dibagi. Anda dapat mengaturnya ke `PieSplitType.ByPercentage` atau `PieSplitType.ByValue` untuk membagi grafik berdasarkan persentase atau nilai tertentu.

### Bagaimana cara mengatur posisi pemisahan pada diagram Pie of Pie?

Anda dapat mengatur posisi split pada diagram Pie of Pie menggunakan `setPieSplitPosition` metode. Sesuaikan nilai untuk menentukan posisi yang diinginkan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}