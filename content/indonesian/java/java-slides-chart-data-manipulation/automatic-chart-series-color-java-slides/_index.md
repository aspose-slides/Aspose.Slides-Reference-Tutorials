---
title: Warna Seri Bagan Otomatis di Slide Java
linktitle: Warna Seri Bagan Otomatis di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat bagan dinamis dengan warna rangkaian otomatis dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Tingkatkan visualisasi data Anda dengan mudah.
type: docs
weight: 14
url: /id/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## Pengantar Warna Seri Bagan Otomatis di Aspose.Slide untuk Java

Dalam tutorial ini, kita akan mempelajari cara membuat presentasi PowerPoint dengan bagan menggunakan Aspose.Slides untuk Java dan mengatur warna pengisian otomatis untuk rangkaian bagan. Warna pengisian otomatis dapat membuat bagan Anda lebih menarik secara visual dan menghemat waktu Anda dengan membiarkan perpustakaan memilihkan warna untuk Anda.

## Prasyarat

 Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.Slides for Java di proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Buat Presentasi Baru

Pertama, kita akan membuat presentasi PowerPoint baru dan menambahkan slide ke dalamnya.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
```

## Langkah 2: Tambahkan Bagan ke Slide

Selanjutnya, kita akan menambahkan bagan kolom berkerumun ke slide. Kami juga akan mengatur seri pertama untuk menunjukkan nilai.

```java
// Akses slide pertama
ISlide slide = presentation.getSlides().get_Item(0);
// Tambahkan bagan dengan data default
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Setel seri pertama ke Tampilkan Nilai
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Langkah 3: Isi Data Bagan

Sekarang, kita akan mengisi grafik dengan data. Kami akan mulai dengan menghapus rangkaian dan kategori yang dihasilkan secara default, lalu menambahkan rangkaian dan kategori baru.

```java
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

## Langkah 4: Isi Data Seri

Kami akan mengisi data seri untuk Seri 1 dan Seri 2.

```java
// Ambil seri grafik pertama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Sekarang mengisi data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Ambil seri grafik kedua
series = chart.getChartData().getSeries().get_Item(1);
// Sekarang mengisi data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Langkah 5: Atur Warna Isi Otomatis untuk Seri

Sekarang, mari kita atur warna pengisian otomatis untuk rangkaian bagan. Ini akan membuat perpustakaan memilih warna untuk kita.

```java
// Mengatur warna isian otomatis untuk rangkaian
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Langkah 6: Simpan Presentasi

Terakhir, kami akan menyimpan presentasi dengan bagan ke file PowerPoint.

```java
// Simpan presentasi dengan bagan
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Kode Sumber Lengkap Untuk Warna Seri Bagan Otomatis di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
try
{
	// Akses slide pertama
	ISlide slide = presentation.getSlides().get_Item(0);
	// Tambahkan bagan dengan data default
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
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
	// Mengatur warna isian otomatis untuk rangkaian
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Ambil seri grafik kedua
	series = chart.getChartData().getSeries().get_Item(1);
	// Sekarang mengisi data seri
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Mengatur warna isian untuk seri
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Simpan presentasi dengan bagan
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara membuat presentasi PowerPoint dengan bagan menggunakan Aspose.Slides untuk Java dan mengatur warna pengisian otomatis untuk rangkaian bagan. Warna otomatis dapat meningkatkan daya tarik visual bagan Anda dan membuat presentasi Anda lebih menarik. Anda dapat menyesuaikan bagan lebih lanjut sesuai kebutuhan untuk kebutuhan spesifik Anda.

## FAQ

### Bagaimana cara mengatur warna pengisian otomatis untuk rangkaian bagan di Aspose.Slides untuk Java?

Untuk mengatur warna pengisian otomatis untuk rangkaian bagan di Aspose.Slides untuk Java, gunakan kode berikut:

```java
// Mengatur warna isian otomatis untuk rangkaian
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Kode ini akan membiarkan perpustakaan memilih warna secara otomatis untuk rangkaian bagan.

### Bisakah saya menyesuaikan warna bagan jika diperlukan?

 Ya, Anda dapat menyesuaikan warna bagan sesuai kebutuhan. Dalam contoh yang diberikan, kami menggunakan warna pengisian otomatis, namun Anda dapat mengatur warna tertentu dengan memodifikasinya`FillType` Dan`SolidFillColor` properti format seri.

### Bagaimana cara menambahkan rangkaian atau kategori tambahan ke bagan?

 Untuk menambahkan rangkaian atau kategori tambahan ke bagan, gunakan`getSeries()` Dan`getCategories()` metode grafik`ChartData` obyek. Anda dapat menambahkan rangkaian dan kategori baru dengan menentukan data dan labelnya.

### Apakah mungkin untuk memformat bagan dan label lebih lanjut?

Ya, Anda dapat memformat lebih lanjut bagan, seri, dan label sesuai kebutuhan. Aspose.Slides untuk Java menyediakan opsi pemformatan ekstensif untuk bagan, termasuk font, warna, gaya, dan banyak lagi. Anda dapat menjelajahi dokumentasi untuk detail selengkapnya tentang opsi pemformatan.

### Di mana saya dapat menemukan informasi selengkapnya tentang bekerja dengan Aspose.Slides untuk Java?

 Untuk informasi lebih lanjut dan dokumentasi mendetail tentang Aspose.Slides untuk Java, Anda dapat mengunjungi dokumentasi referensi[Di Sini](https://reference.aspose.com/slides/java/).