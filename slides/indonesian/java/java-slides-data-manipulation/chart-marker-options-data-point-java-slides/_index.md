---
"description": "Optimalkan Slide Java Anda dengan Opsi Penanda Bagan Kustom. Pelajari cara menyempurnakan titik data secara visual menggunakan Aspose.Slides untuk Java. Jelajahi panduan langkah demi langkah dan Tanya Jawab Umum."
"linktitle": "Opsi Penanda Bagan pada Titik Data di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Opsi Penanda Bagan pada Titik Data di Java Slides"
"url": "/id/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Opsi Penanda Bagan pada Titik Data di Java Slides


## Pengenalan Opsi Penanda Bagan pada Titik Data di Slide Java

Dalam hal membuat presentasi yang mengesankan, kemampuan untuk menyesuaikan dan memanipulasi penanda bagan pada titik data dapat membuat perbedaan besar. Dengan Aspose.Slides untuk Java, Anda memiliki kekuatan untuk mengubah bagan Anda menjadi elemen yang dinamis dan menarik secara visual.

## Prasyarat

Sebelum kita masuk ke bagian pengkodean, pastikan Anda memiliki prasyarat berikut:

- Lingkungan Pengembangan Java
- Aspose.Slides untuk Pustaka Java
- Lingkungan Pengembangan Terpadu (IDE) Java
- Contoh Dokumen Presentasi (misalnya, "Test.pptx")

## Langkah 1: Menyiapkan Lingkungan

Pertama, pastikan Anda telah memasang dan menyiapkan alat yang diperlukan. Buat proyek Java di IDE Anda dan impor pustaka Aspose.Slides for Java.

## Langkah 2: Memuat Presentasi

Untuk memulai, muat contoh dokumen presentasi Anda. Dalam kode yang diberikan, kami berasumsi dokumen tersebut diberi nama "Test.pptx."

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Langkah 3: Membuat Bagan

Sekarang, mari kita buat diagram dalam presentasi. Kita akan menggunakan Diagram Garis dengan Penanda dalam contoh ini.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Langkah 4: Bekerja dengan Data Bagan

Untuk memanipulasi data grafik, kita perlu mengakses buku kerja data grafik dan menyiapkan rangkaian data. Kita akan menghapus rangkaian default dan menambahkan data kustom kita.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Langkah 5: Menambahkan Penanda Kustom

Di sinilah bagian yang menarik - menyesuaikan penanda pada titik data. Kita akan menggunakan gambar sebagai penanda dalam contoh ini.

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

// Mengubah ukuran penanda seri grafik
series.getMarker().setSize(15);
```

## Langkah 6: Menyimpan Presentasi

Setelah Anda menyesuaikan penanda bagan Anda, simpan presentasi untuk melihat perubahannya dalam tindakan.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Source Code Lengkap Untuk Opsi Penanda Grafik pada Titik Data di Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Membuat grafik default
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Mendapatkan indeks lembar kerja data grafik default
int defaultWorksheetIndex = 0;
//Mendapatkan lembar kerja data grafik
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Hapus seri demo
chart.getChartData().getSeries().clear();
//Tambahkan seri baru
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Mengatur gambar
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Mengatur gambar
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Ambil seri grafik pertama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Tambahkan titik baru (1:3) di sana.
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
//Mengubah penanda seri grafik
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Dengan Aspose.Slides untuk Java, Anda dapat meningkatkan presentasi Anda dengan menyesuaikan penanda bagan pada titik data. Ini memungkinkan Anda membuat slide yang memukau secara visual dan informatif yang memikat audiens Anda.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah ukuran penanda untuk titik data?

Untuk mengubah ukuran penanda untuk titik data, gunakan `series.getMarker().setSize()` metode dan berikan ukuran yang diinginkan sebagai argumen.

### Bisakah saya menggunakan gambar sebagai penanda khusus?

Ya, Anda dapat menggunakan gambar sebagai penanda khusus untuk titik data. Atur jenis isian ke `FillType.Picture` dan berikan gambar yang ingin Anda gunakan.

### Apakah Aspose.Slides untuk Java cocok untuk membuat bagan dinamis?

Tentu saja! Aspose.Slides untuk Java menyediakan kemampuan ekstensif untuk membuat diagram yang dinamis dan interaktif dalam presentasi Anda.

### Bisakah saya menyesuaikan aspek lain dari bagan menggunakan Aspose.Slides?

Ya, Anda dapat menyesuaikan berbagai aspek bagan, termasuk judul, sumbu, label data, dan lainnya, menggunakan Aspose.Slides untuk Java.

### Di mana saya dapat mengakses dokumentasi dan unduhan Aspose.Slides untuk Java?

Anda dapat menemukan dokumentasinya di [Di Sini](https://reference.aspose.com/slides/java/) dan unduh perpustakaan di [Di Sini](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}