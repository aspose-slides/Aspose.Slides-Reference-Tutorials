---
"description": "Pelajari cara mengatur warna isian terbalik untuk bagan Java Slides menggunakan Aspose.Slides. Sempurnakan visualisasi bagan Anda dengan panduan langkah demi langkah dan kode sumber ini."
"linktitle": "Mengatur Bagan Warna Isian Terbalik di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Bagan Warna Isian Terbalik di Slide Java"
"url": "/id/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Bagan Warna Isian Terbalik di Slide Java


## Pengantar untuk Mengatur Bagan Warna Isian Terbalik di Slide Java

Dalam tutorial ini, kami akan menunjukkan cara mengatur warna isian terbalik untuk bagan di Java Slides menggunakan Aspose.Slides untuk Java. Membalikkan warna isian adalah fitur yang berguna saat Anda ingin menyorot nilai negatif dalam bagan dengan warna tertentu. Kami akan memberikan petunjuk langkah demi langkah dan kode sumber untuk mencapainya.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Aspose.Slides untuk pustaka Java terinstal.
2. Lingkungan pengembangan Java telah disiapkan.

## Langkah 1: Buat Presentasi

Pertama, kita perlu membuat presentasi untuk menambahkan diagram kita. Anda dapat menggunakan kode berikut untuk membuat presentasi:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Bagan

Selanjutnya, kita akan menambahkan bagan kolom berkelompok ke presentasi. Berikut cara melakukannya:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Langkah 3: Siapkan Data Bagan

Sekarang, mari kita atur data grafik, termasuk seri dan kategori:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Menambahkan seri dan kategori baru
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Langkah 4: Mengisi Data Seri

Sekarang, mari isi data seri untuk grafik:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Langkah 5: Atur Warna Isian Inversi

Untuk mengatur warna isian terbalik untuk rangkaian grafik, Anda dapat menggunakan kode berikut:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Dalam kode di atas, kita menetapkan seri untuk menginversi warna isian untuk nilai negatif dan menentukan warna untuk isian terbalik.

## Langkah 6: Simpan Presentasi

Terakhir, simpan presentasi dengan bagan:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Source Code Lengkap Untuk Set Invert Fill Color Chart di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Menambahkan seri dan kategori baru
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Ambil rangkaian grafik pertama dan isi data rangkaian tersebut.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kami telah menunjukkan kepada Anda cara mengatur warna isian terbalik untuk bagan di Java Slides menggunakan Aspose.Slides untuk Java. Fitur ini memungkinkan Anda untuk menyorot nilai negatif dalam bagan Anda dengan warna tertentu, sehingga data Anda lebih informatif secara visual.

## Pertanyaan yang Sering Diajukan

Di bagian ini, kami akan menjawab beberapa pertanyaan umum terkait pengaturan warna isian terbalik untuk bagan di Java Slides menggunakan Aspose.Slides untuk Java.

### Bagaimana cara menginstal Aspose.Slides untuk Java?

Anda dapat menginstal Aspose.Slides untuk Java dengan menyertakan file JAR Aspose.Slides dalam proyek Java Anda. Anda dapat mengunduh pustaka dari [Halaman unduhan Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/)Ikuti petunjuk instalasi yang disediakan dalam dokumentasi untuk lingkungan pengembangan spesifik Anda.

### Dapatkah saya menyesuaikan warna untuk isian terbalik pada rangkaian bagan?

Ya, Anda dapat menyesuaikan warna untuk isian terbalik dalam rangkaian bagan. Dalam contoh kode yang diberikan, `series.getInvertedSolidFillColor().setColor(Color.RED)` garis mengatur warna menjadi merah untuk isian terbalik. Anda dapat mengganti `Color.RED` dengan warna lain pilihan Anda.

### Bagaimana cara mengubah jenis bagan di Aspose.Slides untuk Java?

Anda dapat mengubah jenis grafik dengan mengubah `ChartType` parameter saat menambahkan grafik ke presentasi. Dalam contoh kode, kami menggunakan `ChartType.ClusteredColumn`Anda dapat menjelajahi jenis grafik lainnya seperti grafik garis, grafik batang, grafik pai, dll., dengan menentukan jenis grafik yang sesuai. `ChartType` nilai enum.

### Bagaimana cara menambahkan beberapa seri data ke bagan?

Untuk menambahkan beberapa seri data ke dalam bagan, Anda dapat menggunakan `chart.getChartData().getSeries().add(...)` metode untuk setiap seri yang ingin Anda tambahkan. Pastikan untuk memberikan titik data dan label yang sesuai untuk setiap seri guna mengisi diagram Anda dengan beberapa seri.

### Apakah ada cara untuk menyesuaikan aspek lain dari tampilan grafik?

Ya, Anda dapat menyesuaikan berbagai aspek tampilan bagan, termasuk label sumbu, judul, legenda, dan lainnya menggunakan Aspose.Slides untuk Java. Lihat dokumentasi untuk panduan terperinci tentang penyesuaian elemen dan tampilan bagan.

### Bisakah saya menyimpan grafik dalam format yang berbeda?

Ya, Anda dapat menyimpan grafik dalam format yang berbeda menggunakan Aspose.Slides untuk Java. Dalam contoh kode yang diberikan, kami menyimpan presentasi sebagai file PPTX. Anda dapat menggunakan format yang berbeda `SaveFormat` pilihan untuk menyimpannya dalam format lain seperti PDF, PNG, atau SVG, tergantung pada kebutuhan Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}