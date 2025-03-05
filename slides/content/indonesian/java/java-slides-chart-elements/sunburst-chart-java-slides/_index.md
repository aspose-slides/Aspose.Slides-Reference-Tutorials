---
title: Bagan Sunburst di Slide Java
linktitle: Bagan Sunburst di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Buat Bagan Sunburst yang Menakjubkan di Slide Java dengan Aspose.Slides. Pelajari Pembuatan Bagan Langkah demi Langkah dan Manipulasi Data.
type: docs
weight: 16
url: /id/java/chart-elements/sunburst-chart-java-slides/
---

## Pengantar Sunburst Chart di Java Slides dengan Aspose.Slides

Dalam tutorial ini, Anda akan mempelajari cara membuat bagan Sunburst dalam presentasi PowerPoint menggunakan Aspose.Slides for Java API. Bagan Sunburst adalah bagan radial yang digunakan untuk mewakili data hierarki. Kami akan memberikan petunjuk langkah demi langkah beserta kode sumbernya.

## Prasyarat

 Sebelum memulai, pastikan Anda telah menginstal dan mengonfigurasi pustaka Aspose.Slides for Java di proyek Java Anda. Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Impor Perpustakaan yang Diperlukan

Pertama, impor pustaka yang diperlukan untuk bekerja dengan Aspose.Slides dan buat bagan Sunburst di aplikasi Java Anda.

```java
import com.aspose.slides.*;
```

## Langkah 2: Inisialisasi Presentasi

Inisialisasi presentasi PowerPoint dan tentukan direktori tempat file presentasi Anda akan disimpan.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Langkah 3: Buat Bagan Sunburst

Buat grafik Sunburst pada slide. Kami menentukan posisi (X, Y) dan dimensi (lebar, tinggi) grafik.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Langkah 4: Siapkan Data Bagan

Hapus semua kategori dan data seri yang ada dari bagan, dan buat buku kerja data untuk bagan.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Langkah 5: Tentukan Hierarki Bagan

Tentukan struktur hierarki bagan Sunburst. Anda dapat menambahkan cabang, batang, dan daun sebagai kategori.

```java
// Cabang 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Cabang 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Langkah 6: Tambahkan Data ke Bagan

Tambahkan titik data ke rangkaian bagan Sunburst.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Langkah 7: Simpan Presentasi

Terakhir, simpan presentasi dengan grafik Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Kode Sumber Lengkap Untuk Sunburst Chart di Slide Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//cabang 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//cabang 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara membuat bagan Sunburst dalam presentasi PowerPoint menggunakan Aspose.Slides for Java API. Anda telah melihat cara menginisialisasi presentasi, membuat bagan, menentukan hierarki bagan, menambahkan titik data, dan menyimpan presentasi. Anda sekarang dapat menggunakan pengetahuan ini untuk membuat grafik Sunburst yang interaktif dan informatif di aplikasi Java Anda.

## FAQ

### Bagaimana cara menyesuaikan tampilan grafik Sunburst?

Anda dapat menyesuaikan tampilan bagan Sunburst dengan memodifikasi properti seperti warna, label, dan gaya. Lihat dokumentasi Aspose.Slides untuk opsi penyesuaian terperinci.

### Bisakah saya menambahkan lebih banyak titik data ke bagan?

 Ya, Anda dapat menambahkan lebih banyak titik data ke bagan dengan menggunakan`series.getDataPoints().addDataPointForSunburstSeries()` metode untuk setiap titik data yang ingin Anda sertakan.

### Bagaimana cara menambahkan keterangan alat ke bagan Sunburst?

Untuk menambahkan keterangan alat ke bagan Sunburst, Anda bisa mengatur format label data untuk menampilkan informasi tambahan, seperti nilai atau deskripsi, saat mengarahkan kursor ke segmen bagan.

### Apakah mungkin membuat grafik Sunburst interaktif dengan hyperlink?

Ya, Anda dapat membuat bagan Sunburst interaktif dengan hyperlink dengan menambahkan hyperlink ke elemen atau segmen bagan tertentu. Lihat dokumentasi Aspose.Slides untuk detail tentang penambahan hyperlink.