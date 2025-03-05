---
title: Atur Balikkan Bagan Warna Isi di Slide Java
linktitle: Atur Balikkan Bagan Warna Isi di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengatur warna isian terbalik untuk bagan Java Slides menggunakan Aspose.Slides. Sempurnakan visualisasi bagan Anda dengan panduan langkah demi langkah dan kode sumber ini.
type: docs
weight: 22
url: /id/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

## Pengantar Mengatur Bagan Warna Isi Balik di Slide Java

Dalam tutorial ini, kami akan mendemonstrasikan cara mengatur warna isian terbalik untuk bagan di Java Slides menggunakan Aspose.Slides untuk Java. Membalikkan warna isian adalah fitur yang berguna ketika Anda ingin menyorot nilai negatif dalam bagan dengan warna tertentu. Kami akan memberikan petunjuk langkah demi langkah dan kode sumber untuk mencapai hal ini.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Aspose.Slides untuk perpustakaan Java diinstal.
2. Lingkungan pengembangan Java disiapkan.

## Langkah 1: Buat Presentasi

Pertama, kita perlu membuat presentasi untuk menambahkan grafik kita. Anda dapat menggunakan kode berikut untuk membuat presentasi:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Bagan

Selanjutnya, kita akan menambahkan bagan kolom berkerumun ke presentasi. Inilah cara Anda melakukannya:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Langkah 3: Siapkan Data Bagan

Sekarang, mari siapkan data bagan, termasuk seri dan kategori:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Menambahkan seri dan kategori baru
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Langkah 4: Isi Data Seri

Sekarang, mari kita isi data seri untuk bagan:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Langkah 5: Atur Balikkan Warna Isi

Untuk mengatur warna isian terbalik pada rangkaian bagan, Anda dapat menggunakan kode berikut:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Dalam kode di atas, kita mengatur rangkaian untuk membalikkan warna isian untuk nilai negatif dan menentukan warna untuk isian terbalik.

## Langkah 6: Simpan Presentasi

Terakhir, simpan presentasi dengan bagan:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Kode Sumber Lengkap Untuk Mengatur Bagan Warna Isi Terbalik di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Menambahkan seri dan kategori baru
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Ambil rangkaian bagan pertama dan isi data seri.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kami telah menunjukkan kepada Anda cara mengatur warna isian terbalik untuk bagan di Java Slides menggunakan Aspose.Slides untuk Java. Fitur ini memungkinkan Anda menyorot nilai negatif dalam bagan dengan warna tertentu, sehingga menjadikan data Anda lebih informatif secara visual.

## FAQ

Di bagian ini, kami akan menjawab beberapa pertanyaan umum terkait pengaturan warna isian terbalik untuk bagan di Slide Java menggunakan Aspose.Slides untuk Java.

### Bagaimana cara menginstal Aspose.Slides untuk Java?

 Anda dapat menginstal Aspose.Slides untuk Java dengan menyertakan file JAR Aspose.Slides di proyek Java Anda. Anda dapat mengunduh perpustakaan dari[Aspose.Slide untuk halaman unduh Java](https://releases.aspose.com/slides/java/). Ikuti petunjuk instalasi yang disediakan dalam dokumentasi untuk lingkungan pengembangan spesifik Anda.

### Bisakah saya menyesuaikan warna untuk isian terbalik pada rangkaian bagan?

Ya, Anda dapat menyesuaikan warna untuk isian terbalik pada rangkaian bagan. Dalam contoh kode yang diberikan,`series.getInvertedSolidFillColor().setColor(Color.RED)` garis mengatur warna menjadi merah untuk isian terbalik. Anda bisa menggantinya`Color.RED` dengan warna lain pilihan Anda.

### Bagaimana cara mengubah tipe bagan di Aspose.Slides untuk Java?

 Anda dapat mengubah tipe bagan dengan mengubah`ChartType` parameter saat menambahkan bagan ke presentasi. Dalam contoh kode, kami menggunakan`ChartType.ClusteredColumn` . Anda dapat menjelajahi jenis diagram lain seperti diagram garis, diagram batang, diagram lingkaran, dll., dengan menentukan yang sesuai`ChartType` nilai enum.

### Bagaimana cara menambahkan beberapa seri data ke bagan?

 Untuk menambahkan beberapa seri data ke bagan, Anda dapat menggunakan`chart.getChartData().getSeries().add(...)` metode untuk setiap seri yang ingin Anda tambahkan. Pastikan untuk memberikan titik data dan label yang sesuai untuk setiap rangkaian untuk mengisi bagan Anda dengan beberapa rangkaian.

### Apakah ada cara untuk menyesuaikan aspek lain dari tampilan grafik?

Ya, Anda dapat menyesuaikan berbagai aspek tampilan bagan, termasuk label sumbu, judul, legenda, dan lainnya menggunakan Aspose.Slides untuk Java. Lihat dokumentasi untuk panduan mendetail tentang menyesuaikan elemen dan tampilan bagan.

### Bisakah saya menyimpan grafik dalam format berbeda?

 Ya, Anda dapat menyimpan grafik dalam format berbeda menggunakan Aspose.Slides untuk Java. Dalam contoh kode yang diberikan, kami menyimpan presentasi sebagai file PPTX. Anda dapat menggunakan yang berbeda`SaveFormat` opsi untuk menyimpannya dalam format lain seperti PDF, PNG, atau SVG, tergantung kebutuhan Anda.