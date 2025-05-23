---
"description": "Pelajari cara membuat bagan yang memukau dan mengelola properti dalam slide Java dengan Aspose.Slides. Panduan langkah demi langkah dengan kode sumber untuk presentasi yang hebat."
"linktitle": "Mengelola Properti Grafik di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengelola Properti Grafik di Java Slides"
"url": "/id/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengelola Properti Grafik di Java Slides


## Pengantar Pengelolaan Properti dan Bagan di Java Slides menggunakan Aspose.Slides

Dalam tutorial ini, kita akan menjelajahi cara mengelola properti dan membuat bagan di slide Java menggunakan Aspose.Slides. Aspose.Slides adalah API Java yang hebat untuk bekerja dengan presentasi PowerPoint. Kita akan membahas prosesnya langkah demi langkah, termasuk contoh kode sumber.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menginstal dan mengatur pustaka Aspose.Slides untuk Java di proyek Anda. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).

## Menambahkan Bagan ke Slide

Untuk menambahkan bagan ke slide, ikuti langkah-langkah berikut:

1. Impor kelas yang diperlukan dan buat contoh kelas Presentasi.

```java
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
```

2. Akses slide tempat Anda ingin menambahkan diagram. Dalam contoh ini, kita mengakses slide pertama.

```java
// Akses slide pertama
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Tambahkan diagram dengan data default. Dalam kasus ini, kami menambahkan diagram StackedColumn3D.

```java
// Tambahkan bagan dengan data default
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Pengaturan Data Bagan

Untuk mengatur data grafik, kita perlu membuat buku kerja data grafik dan menambahkan seri dan kategori. Ikuti langkah-langkah berikut:

4. Tetapkan indeks lembar data bagan.

```java
// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;
```

5. Dapatkan buku kerja data bagan.

```java
// Mendapatkan lembar kerja data grafik
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Tambahkan seri ke bagan. Dalam contoh ini, kami menambahkan dua seri yang diberi nama "Seri 1" dan "Seri 2."

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Tambahkan kategori ke bagan. Di sini, kami menambahkan tiga kategori.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Mengatur Properti Rotasi 3D

Sekarang, mari kita atur properti rotasi 3D untuk grafik:

8. Atur sumbu sudut siku-siku.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Mengatur sudut rotasi untuk sumbu X dan Y. Dalam contoh ini, kita memutar X sebesar 40 derajat dan Y sebesar 270 derajat.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Atur persentase kedalaman ke 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Mengisi Data Seri

11. Ambil rangkaian grafik kedua dan isi dengan titik data.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Mengisi data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Menyesuaikan Tumpang Tindih

12. Tetapkan nilai tumpang tindih untuk seri. Misalnya, Anda dapat menetapkannya ke 100 agar tidak ada tumpang tindih.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Menyimpan Presentasi

Terakhir, simpan presentasi ke disk.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Selesai! Anda telah berhasil membuat bagan kolom bertumpuk 3D dengan properti khusus menggunakan Aspose.Slides di Java.

## Source Code Lengkap Untuk Mengelola Grafik Properti di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
// Akses slide pertama
ISlide slide = presentation.getSlides().get_Item(0);
// Tambahkan bagan dengan data default
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;
// Mendapatkan lembar kerja data grafik
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Tambahkan seri
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Tambahkan Kategori
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Tetapkan properti Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Ambil seri grafik kedua
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Sekarang mengisi data seri
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Tetapkan nilai OverLap
series.getParentSeriesGroup().setOverlap((byte) 100);
// Tulis presentasi ke disk
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Dalam tutorial ini, kami mendalami dunia pengelolaan properti dan pembuatan bagan dalam slide Java menggunakan Aspose.Slides. Aspose.Slides adalah API Java tangguh yang memungkinkan pengembang bekerja dengan presentasi PowerPoint secara efisien. Kami membahas langkah-langkah penting dan memberikan contoh kode sumber untuk memandu Anda melalui proses tersebut.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah jenis grafik?

Anda dapat mengubah jenis grafik dengan memodifikasi `ChartType` parameter saat menambahkan bagan. Lihat dokumentasi Aspose.Slides untuk mengetahui jenis bagan yang tersedia.

### Bisakah saya menyesuaikan warna grafik?

Ya, Anda dapat menyesuaikan warna bagan dengan mengatur properti isian titik data seri atau kategori.

### Bagaimana cara menambahkan lebih banyak titik data ke suatu seri?

Anda dapat menambahkan lebih banyak titik data ke suatu seri dengan menggunakan `series.getDataPoints().addDataPointForBarSeries()` metode dan menentukan sel yang berisi nilai data.

### Bagaimana saya dapat mengatur sudut rotasi yang berbeda?

Untuk mengatur sudut rotasi yang berbeda untuk sumbu X dan Y, gunakan `chart.getRotation3D().setRotationX()` Dan `chart.getRotation3D().setRotationY()` dengan nilai sudut yang diinginkan.

### Properti 3D apa lagi yang dapat saya sesuaikan?

Anda dapat menjelajahi properti 3D lainnya pada bagan, seperti kedalaman, perspektif, dan pencahayaan, dengan merujuk pada dokumentasi Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}