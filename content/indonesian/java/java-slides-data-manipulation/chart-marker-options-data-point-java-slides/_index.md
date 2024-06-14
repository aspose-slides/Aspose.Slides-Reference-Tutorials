---
title: Opsi Penanda Bagan pada Titik Data di Slide Java
linktitle: Opsi Penanda Bagan pada Titik Data di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Optimalkan Slide Java Anda dengan Opsi Penanda Bagan Kustom. Pelajari cara menyempurnakan titik data secara visual menggunakan Aspose.Slides untuk Java. Jelajahi panduan langkah demi langkah dan FAQ.
type: docs
weight: 14
url: /id/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

## Pengenalan Opsi Penanda Bagan pada Titik Data di Slide Java

Dalam hal membuat presentasi yang berdampak, kemampuan untuk menyesuaikan dan memanipulasi penanda bagan pada titik data dapat membuat perbedaan besar. Dengan Aspose.Slides untuk Java, Anda memiliki kekuatan untuk mengubah bagan Anda menjadi elemen yang dinamis dan menarik secara visual.

## Prasyarat

Sebelum kita mendalami bagian pengkodean, pastikan Anda memiliki prasyarat berikut:

- Lingkungan Pengembangan Jawa
- Aspose.Slide untuk Perpustakaan Java
- Lingkungan Pengembangan Terpadu Java (IDE)
- Contoh Dokumen Presentasi (misalnya, "Test.pptx")

## Langkah 1: Menyiapkan Lingkungan

Pertama, pastikan Anda telah menginstal dan menyiapkan alat yang diperlukan. Buat proyek Java di IDE Anda dan impor perpustakaan Aspose.Slides untuk Java.

## Langkah 2: Memuat Presentasi

Untuk memulai, muat contoh dokumen presentasi Anda. Dalam kode yang diberikan, kami menganggap dokumen tersebut bernama "Test.pptx."

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Langkah 3: Membuat Bagan

Sekarang, mari buat bagan dalam presentasi. Kami akan menggunakan Bagan Garis dengan Penanda dalam contoh ini.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Langkah 4: Bekerja dengan Data Bagan

Untuk memanipulasi data bagan, kita perlu mengakses buku kerja data bagan dan menyiapkan seri datanya. Kami akan menghapus seri default dan menambahkan data khusus kami.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Langkah 5: Menambahkan Penanda Kustom

Inilah bagian yang menarik - menyesuaikan penanda pada titik data. Kami akan menggunakan gambar sebagai penanda dalam contoh ini.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Menambahkan penanda khusus ke titik data
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Ulangi untuk titik data lainnya
// ...

// Mengubah ukuran penanda seri bagan
series.getMarker().setSize(15);
```

## Langkah 6: Menyimpan Presentasi

Setelah Anda menyesuaikan penanda bagan, simpan presentasi untuk melihat perubahannya.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Kode Sumber Lengkap Untuk Opsi Penanda Bagan pada Titik Data di Slide Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Membuat bagan default
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Mendapatkan indeks lembar kerja data bagan default
int defaultWorksheetIndex = 0;
//Mendapatkan lembar kerja data bagan
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Hapus seri demo
chart.getChartData().getSeries().clear();
//Tambahkan seri baru
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Atur gambarnya
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Atur gambarnya
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Ambil seri grafik pertama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Tambahkan poin baru (1:3) di sana.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//Mengubah penanda rangkaian grafik
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Dengan Aspose.Slides untuk Java, Anda dapat meningkatkan presentasi Anda dengan menyesuaikan penanda bagan pada titik data. Hal ini memungkinkan Anda membuat slide yang menakjubkan secara visual dan informatif yang memikat audiens Anda.

## FAQ

### Bagaimana cara mengubah ukuran penanda untuk titik data?

 Untuk mengubah ukuran penanda titik data, gunakan`series.getMarker().setSize()` metode dan berikan ukuran yang diinginkan sebagai argumen.

### Bisakah saya menggunakan gambar sebagai penanda khusus?

 Ya, Anda dapat menggunakan gambar sebagai penanda khusus untuk titik data. Atur jenis isian menjadi`FillType.Picture` dan berikan gambar yang ingin Anda gunakan.

### Apakah Aspose.Slides untuk Java cocok untuk membuat grafik dinamis?

Sangat! Aspose.Slides untuk Java menyediakan kemampuan luas untuk membuat bagan dinamis dan interaktif dalam presentasi Anda.

### Bisakah saya menyesuaikan aspek lain dari bagan menggunakan Aspose.Slides?

Ya, Anda dapat menyesuaikan berbagai aspek bagan, termasuk judul, sumbu, label data, dan lainnya, menggunakan Aspose.Slides untuk Java.

### Di mana saya dapat mengakses dokumentasi dan unduhan Aspose.Slides untuk Java?

 Anda dapat menemukan dokumentasinya di[Di Sini](https://reference.aspose.com/slides/java/) dan unduh perpustakaan di[Di Sini](https://releases.aspose.com/slides/java/).