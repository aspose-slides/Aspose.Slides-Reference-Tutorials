---
"description": "Pelajari cara membuat bagan dinamis dengan warna seri otomatis dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Sempurnakan visualisasi data Anda dengan mudah."
"linktitle": "Seri Bagan Warna Otomatis di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Seri Bagan Warna Otomatis di Java Slides"
"url": "/id/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Seri Bagan Warna Otomatis di Java Slides


## Pengenalan Warna Seri Bagan Otomatis di Aspose.Slides untuk Java

Dalam tutorial ini, kita akan menjelajahi cara membuat presentasi PowerPoint dengan bagan menggunakan Aspose.Slides untuk Java dan mengatur warna isian otomatis untuk rangkaian bagan. Warna isian otomatis dapat membuat bagan Anda lebih menarik secara visual dan menghemat waktu Anda dengan membiarkan pustaka memilih warna untuk Anda.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.Slides for Java di proyek Anda. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Buat Presentasi Baru

Pertama, kita akan membuat presentasi PowerPoint baru dan menambahkan slide ke dalamnya.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
```

## Langkah 2: Tambahkan Bagan ke Slide

Selanjutnya, kita akan menambahkan bagan kolom berkelompok ke slide. Kita juga akan mengatur rangkaian pertama untuk menampilkan nilai.

```java
// Akses slide pertama
ISlide slide = presentation.getSlides().get_Item(0);
// Tambahkan bagan dengan data default
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Tetapkan seri pertama untuk Menampilkan Nilai
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Langkah 3: Mengisi Data Bagan

Sekarang, kita akan mengisi grafik dengan data. Kita akan mulai dengan menghapus seri dan kategori yang dihasilkan secara default, lalu menambahkan seri dan kategori baru.

```java
// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;
// Mendapatkan lembar kerja data grafik
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

## Langkah 4: Mengisi Data Seri

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

Sekarang, mari kita tetapkan warna isian otomatis untuk rangkaian grafik. Ini akan membuat pustaka memilih warna untuk kita.

```java
// Mengatur warna isi otomatis untuk seri
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Langkah 6: Simpan Presentasi

Terakhir, kita akan menyimpan presentasi beserta bagan ke dalam berkas PowerPoint.

```java
// Simpan presentasi dengan bagan
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Source Code Lengkap Untuk Pewarnaan Seri Grafik Otomatis di Java Slides

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
	// Tetapkan seri pertama untuk Menampilkan Nilai
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Mengatur indeks lembar data grafik
	int defaultWorksheetIndex = 0;
	// Mendapatkan lembar kerja data grafik
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
	// Mengatur warna isi otomatis untuk seri
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

Dalam tutorial ini, kita telah mempelajari cara membuat presentasi PowerPoint dengan bagan menggunakan Aspose.Slides untuk Java dan mengatur warna isian otomatis untuk rangkaian bagan. Warna otomatis dapat meningkatkan daya tarik visual bagan Anda dan membuat presentasi Anda lebih menarik. Anda dapat menyesuaikan bagan lebih lanjut sesuai kebutuhan khusus Anda.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengatur warna isian otomatis untuk rangkaian bagan di Aspose.Slides untuk Java?

Untuk mengatur warna isian otomatis untuk rangkaian bagan di Aspose.Slides untuk Java, gunakan kode berikut:

```java
// Mengatur warna isi otomatis untuk seri
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Kode ini akan membiarkan perpustakaan memilih warna secara otomatis untuk rangkaian bagan.

### Bisakah saya menyesuaikan warna bagan jika diperlukan?

Ya, Anda dapat menyesuaikan warna grafik sesuai kebutuhan. Dalam contoh yang diberikan, kami menggunakan warna isian otomatis, tetapi Anda dapat mengatur warna tertentu dengan memodifikasi `FillType` Dan `SolidFillColor` properti format seri.

### Bagaimana cara menambahkan seri atau kategori tambahan ke bagan?

Untuk menambahkan seri atau kategori tambahan ke bagan, gunakan `getSeries()` Dan `getCategories()` metode grafik `ChartData` objek. Anda dapat menambahkan seri dan kategori baru dengan menentukan data dan labelnya.

### Apakah mungkin untuk memformat bagan dan label lebih lanjut?

Ya, Anda dapat memformat lebih lanjut bagan, seri, dan label sesuai kebutuhan. Aspose.Slides untuk Java menyediakan opsi pemformatan yang lengkap untuk bagan, termasuk fon, warna, gaya, dan banyak lagi. Anda dapat menjelajahi dokumentasi untuk detail lebih lanjut tentang opsi pemformatan.

### Di mana saya dapat menemukan informasi lebih lanjut tentang bekerja dengan Aspose.Slides untuk Java?

Untuk informasi lebih lanjut dan dokumentasi terperinci tentang Aspose.Slides untuk Java, Anda dapat mengunjungi dokumentasi referensi [Di Sini](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}