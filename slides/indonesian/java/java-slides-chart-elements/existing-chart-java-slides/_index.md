---
"description": "Sempurnakan presentasi PowerPoint Anda dengan Aspose.Slides untuk Java. Pelajari cara memodifikasi bagan yang ada secara terprogram. Panduan langkah demi langkah dengan kode sumber untuk kustomisasi bagan."
"linktitle": "Bagan yang Ada di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Bagan yang Ada di Slide Java"
"url": "/id/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Bagan yang Ada di Slide Java


## Pengenalan Bagan yang Ada di Slide Java menggunakan Aspose.Slides untuk Java

Dalam tutorial ini, kami akan menunjukkan cara mengubah bagan yang sudah ada dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Kami akan membahas langkah-langkah untuk mengubah data bagan, nama kategori, nama seri, dan menambahkan seri baru ke bagan. Pastikan Anda telah menyiapkan Aspose.Slides untuk Java di proyek Anda.

## Prasyarat

Sebelum kita memulai, pastikan Anda memiliki prasyarat berikut:

1. Aspose.Slides untuk pustaka Java disertakan dalam proyek Anda.
2. Presentasi PowerPoint yang sudah ada dengan bagan yang ingin Anda ubah.
3. Lingkungan pengembangan Java telah disiapkan.

## Langkah 1: Muat Presentasi

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";

// Membuat instance kelas Presentasi yang merepresentasikan file PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Langkah 2: Akses Slide dan Bagan

```java
// Akses slide pertama
ISlide sld = pres.getSlides().get_Item(0);

// Akses bagan pada slide
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Langkah 3: Ubah Data Bagan dan Nama Kategori

```java
// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;

// Mendapatkan lembar kerja data grafik
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Ubah nama kategori grafik
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Langkah 4: Perbarui Seri Bagan Pertama

```java
// Ambil rangkaian grafik pertama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Perbarui nama seri
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Perbarui data seri
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Langkah 5: Perbarui Seri Bagan Kedua

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

// Mengisi data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Langkah 7: Ubah Jenis Bagan

```java
// Ubah jenis grafik menjadi Silinder Berkelompok
chart.setType(ChartType.ClusteredCylinder);
```

## Langkah 8: Simpan Presentasi yang Dimodifikasi

```java
// Simpan presentasi dengan bagan yang dimodifikasi
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Selamat! Anda telah berhasil mengubah bagan yang ada dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Kini Anda dapat menggunakan kode ini untuk menyesuaikan bagan dalam presentasi PowerPoint Anda secara terprogram.

## Source Code Lengkap Untuk Grafik Yang Ada di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Membuat instance kelas Presentasi yang mewakili file PPTX// Membuat instance kelas Presentasi yang mewakili file PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Akses slide pertamaMarker
ISlide sld = pres.getSlides().get_Item(0);
// Tambahkan bagan dengan data default
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;
// Mendapatkan lembar kerja data grafik
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Mengubah Nama Kategori Bagan
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Ambil seri grafik pertama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Sekarang memperbarui data seri
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Mengubah nama seri
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Ambil Seri Bagan Kedua
series = chart.getChartData().getSeries().get_Item(1);
// Sekarang memperbarui data seri
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Mengubah nama seri
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

Dalam tutorial komprehensif ini, kita telah mempelajari cara memodifikasi bagan yang sudah ada dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan contoh kode sumber, Anda dapat dengan mudah menyesuaikan dan memperbarui bagan untuk memenuhi persyaratan khusus Anda. Berikut ringkasan dari apa yang telah kami bahas:

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah jenis grafik?

Anda dapat mengubah jenis grafik dengan menggunakan `chart.setType(ChartType.ChartTypeHere)` metode. Ganti `ChartTypeHere` dengan jenis grafik yang diinginkan, seperti `ChartType.ClusteredCylinder` dalam contoh kita.

### Bisakah saya menambahkan lebih banyak titik data ke suatu seri?

Ya, Anda dapat menambahkan lebih banyak titik data ke seri menggunakan `series.getDataPoints().addDataPointForBarSeries(cell)` metode. Pastikan untuk memberikan data sel yang sesuai.

### Bagaimana cara memperbarui nama kategori?

Anda dapat memperbarui nama kategori dengan menggunakan `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` untuk menetapkan nama kategori baru.

### Bagaimana cara mengubah nama seri?

Untuk mengubah nama seri, gunakan `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` untuk menetapkan nama seri baru.

### Apakah ada cara untuk menghapus seri dari bagan?

Ya, Anda dapat menghapus seri dari bagan dengan menggunakan `chart.getChartData().getSeries().removeAt(index)` metode, dimana `index` adalah indeks seri yang ingin Anda hapus.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}