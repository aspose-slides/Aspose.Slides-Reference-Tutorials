---
title: Tetapkan Persentase Label Data Masuk di Slide Java
linktitle: Tetapkan Persentase Label Data Masuk di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengatur label data dengan tanda persentase dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Buat bagan yang menarik dengan panduan langkah demi langkah dan kode sumber.
weight: 17
url: /id/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Pengantar Menetapkan Masuk Persentase Label Data di Aspose.Slides untuk Java

Dalam panduan ini, kami akan memandu Anda melalui proses pengaturan label data dengan tanda persentase menggunakan Aspose.Slides untuk Java. Kami akan membuat presentasi PowerPoint dengan bagan kolom bertumpuk dan mengonfigurasi label data untuk menampilkan persentase.

## Prasyarat

 Sebelum memulai, pastikan Anda telah menambahkan pustaka Aspose.Slides untuk Java ke proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Buat Presentasi Baru

Pertama, kita membuat presentasi PowerPoint baru menggunakan Aspose.Slides.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
```

## Langkah 2: Tambahkan Slide dan Bagan

Selanjutnya, kita menambahkan slide dan bagan kolom bertumpuk ke presentasi.

```java
// Dapatkan referensi slide
ISlide slide = presentation.getSlides().get_Item(0);

// Tambahkan bagan PercentsStackedColumn pada slide
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Langkah 3: Konfigurasikan Format Angka Sumbu

Untuk menampilkan persentase, kita perlu mengonfigurasi format angka untuk sumbu vertikal grafik.

```java
// Setel NumberFormatLinkedToSource ke salah
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Langkah 4: Tambahkan Data Bagan

Kami menambahkan data ke grafik dengan membuat seri dan titik data. Dalam contoh ini, kami menambahkan dua rangkaian dengan titik datanya masing-masing.

```java
// Mendapatkan lembar kerja data bagan
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Tambahkan seri baru
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Tambahkan seri baru
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Langkah 5: Sesuaikan Label Data

Sekarang, mari sesuaikan tampilan label data.

```java
// Mengatur properti LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Langkah 6: Simpan Presentasi

Terakhir, kami menyimpan presentasi ke file PowerPoint.

```java
// Tulis presentasi ke disk
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Itu dia! Anda telah berhasil membuat presentasi PowerPoint dengan bagan kolom bertumpuk dan mengonfigurasi label data untuk menampilkan persentase menggunakan Aspose.Slides untuk Java.

## Kode Sumber Lengkap Untuk Set Label Data Persentase Masuk di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
// Dapatkan referensi slide
ISlide slide = presentation.getSlides().get_Item(0);
// Tambahkan bagan PercentsStackedColumn pada slide
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Setel NumberFormatLinkedToSource ke salah
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Mendapatkan lembar kerja data bagan
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Tambahkan seri baru
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Mengatur warna isian rangkaian
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Mengatur properti LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Tambahkan seri baru
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Mengatur jenis dan warna isian
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Tulis presentasi ke disk
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Dengan mengikuti panduan ini, Anda telah mempelajari cara membuat presentasi menarik dengan label data berbasis persentase, yang khususnya berguna untuk menyampaikan informasi secara efektif dalam laporan bisnis, materi pendidikan, dan banyak lagi.

## FAQ

### Bagaimana cara mengubah warna rangkaian bagan?

 Anda dapat mengubah warna isian rangkaian bagan menggunakan`setFill` metode seperti yang ditunjukkan pada contoh.

### Bisakah saya menyesuaikan ukuran font label data?

Ya, Anda dapat menyesuaikan ukuran font label data dengan mengatur`setFontHeight` properti seperti yang ditunjukkan dalam kode.

### Bagaimana cara menambahkan lebih banyak seri ke grafik?

 Anda dapat menambahkan rangkaian tambahan ke bagan dengan menggunakan`add` metode pada`IChartSeriesCollection` obyek.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
