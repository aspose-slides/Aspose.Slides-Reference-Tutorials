---
title: Bagan yang Ada di Slide Java
linktitle: Bagan yang Ada di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Sempurnakan presentasi PowerPoint Anda dengan Aspose.Slides untuk Java. Pelajari cara mengubah diagram yang ada secara terprogram. Panduan langkah demi langkah dengan kode sumber untuk penyesuaian bagan.
type: docs
weight: 12
url: /id/java/chart-elements/existing-chart-java-slides/
---

## Pengenalan Bagan yang Ada di Slide Java menggunakan Aspose.Slides for Java

Dalam tutorial ini, kami akan menunjukkan cara memodifikasi bagan yang ada dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Kita akan melalui langkah-langkah untuk mengubah data bagan, nama kategori, nama rangkaian, dan menambahkan rangkaian baru ke bagan. Pastikan Anda telah menyiapkan Aspose.Slides untuk Java di proyek Anda.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1. Aspose.Slides untuk perpustakaan Java disertakan dalam proyek Anda.
2. Presentasi PowerPoint yang sudah ada dengan bagan yang ingin Anda modifikasi.
3. Lingkungan pengembangan Java disiapkan.

## Langkah 1: Muat Presentasi

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";

// Buat instance kelas Presentasi yang mewakili file PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Langkah 2: Akses Slide dan Bagan

```java
// Akses slide pertama
ISlide sld = pres.getSlides().get_Item(0);

// Akses grafik pada slide
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Langkah 3: Ubah Data Bagan dan Nama Kategori

```java
// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;

//Mendapatkan lembar kerja data bagan
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Ubah nama kategori bagan
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Langkah 4: Perbarui Seri Grafik Pertama

```java
// Ambil seri grafik pertama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Perbarui nama seri
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Perbarui data seri
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Langkah 5: Perbarui Seri Grafik Kedua

```java
// Ambil seri grafik kedua
series = chart.getChartData().getSeries().get_Item(1);

// Perbarui nama seri
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Perbarui data seri
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Langkah 6: Tambahkan Seri Baru ke Bagan

```java
// Menambahkan seri baru
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Ambil seri grafik ketiga
series = chart.getChartData().getSeries().get_Item(2);

// Isi data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Langkah 7: Ubah Jenis Bagan

```java
//Ubah tipe grafik menjadi Clustered Cylinder
chart.setType(ChartType.ClusteredCylinder);
```

## Langkah 8: Simpan Presentasi yang Dimodifikasi

```java
// Simpan presentasi dengan bagan yang dimodifikasi
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Selamat! Anda telah berhasil memodifikasi bagan yang ada dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Anda sekarang dapat menggunakan kode ini untuk mengkustomisasi bagan dalam presentasi PowerPoint Anda secara terprogram.

## Source Code Lengkap Untuk Chart yang Ada di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Kelas Presentasi Instantiate yang mewakili file PPTX// Kelas Presentasi Instantiate yang mewakili file PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Akses slideMarker pertama
ISlide sld = pres.getSlides().get_Item(0);
// Tambahkan bagan dengan data default
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;
//Mendapatkan lembar kerja data bagan
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Mengubah Nama Kategori bagan
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Ambil seri grafik pertama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Sekarang memperbarui data seri
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Memodifikasi nama seri
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Ambil seri grafik kedua
series = chart.getChartData().getSeries().get_Item(1);
// Sekarang memperbarui data seri
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Memodifikasi nama seri
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Sekarang, Menambahkan seri baru
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Ambil seri grafik ke-3
series = chart.getChartData().getSeries().get_Item(2);
// Sekarang mengisi data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Simpan presentasi dengan bagan
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Kesimpulan

Dalam tutorial komprehensif ini, kita telah mempelajari cara memodifikasi bagan yang ada dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan contoh kode sumber, Anda dapat dengan mudah menyesuaikan dan memperbarui bagan untuk memenuhi kebutuhan spesifik Anda. Berikut rekap dari apa yang kami bahas:

## FAQ

### Bagaimana cara mengubah jenis grafik?

 Anda dapat mengubah jenis bagan dengan menggunakan`chart.setType(ChartType.ChartTypeHere)` metode. Mengganti`ChartTypeHere` dengan tipe grafik yang diinginkan, misalnya`ChartType.ClusteredCylinder` dalam contoh kita.

### Bisakah saya menambahkan lebih banyak titik data ke suatu rangkaian?

 Ya, Anda dapat menambahkan lebih banyak titik data ke rangkaian menggunakan`series.getDataPoints().addDataPointForBarSeries(cell)` metode. Pastikan untuk memberikan data sel yang sesuai.

### Bagaimana cara memperbarui nama kategori?

 Anda dapat memperbarui nama kategori dengan menggunakan`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` untuk mengatur nama kategori baru.

### Bagaimana cara mengubah nama seri?

 Untuk mengubah nama seri, gunakan`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` untuk mengatur nama seri baru.

### Apakah ada cara untuk menghapus rangkaian dari grafik?

 Ya, Anda dapat menghapus rangkaian dari grafik dengan menggunakan`chart.getChartData().getSeries().removeAt(index)` metode, dimana`index`adalah indeks seri yang ingin Anda hapus.