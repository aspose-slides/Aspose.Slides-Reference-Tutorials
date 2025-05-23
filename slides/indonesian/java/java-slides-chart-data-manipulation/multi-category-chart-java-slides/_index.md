---
"description": "Buat Bagan Multi-Kategori di Slide Java menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber untuk visualisasi data yang mengesankan dalam presentasi."
"linktitle": "Bagan Multi-Kategori dalam Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Bagan Multi-Kategori dalam Slide Java"
"url": "/id/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Bagan Multi-Kategori dalam Slide Java


## Pengenalan Bagan Multi-Kategori di Java Slides dengan Aspose.Slides

Dalam tutorial ini, kita akan mempelajari cara membuat bagan multikategori di slide Java menggunakan Aspose.Slides for Java API. Panduan ini akan memberikan petunjuk langkah demi langkah beserta kode sumber untuk membantu Anda membuat bagan kolom berkelompok dengan beberapa kategori dan seri.

## Prasyarat
Sebelum memulai, pastikan Anda telah menginstal dan mengatur pustaka Aspose.Slides untuk Java di lingkungan pengembangan Java Anda.

## Langkah 1: Menyiapkan Lingkungan
Pertama, impor kelas yang diperlukan dan buat objek Presentasi baru untuk bekerja dengan slide.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 2: Menambahkan Slide dan Bagan
Berikutnya, buat slide dan tambahkan diagram kolom berkelompok ke dalamnya.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Langkah 3: Menghapus Data yang Ada
Hapus semua data yang ada dari bagan.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Langkah 4: Menyiapkan Kategori Data
Sekarang, mari kita atur kategori data untuk diagram. Kita akan membuat beberapa kategori dan mengelompokkannya.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Tambahkan kategori dan kelompokkan
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Langkah 5: Menambahkan Seri
Sekarang, mari tambahkan seri ke bagan beserta titik-titik data.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Langkah 6: Menyimpan Presentasi
Terakhir, simpan presentasi dengan bagan.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Selesai! Anda telah berhasil membuat bagan multikategori dalam slide Java menggunakan Aspose.Slides. Anda dapat menyesuaikan bagan ini lebih lanjut agar sesuai dengan kebutuhan spesifik Anda.

## Source Code Lengkap Untuk Grafik Multi-Kategori di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
//            Menambahkan Seri
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Simpan presentasi dengan bagan
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara membuat bagan multikategori di slide Java menggunakan Aspose.Slides for Java API. Kita mempelajari panduan langkah demi langkah dengan kode sumber untuk membuat bagan kolom berkelompok dengan beberapa kategori dan seri.

## Pertanyaan yang Sering Diajukan

### Bagaimana saya dapat menyesuaikan tampilan grafik?

Anda dapat menyesuaikan tampilan bagan dengan memodifikasi properti seperti warna, font, dan gaya. Lihat dokumentasi Aspose.Slides untuk opsi penyesuaian terperinci.

### Bisakah saya menambahkan lebih banyak seri ke bagan?

Ya, Anda dapat menambahkan seri tambahan ke bagan dengan mengikuti proses serupa seperti yang ditunjukkan pada Langkah 5.

### Bagaimana cara mengubah jenis grafik?

Untuk mengubah jenis grafik, ganti `ChartType.ClusteredColumn` dengan jenis bagan yang diinginkan saat menambahkan bagan pada Langkah 2.

### Bagaimana cara menambahkan judul ke bagan?

Anda dapat menambahkan judul ke grafik dengan menggunakan `ch.getChartTitle().getTextFrame().setText("Chart Title");` metode.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}