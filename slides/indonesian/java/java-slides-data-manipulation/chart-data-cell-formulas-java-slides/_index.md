---
"description": "Pelajari cara mengatur rumus sel data bagan dalam presentasi PowerPoint Java menggunakan Aspose.Slides untuk Java. Buat bagan dinamis dengan rumus."
"linktitle": "Rumus Sel Data Bagan di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Rumus Sel Data Bagan di Slide Java"
"url": "/id/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Rumus Sel Data Bagan di Slide Java


## Pengenalan Rumus Sel Data Bagan di Aspose.Slides untuk Java

Dalam tutorial ini, kita akan mempelajari cara bekerja dengan rumus sel data bagan menggunakan Aspose.Slides untuk Java. Dengan Aspose.Slides, Anda dapat membuat dan memanipulasi bagan dalam presentasi PowerPoint, termasuk pengaturan rumus untuk sel data.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.Slides for Java. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Buat Presentasi PowerPoint

Pertama, mari buat presentasi PowerPoint baru dan tambahkan bagan ke dalamnya.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Tambahkan bagan ke slide pertama
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Dapatkan buku kerja untuk data bagan
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Lanjutkan dengan operasi sel data
    // ...
    
    // Simpan presentasi
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Langkah 2: Mengatur Rumus untuk Sel Data

Sekarang, mari kita tetapkan rumus untuk sel data tertentu dalam bagan. Dalam contoh ini, kita akan menetapkan rumus untuk dua sel yang berbeda.

### Sel 1: Menggunakan Notasi A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

Pada kode di atas, kami menetapkan rumus untuk sel B2 menggunakan notasi A1. Rumus tersebut menghitung jumlah sel F2 hingga H5 dan menambahkan 1 ke hasilnya.

### Sel 2: Menggunakan Notasi R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Di sini, kami menetapkan rumus untuk sel C2 menggunakan notasi R1C1. Rumus tersebut menghitung nilai maksimum dalam rentang R2C6 hingga R5C8, lalu membaginya dengan 3.

## Langkah 3: Hitung Rumus

Setelah menetapkan rumus, penting untuk menghitungnya menggunakan kode berikut:

```java
workbook.calculateFormulas();
```

Langkah ini memastikan bahwa bagan mencerminkan nilai yang diperbarui berdasarkan rumus.

## Langkah 4: Simpan Presentasi

Terakhir, simpan presentasi yang sudah dimodifikasi ke sebuah berkas.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Source Code Lengkap Rumus Sel Data Grafik di Java Slides

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kami telah mempelajari cara bekerja dengan rumus sel data bagan di Aspose.Slides untuk Java. Kami telah membahas cara membuat presentasi PowerPoint, menambahkan bagan, menetapkan rumus untuk sel data, menghitung rumus, dan menyimpan presentasi. Kini Anda dapat memanfaatkan kemampuan ini untuk membuat bagan yang dinamis dan berbasis data dalam presentasi Anda.

## Tanya Jawab Umum

### Bagaimana cara menambahkan bagan ke slide tertentu?

Untuk menambahkan grafik ke slide tertentu, Anda dapat menggunakan `getSlides().get_Item(slideIndex)` metode untuk mengakses slide yang diinginkan, lalu gunakan `addChart` metode untuk menambahkan bagan.

### Dapatkah saya menggunakan berbagai jenis rumus dalam sel data?

Ya, Anda dapat menggunakan berbagai jenis rumus, termasuk operasi matematika, fungsi, dan referensi ke sel lain, dalam rumus sel data.

### Bagaimana cara mengubah jenis grafik?

Anda dapat mengubah jenis grafik dengan menggunakan `setChartType` metode pada `IChart` objek dan menentukan yang diinginkan `ChartType`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}