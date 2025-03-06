---
title: Atur Lebar Celah di Slide Java
linktitle: Atur Lebar Celah di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengatur Lebar Celah di Slide Java dengan Aspose.Slides untuk Java. Sempurnakan visual bagan untuk presentasi PowerPoint Anda.
weight: 21
url: /id/java/data-manipulation/set-gap-width-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atur Lebar Celah di Slide Java


## Pengantar Mengatur Lebar Celah di Aspose.Slides untuk Java

Dalam tutorial ini, kami akan memandu Anda melalui proses pengaturan Lebar Celah untuk bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Lebar Celah menentukan jarak antara kolom atau batang dalam bagan, memungkinkan Anda mengontrol tampilan visual bagan.

## Prasyarat

 Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.Slides untuk Java. Anda dapat mengunduhnya dari situs web Aspose[Di Sini](https://releases.aspose.com/slides/java/).

## Panduan Langkah demi Langkah

Ikuti langkah-langkah berikut untuk mengatur Lebar Celah dalam bagan menggunakan Aspose.Slides untuk Java:

### 1. Buat Presentasi Kosong

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";

// Membuat presentasi kosong
Presentation presentation = new Presentation();
```

### 2. Akses Slide Pertama

```java
// Akses slide pertama
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Tambahkan Bagan dengan Data Default

```java
// Tambahkan bagan dengan data default
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Atur Indeks Lembar Data Grafik

```java
// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;
```

### 5. Dapatkan Buku Kerja Data Bagan

```java
// Mendapatkan lembar kerja data bagan
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Tambahkan Seri ke Bagan

```java
// Tambahkan seri ke bagan
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Tambahkan Kategori ke Bagan

```java
// Tambahkan kategori ke bagan
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Isi Data Seri

```java
// Isi data seri
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Mengisi titik data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Atur Lebar Celah

```java
// Tetapkan nilai Lebar Celah
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Simpan Presentasi

```java
// Simpan presentasi dengan bagan
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Kode Sumber Lengkap Untuk Mengatur Lebar Celah di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Membuat presentasi kosong
Presentation presentation = new Presentation();
// Akses slide pertama
ISlide slide = presentation.getSlides().get_Item(0);
// Tambahkan bagan dengan data default
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;
// Mendapatkan lembar kerja data bagan
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Tambahkan seri
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Tambahkan Kategori
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Ambil seri grafik kedua
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Sekarang mengisi data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Tetapkan nilai GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// Simpan presentasi dengan bagan
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengatur Lebar Celah untuk bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Menyesuaikan Lebar Celah memungkinkan Anda mengontrol jarak antar kolom atau batang pada bagan, sehingga meningkatkan representasi visual data Anda.

## FAQ

### Bagaimana cara mengubah nilai Lebar Celah?

 Untuk mengubah Lebar Celah, gunakan`setGapWidth` metode pada`ParentSeriesGroup`dari seri grafik. Dalam contoh yang diberikan, kami mengatur Lebar Celah menjadi 50, namun Anda dapat menyesuaikan nilai ini dengan jarak yang Anda inginkan.

### Bisakah saya menyesuaikan properti bagan lainnya?

Ya, Aspose.Slides untuk Java menyediakan kemampuan luas untuk penyesuaian bagan. Anda dapat memodifikasi berbagai properti bagan, seperti warna, label, judul, dan lainnya. Periksa Referensi API untuk informasi mendetail tentang opsi penyesuaian bagan.

### Di mana saya dapat menemukan lebih banyak sumber daya dan dokumentasi?

 Anda dapat menemukan dokumentasi komprehensif dan sumber daya tambahan di Aspose.Slides untuk Java di[Asumsikan situs web](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
