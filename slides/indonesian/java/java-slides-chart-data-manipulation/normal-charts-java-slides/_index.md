---
title: Grafik Normal di Slide Java
linktitle: Grafik Normal di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Buat Bagan Normal di Slide Java dengan Aspose.Slides untuk Java. Panduan langkah demi langkah dan kode sumber untuk membuat, menyesuaikan, dan menyimpan bagan dalam presentasi PowerPoint.
type: docs
weight: 21
url: /id/java/chart-data-manipulation/normal-charts-java-slides/
---

## Pengantar Grafik Normal di Slide Java

Dalam tutorial ini, kita akan memandu proses pembuatan bagan normal di Java Slides menggunakan Aspose.Slides for Java API. Kami akan menggunakan petunjuk langkah demi langkah bersama dengan kode sumber untuk menunjukkan cara membuat bagan kolom berkerumun dalam presentasi PowerPoint.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Aspose.Slides untuk Java API diinstal.
2. Lingkungan pengembangan Java telah disiapkan.
3. Pengetahuan dasar tentang pemrograman Java.

## Langkah 1: Menyiapkan Proyek

Pastikan Anda memiliki direktori untuk proyek Anda. Sebut saja "Direktori Dokumen Anda" seperti yang disebutkan dalam kode. Anda dapat menggantinya dengan jalur sebenarnya ke direktori proyek Anda.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Langkah 2: Membuat Presentasi

Sekarang, mari buat presentasi PowerPoint dan akses slide pertamanya.

```java
// Buat instance kelas Presentasi yang mewakili file PPTX
Presentation pres = new Presentation();
// Akses slide pertama
ISlide sld = pres.getSlides().get_Item(0);
```

## Langkah 3: Menambahkan Bagan

Kami akan menambahkan bagan kolom berkerumun ke slide dan menetapkan judulnya.

```java
// Tambahkan bagan dengan data default
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Judul bagan pengaturan
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Langkah 4: Mengatur Data Bagan

Selanjutnya, kita akan mengatur data grafik dengan menentukan seri dan kategori.

```java
// Setel seri pertama ke Tampilkan Nilai
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;

// Mendapatkan lembar kerja data bagan
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Hapus seri dan kategori yang dihasilkan secara default
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Menambahkan seri baru
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Menambahkan kategori baru
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Langkah 5: Mengisi Data Seri

Sekarang, mari kita isi titik data seri untuk bagan tersebut.

```java
// Ambil seri grafik pertama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Mengisi data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Mengatur warna isian untuk seri
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Ambil seri grafik kedua
series = chart.getChartData().getSeries().get_Item(1);

// Mengisi data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Mengatur warna isian untuk seri
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Langkah 6: Menyesuaikan Label

Mari sesuaikan label data untuk rangkaian bagan.

```java
// Label pertama akan menampilkan nama Kategori
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Tampilkan nilai untuk label ketiga dengan nama seri dan pemisah
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Langkah 7: Menyimpan Presentasi

Terakhir, simpan presentasi dengan bagan ke direktori proyek Anda.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Itu dia! Anda telah berhasil membuat bagan kolom berkerumun dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan bagan ini lebih lanjut sesuai dengan kebutuhan Anda.

## Kode Sumber Lengkap Untuk Grafik Normal di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Buat instance kelas Presentasi yang mewakili file PPTX
Presentation pres = new Presentation();
// Akses slide pertama
ISlide sld = pres.getSlides().get_Item(0);
// Tambahkan bagan dengan data default
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Judul bagan pengaturan
// Chart.getChartTitle().getTextFrameForOverriding().setText("Contoh Judul");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Setel seri pertama ke Tampilkan Nilai
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;
// Mendapatkan lembar kerja data bagan
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Hapus seri dan kategori yang dihasilkan secara default
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Menambahkan seri baru
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Menambahkan kategori baru
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Ambil seri grafik pertama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Sekarang mengisi data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Mengatur warna isian untuk seri
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Ambil seri grafik kedua
series = chart.getChartData().getSeries().get_Item(1);
// Sekarang mengisi data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Mengatur warna isian untuk seri
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Label pertama akan menampilkan nama Kategori
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Tampilkan nilai untuk label ketiga
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Simpan presentasi dengan bagan
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara membuat grafik normal di Java Slides menggunakan Aspose.Slides for Java API. Kami mempelajari panduan langkah demi langkah dengan kode sumber untuk membuat bagan kolom berkerumun dalam presentasi PowerPoint.

## FAQ

### Bagaimana cara mengubah jenis grafik?

 Untuk mengubah tipe bagan, ubah`ChartType`parameter saat menambahkan grafik menggunakan`sld.getShapes().addChart()`. Anda dapat memilih dari berbagai jenis bagan yang tersedia di Aspose.Slides.

### Bisakah saya mengubah warna rangkaian bagan?

 Ya, Anda dapat mengubah warna rangkaian bagan dengan mengatur warna isian untuk setiap rangkaian menggunakan`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Bagaimana cara menambahkan lebih banyak kategori atau rangkaian ke bagan?

 Anda dapat menambahkan lebih banyak kategori atau rangkaian ke bagan dengan menambahkan titik data dan label baru menggunakan`chart.getChartData().getCategories().add()` Dan`chart.getChartData().getSeries().add()` metode.

### Bagaimana cara menyesuaikan judul grafik lebih lanjut?

 Anda dapat menyesuaikan judul bagan lebih lanjut dengan memodifikasi properti`chart.getChartTitle()` seperti perataan teks, ukuran font, dan warna.

### Bagaimana cara menyimpan grafik ke format file lain?

 Untuk menyimpan bagan ke format file lain, ubah`SaveFormat` parameter di`pres.save()` metode ke format yang diinginkan (misalnya, PDF, PNG, JPEG).