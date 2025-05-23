---
"description": "Pelajari cara mengatur buku kerja eksternal di Java Slides menggunakan Aspose.Slides untuk Java. Buat presentasi dinamis dengan integrasi data Excel."
"linktitle": "Mengatur Buku Kerja Eksternal di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Buku Kerja Eksternal di Slide Java"
"url": "/id/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Buku Kerja Eksternal di Slide Java


## Pengantar untuk Mengatur Buku Kerja Eksternal di Slide Java

Dalam tutorial ini, kita akan mempelajari cara mengatur buku kerja eksternal di Java Slides menggunakan Aspose.Slides. Anda akan mempelajari cara membuat presentasi PowerPoint dengan bagan yang merujuk data dari buku kerja Excel eksternal. Di akhir panduan ini, Anda akan memiliki pemahaman yang jelas tentang cara mengintegrasikan data eksternal ke dalam presentasi Java Slides Anda.

## Prasyarat

Sebelum kita mulai menerapkannya, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) terinstal di sistem Anda.
- Pustaka Aspose.Slides untuk Java ditambahkan ke proyek Anda.
- Buku kerja Excel dengan data yang ingin Anda rujuk dalam presentasi Anda.

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

Selanjutnya, kita masukkan diagram lingkaran ke dalam presentasi. Anda dapat menyesuaikan jenis dan posisi diagram sesuai kebutuhan.

## Langkah 3: Akses Buku Kerja Eksternal

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

Untuk mengakses buku kerja eksternal, kami menggunakan `setExternalWorkbook` metode dan menyediakan jalur ke buku kerja Excel yang berisi data.

## Langkah 4: Mengikat Data Bagan

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

Terakhir, kami menyimpan presentasi dengan referensi buku kerja eksternal sebagai berkas PowerPoint.

## Source Code Lengkap Untuk Set External Workbook di Java Slides

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

Dalam tutorial ini, kita telah mempelajari cara mengatur buku kerja eksternal di Java Slides menggunakan Aspose.Slides. Kini Anda dapat membuat presentasi yang secara dinamis merujuk data dari buku kerja Excel, sehingga meningkatkan fleksibilitas dan interaktivitas slide Anda.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menginstal Aspose.Slides untuk Java?

Aspose.Slides untuk Java dapat diinstal dengan menambahkan pustaka tersebut ke proyek Java Anda. Anda dapat mengunduh pustaka tersebut dari situs web Aspose dan mengikuti petunjuk instalasi yang tersedia dalam dokumentasi.

### Dapatkah saya menggunakan jenis bagan yang berbeda dengan buku kerja eksternal?

Ya, Anda dapat menggunakan berbagai jenis bagan yang didukung oleh Aspose.Slides dan mengikatnya ke data dari buku kerja eksternal. Prosesnya mungkin sedikit berbeda, tergantung pada jenis bagan yang Anda pilih.

### Bagaimana jika struktur data buku kerja eksternal saya berubah?

Jika struktur data buku kerja eksternal Anda berubah, Anda mungkin perlu memperbarui referensi sel dalam kode Java Anda untuk memastikan bahwa data bagan tetap akurat.

### Apakah Aspose.Slides kompatibel dengan versi Java terbaru?

Aspose.Slides untuk Java diperbarui secara berkala untuk memastikan kompatibilitas dengan versi Java terbaru. Pastikan untuk memeriksa pembaruan dan menggunakan versi terbaru pustaka untuk kinerja dan kompatibilitas yang optimal.

### Dapatkah saya menambahkan beberapa bagan yang merujuk ke buku kerja eksternal yang sama?

Ya, Anda dapat menambahkan beberapa bagan ke presentasi Anda, yang semuanya merujuk ke buku kerja eksternal yang sama. Cukup ulangi langkah-langkah yang diuraikan dalam tutorial ini untuk setiap bagan yang ingin Anda buat.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}