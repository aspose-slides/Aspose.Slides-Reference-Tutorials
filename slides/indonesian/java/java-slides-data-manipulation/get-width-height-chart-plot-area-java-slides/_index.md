---
"description": "Pelajari cara mengambil dimensi area diagram di Java Slides menggunakan Aspose.Slides untuk Java. Tingkatkan keterampilan otomatisasi PowerPoint Anda."
"linktitle": "Mendapatkan Lebar dan Tinggi dari Area Plot Grafik di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mendapatkan Lebar dan Tinggi dari Area Plot Grafik di Java Slides"
"url": "/id/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mendapatkan Lebar dan Tinggi dari Area Plot Grafik di Java Slides


## Perkenalan

Bagan merupakan cara yang ampuh untuk memvisualisasikan data dalam presentasi PowerPoint. Terkadang, Anda mungkin perlu mengetahui dimensi area plot bagan karena berbagai alasan, seperti mengubah ukuran atau memposisikan ulang elemen dalam bagan. Panduan ini akan menunjukkan cara memperoleh lebar dan tinggi area plot menggunakan Java dan Aspose.Slides untuk Java.

## Prasyarat

Sebelum kita mulai membuat kode, pastikan Anda telah menginstal dan mengatur pustaka Aspose.Slides for Java di proyek Java Anda. Anda dapat mengunduh pustaka tersebut dari situs web Aspose [Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Menyiapkan Lingkungan

Pastikan Anda telah menambahkan pustaka Aspose.Slides for Java ke proyek Java Anda. Anda dapat melakukannya dengan menyertakan pustaka tersebut dalam dependensi proyek Anda atau dengan menambahkan berkas JAR secara manual.

## Langkah 2: Membuat Presentasi PowerPoint

Mari kita mulai dengan membuat presentasi PowerPoint dan menambahkan slide ke dalamnya. Ini akan berfungsi sebagai wadah untuk diagram kita.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Mengganti `"Your Document Directory"` dengan jalur ke direktori dokumen Anda.

## Langkah 3: Menambahkan Bagan

Sekarang, mari tambahkan diagram kolom berkelompok ke slide. Kita juga akan memvalidasi tata letak diagram.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Kode ini membuat bagan kolom berkelompok pada posisi (100, 100) dengan dimensi (500, 350).

## Langkah 4: Mendapatkan Dimensi Area Plot

Untuk mengambil lebar dan tinggi area plot grafik, kita dapat menggunakan kode berikut:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Sekarang, variabelnya `x`Bahasa Indonesia: `y`Bahasa Indonesia: `w`, Dan `h` berisi nilai masing-masing untuk koordinat X, koordinat Y, lebar, dan tinggi area plot.

## Langkah 5: Menyimpan Presentasi

Terakhir, simpan presentasi dengan bagan.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Pastikan untuk mengganti `"Chart_out.pptx"` dengan nama file keluaran yang Anda inginkan.

## Source Code Lengkap Untuk Mendapatkan Lebar dan Tinggi dari Area Plot Grafik di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Simpan presentasi dengan bagan
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam artikel ini, kami telah membahas cara memperoleh lebar dan tinggi area plot bagan di Java Slides menggunakan Aspose.Slides for Java API. Informasi ini dapat berguna saat Anda perlu menyesuaikan tata letak bagan secara dinamis dalam presentasi PowerPoint.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah jenis bagan menjadi sesuatu selain kolom berkelompok?

Anda dapat mengubah jenis grafik dengan mengganti `ChartType.ClusteredColumn` dengan enumerasi jenis grafik yang diinginkan, seperti `ChartType.Line` atau `ChartType.Pie`.

### Bisakah saya mengubah properti bagan lainnya?

Ya, Anda dapat mengubah berbagai properti bagan, seperti data, label, dan pemformatan, menggunakan API Aspose.Slides for Java. Lihat dokumentasi untuk keterangan lebih rinci.

### Apakah Aspose.Slides untuk Java cocok untuk otomatisasi PowerPoint profesional?

Ya, Aspose.Slides untuk Java adalah pustaka yang hebat untuk mengotomatiskan tugas PowerPoint dalam aplikasi Java. Pustaka ini menyediakan fitur lengkap untuk bekerja dengan presentasi, slide, bentuk, bagan, dan banyak lagi.

### Bagaimana saya dapat mempelajari lebih lanjut tentang Aspose.Slides untuk Java?

Anda dapat menemukan dokumentasi dan contoh yang lengkap di halaman dokumentasi Aspose.Slides untuk Java [Di Sini](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}