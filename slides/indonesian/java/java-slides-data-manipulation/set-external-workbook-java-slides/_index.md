---
title: Atur Buku Kerja Eksternal di Slide Java
linktitle: Atur Buku Kerja Eksternal di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengatur buku kerja eksternal di Java Slides menggunakan Aspose.Slides for Java. Buat presentasi dinamis dengan integrasi data Excel.
weight: 19
url: /id/java/data-manipulation/set-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengantar Mengatur Buku Kerja Eksternal di Slide Java

Dalam tutorial ini, kita akan mempelajari cara mengatur buku kerja eksternal di Java Slides menggunakan Aspose.Slides. Anda akan mempelajari cara membuat presentasi PowerPoint dengan bagan yang mereferensikan data dari buku kerja Excel eksternal. Di akhir panduan ini, Anda akan memiliki pemahaman yang jelas tentang cara mengintegrasikan data eksternal ke dalam presentasi Java Slides Anda.

## Prasyarat

Sebelum kita mendalami penerapannya, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) diinstal pada sistem Anda.
- Aspose.Slides untuk perpustakaan Java ditambahkan ke proyek Anda.
- Buku kerja Excel dengan data yang ingin Anda referensikan dalam presentasi Anda.

## Langkah 1: Buat Presentasi Baru

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Kita mulai dengan membuat presentasi PowerPoint baru menggunakan Aspose.Slides.

## Langkah 2: Tambahkan Bagan

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Selanjutnya, kita menyisipkan diagram lingkaran ke dalam presentasi. Anda dapat menyesuaikan jenis dan posisi grafik sesuai kebutuhan.

## Langkah 3: Akses Buku Kerja Eksternal

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Untuk mengakses buku kerja eksternal, kami menggunakan`setExternalWorkbook` metode dan menyediakan jalur ke buku kerja Excel yang berisi data.

## Langkah 4: Ikat Data Bagan

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Kami mengikat bagan ke data dari buku kerja eksternal dengan menentukan referensi sel untuk seri dan kategori.

## Langkah 5: Simpan Presentasi

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Terakhir, kami menyimpan presentasi dengan referensi buku kerja eksternal sebagai file PowerPoint.

## Kode Sumber Lengkap Untuk Mengatur Buku Kerja Eksternal di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara mengatur buku kerja eksternal di Java Slides menggunakan Aspose.Slides. Anda kini dapat membuat presentasi yang secara dinamis mereferensikan data dari buku kerja Excel, sehingga meningkatkan fleksibilitas dan interaktivitas slide Anda.

## FAQ

### Bagaimana cara menginstal Aspose.Slides untuk Java?

Aspose.Slides untuk Java dapat diinstal dengan menambahkan perpustakaan ke proyek Java Anda. Anda dapat mengunduh perpustakaan dari situs web Aspose dan mengikuti petunjuk instalasi yang disediakan dalam dokumentasi.

### Bisakah saya menggunakan tipe bagan berbeda dengan buku kerja eksternal?

Ya, Anda bisa menggunakan berbagai tipe bagan yang didukung oleh Aspose.Slides dan mengikatnya ke data dari buku kerja eksternal. Prosesnya mungkin sedikit berbeda tergantung pada tipe grafik yang Anda pilih.

### Bagaimana jika struktur data buku kerja eksternal saya berubah?

Jika struktur data buku kerja eksternal Anda berubah, Anda mungkin perlu memperbarui referensi sel dalam kode Java Anda untuk memastikan bahwa data bagan tetap akurat.

### Apakah Aspose.Slides kompatibel dengan versi Java terbaru?

Aspose.Slides untuk Java diperbarui secara berkala untuk memastikan kompatibilitas dengan versi Java terbaru. Pastikan untuk memeriksa pembaruan dan menggunakan perpustakaan versi terbaru untuk kinerja dan kompatibilitas optimal.

### Bisakah saya menambahkan beberapa bagan yang merujuk pada buku kerja eksternal yang sama?

Ya, Anda bisa menambahkan beberapa bagan ke presentasi Anda, semuanya merujuk pada buku kerja eksternal yang sama. Cukup ulangi langkah-langkah yang diuraikan dalam tutorial ini untuk setiap bagan yang ingin Anda buat.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
