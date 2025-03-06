---
title: Validasi Tata Letak Bagan yang Ditambahkan di Slide Java
linktitle: Validasi Tata Letak Bagan yang Ditambahkan di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Validasi tata letak bagan utama di PowerPoint dengan Aspose.Slides untuk Java. Belajar memanipulasi bagan secara terprogram untuk presentasi yang menakjubkan.
weight: 10
url: /id/java/data-manipulation/validate-chart-layout-added-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengantar Memvalidasi Tata Letak Bagan di Aspose.Slides untuk Java

Dalam tutorial ini, kita akan mempelajari cara memvalidasi tata letak bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Pustaka ini memungkinkan Anda bekerja dengan presentasi PowerPoint secara terprogram, sehingga memudahkan untuk memanipulasi dan memvalidasi berbagai elemen, termasuk bagan.

## Langkah 1: Menginisialisasi Presentasi

 Pertama, kita perlu menginisialisasi objek presentasi dan memuat presentasi PowerPoint yang ada. Mengganti`"Your Document Directory"` dengan jalur sebenarnya ke file presentasi Anda (`test.pptx` dalam contoh ini).

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Langkah 2: Menambahkan Bagan

 Selanjutnya, kita akan menambahkan bagan ke presentasi. Dalam contoh ini, kami menambahkan bagan kolom berkerumun, namun Anda dapat mengubahnya`ChartType` sesuai kebutuhan.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## Langkah 3: Memvalidasi Tata Letak Bagan

 Sekarang, kita akan memvalidasi tata letak grafik menggunakan`validateChartLayout()` metode. Hal ini memastikan bahwa grafik ditata dengan benar dalam slide.

```java
chart.validateChartLayout();
```

## Langkah 4: Mengambil Posisi dan Ukuran Bagan

Setelah memvalidasi tata letak bagan, Anda mungkin ingin mengambil informasi tentang posisi dan ukurannya. Kita bisa mendapatkan koordinat X dan Y sebenarnya, serta lebar dan tinggi area plot grafik.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## Langkah 5: Menyimpan Presentasi

 Terakhir, jangan lupa untuk menyimpan presentasi yang telah dimodifikasi. Dalam contoh ini, kami menyimpannya sebagai`Result.pptx`, namun Anda dapat menentukan nama file lain jika diperlukan.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Kode Sumber Lengkap Untuk Validasi Tata Letak Bagan yang Ditambahkan di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Menyimpan presentasi
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari dunia bekerja dengan grafik dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Kami membahas langkah-langkah penting untuk memvalidasi tata letak bagan, mengambil posisi dan ukurannya, dan menyimpan presentasi yang dimodifikasi. Berikut rekap singkatnya:

## FAQ

### Bagaimana cara mengubah jenis grafik?

 Untuk mengubah tipe grafik, cukup ganti`ChartType.ClusteredColumn`dengan tipe grafik yang diinginkan di`addChart()` metode.

### Bisakah saya menyesuaikan data grafik?

Ya, Anda dapat menyesuaikan data bagan dengan menambahkan dan mengubah seri data, kategori, dan nilai. Lihat dokumentasi Aspose.Slides untuk detail selengkapnya.

### Bagaimana jika saya ingin mengubah properti grafik lainnya?

Anda dapat mengakses berbagai properti bagan dan menyesuaikannya sesuai kebutuhan Anda. Jelajahi dokumentasi Aspose.Slides untuk informasi komprehensif tentang manipulasi grafik.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
