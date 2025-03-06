---
title: Hitung Rumus di Slide Java
linktitle: Hitung Rumus di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menghitung rumus di Java Slides menggunakan Aspose.Slides for Java. Panduan langkah demi langkah dengan kode sumber untuk presentasi PowerPoint dinamis.
weight: 10
url: /id/java/data-manipulation/calculate-formulas-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hitung Rumus di Slide Java


## Pengantar Menghitung Rumus di Java Slides menggunakan Aspose.Slides

Dalam panduan ini, kami akan mendemonstrasikan cara menghitung rumus di Java Slides menggunakan Aspose.Slides for Java API. Aspose.Slides adalah perpustakaan yang kuat untuk bekerja dengan presentasi PowerPoint, dan menyediakan fitur untuk memanipulasi grafik dan melakukan penghitungan rumus dalam slide.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan Pengembangan Jawa
-  Aspose.Slides untuk perpustakaan Java (Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/)
- Pengetahuan dasar tentang pemrograman Java

## Langkah 1: Buat Presentasi Baru

Pertama, mari buat presentasi PowerPoint baru dan tambahkan slide ke dalamnya. Kami akan bekerja dengan satu slide dalam contoh ini.

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## Langkah 2: Tambahkan Bagan ke Slide

Sekarang, mari tambahkan bagan kolom berkerumun ke slide. Kami akan menggunakan bagan ini untuk mendemonstrasikan penghitungan rumus.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## Langkah 3: Tetapkan Rumus dan Nilai

Selanjutnya, kita akan menetapkan rumus dan nilai untuk sel data bagan menggunakan Aspose.Slides API. Kami akan menghitung rumus untuk sel-sel ini.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// Tetapkan rumus untuk sel A1
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// Tetapkan nilai untuk sel A2
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// Tetapkan rumus untuk sel B2
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// Tetapkan rumus untuk sel C2
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// Tetapkan rumus untuk sel A1 lagi
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## Langkah 4: Simpan Presentasi

Terakhir, mari simpan presentasi yang dimodifikasi dengan rumus perhitungan.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## Source Code Lengkap Untuk Rumus Hitung di Slide Java

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Dalam panduan ini, kita telah mempelajari cara menghitung rumus di Java Slides menggunakan Aspose.Slides untuk Java. Kami membuat presentasi baru, menambahkan bagan ke dalamnya, menetapkan rumus dan nilai untuk sel data bagan, dan menyimpan presentasi dengan rumus terhitung.

## FAQ

### Bagaimana cara menetapkan rumus untuk sel data bagan?

 Anda dapat mengatur rumus untuk sel data bagan menggunakan`setFormula` metode dari`IChartDataCell` di Aspose.Slide.

### Bagaimana cara menetapkan nilai untuk sel data bagan?

 Anda dapat menetapkan nilai untuk sel data bagan menggunakan`setValue` metode dari`IChartDataCell` di Aspose.Slide.

### Bagaimana cara menghitung rumus di buku kerja?

 Anda bisa menghitung rumus di buku kerja menggunakan`calculateFormulas` metode dari`IChartDataWorkbook` di Aspose.Slide.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
