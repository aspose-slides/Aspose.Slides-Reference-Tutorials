---
title: Dapatkan Lebar dan Tinggi dari Area Plot Bagan di Slide Java
linktitle: Dapatkan Lebar dan Tinggi dari Area Plot Bagan di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengambil dimensi area plot bagan di Java Slides menggunakan Aspose.Slides untuk Java. Tingkatkan keterampilan otomatisasi PowerPoint Anda.
weight: 21
url: /id/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Perkenalan

Bagan adalah cara ampuh untuk memvisualisasikan data dalam presentasi PowerPoint. Terkadang, Anda mungkin perlu mengetahui dimensi area plot bagan karena berbagai alasan, seperti mengubah ukuran atau memposisikan ulang elemen dalam bagan. Panduan ini akan menunjukkan cara mendapatkan lebar dan tinggi area plot menggunakan Java dan Aspose.Slides untuk Java.

## Prasyarat

 Sebelum kita mendalami kodenya, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda. Anda dapat mengunduh perpustakaan dari situs web Aspose[Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Menyiapkan Lingkungan

Pastikan Anda memiliki perpustakaan Aspose.Slides untuk Java yang ditambahkan ke proyek Java Anda. Anda dapat melakukan ini dengan menyertakan perpustakaan dalam dependensi proyek Anda atau dengan menambahkan file JAR secara manual.

## Langkah 2: Membuat Presentasi PowerPoint

Mari kita mulai dengan membuat presentasi PowerPoint dan menambahkan slide ke dalamnya. Ini akan berfungsi sebagai wadah untuk bagan kita.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Mengganti`"Your Document Directory"` dengan jalur ke direktori dokumen Anda.

## Langkah 3: Menambahkan Bagan

Sekarang, mari tambahkan bagan kolom berkerumun ke slide. Kami juga akan memvalidasi tata letak grafik.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Kode ini membuat bagan kolom berkerumun pada posisi (100, 100) dengan dimensi (500, 350).

## Langkah 4: Mendapatkan Dimensi Area Plot

Untuk mengambil lebar dan tinggi area plot grafik, kita dapat menggunakan kode berikut:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 Sekarang, variabelnya`x`, `y`, `w` , Dan`h` berisi nilai masing-masing untuk koordinat X, koordinat Y, lebar, dan tinggi area plot.

## Langkah 5: Menyimpan Presentasi

Terakhir, simpan presentasi dengan bagan.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Pastikan untuk mengganti`"Chart_out.pptx"` dengan nama file keluaran yang Anda inginkan.

## Kode Sumber Lengkap Untuk Mendapatkan Lebar dan Tinggi dari Area Plot Bagan di Slide Java

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

Dalam artikel ini, kami telah membahas cara mendapatkan lebar dan tinggi area plot bagan di Java Slides menggunakan Aspose.Slides for Java API. Informasi ini dapat berguna ketika Anda perlu menyesuaikan tata letak bagan Anda secara dinamis dalam presentasi PowerPoint.

## FAQ

### Bagaimana cara mengubah tipe bagan menjadi selain kolom berkerumun?

 Anda dapat mengubah jenis grafik dengan menggantinya`ChartType.ClusteredColumn` dengan enumerasi jenis bagan yang diinginkan, seperti`ChartType.Line` atau`ChartType.Pie`.

### Bisakah saya mengubah properti lain pada bagan?

Ya, Anda dapat mengubah berbagai properti bagan, seperti data, label, dan pemformatan, menggunakan Aspose.Slides for Java API. Lihat dokumentasi untuk lebih jelasnya.

### Apakah Aspose.Slides untuk Java cocok untuk otomatisasi PowerPoint profesional?

Ya, Aspose.Slides for Java adalah perpustakaan canggih untuk mengotomatisasi tugas PowerPoint di aplikasi Java. Ini menyediakan fitur komprehensif untuk bekerja dengan presentasi, slide, bentuk, bagan, dan banyak lagi.

### Bagaimana saya bisa mempelajari lebih lanjut tentang Aspose.Slides untuk Java?

 Anda dapat menemukan dokumentasi dan contoh ekstensif di halaman dokumentasi Aspose.Slides untuk Java[Di Sini](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
