---
title: Dapatkan Nilai dan Skala Unit dari Axis di Java Slides
linktitle: Dapatkan Nilai dan Skala Unit dari Axis di Java Slides
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mendapatkan nilai dan skala satuan dari sumbu di Java Slides menggunakan Aspose.Slides untuk Java. Tingkatkan kemampuan analisis data Anda.
weight: 20
url: /id/java/data-manipulation/get-values-unit-scale-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengantar Mendapatkan Nilai dan Skala Unit dari Axis di Slide Java

Dalam tutorial ini, kita akan menjelajahi cara mengambil nilai dan skala unit dari sumbu di Java Slides menggunakan Aspose.Slides for Java API. Baik Anda sedang mengerjakan proyek visualisasi data atau perlu menganalisis data bagan di aplikasi Java Anda, memahami cara mengakses nilai sumbu sangatlah penting. Kami akan memandu Anda melalui proses langkah demi langkah, memberikan contoh kode di sepanjang prosesnya.

## Prasyarat

Sebelum kita mendalami kodenya, pastikan Anda memiliki prasyarat berikut:

1. Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java di sistem Anda dan memahami konsep pemrograman Java.

2.  Aspose.Slides for Java: Unduh dan instal pustaka Aspose.Slides for Java dari[tautan unduhan](https://releases.aspose.com/slides/java/).

## Langkah 1: Membuat Presentasi

Untuk memulai, mari buat presentasi baru menggunakan Aspose.Slides untuk Java:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 Mengganti`"Your Document Directory"` dengan jalur ke direktori tempat Anda ingin menyimpan presentasi.

## Langkah 2: Menambahkan Bagan

Selanjutnya, kita akan menambahkan bagan ke presentasi. Dalam contoh ini, kita akan membuat diagram area:

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 100, 100, 500, 350);
chart.validateChartLayout();
```

Kami telah menambahkan bagan area ke slide pertama presentasi. Anda dapat menyesuaikan jenis dan posisi grafik sesuai kebutuhan.

## Langkah 3: Mengambil Nilai Sumbu Vertikal

Sekarang, mari kita ambil nilai dari sumbu vertikal diagram:

```java
double maxValue = chart.getAxes().getVerticalAxis().getActualMaxValue();
double minValue = chart.getAxes().getVerticalAxis().getActualMinValue();
```

Di sini, kita memperoleh nilai maksimum dan minimum dari sumbu vertikal. Nilai-nilai ini dapat berguna untuk berbagai tugas analisis data.

## Langkah 4: Mengambil Nilai Sumbu Horizontal

Demikian pula, kita dapat mengambil nilai dari sumbu horizontal:

```java
double majorUnit = chart.getAxes().getHorizontalAxis().getActualMajorUnit();
double minorUnit = chart.getAxes().getHorizontalAxis().getActualMinorUnit();
```

 Itu`majorUnit` Dan`minorUnit` nilai masing-masing mewakili unit mayor dan minor pada sumbu horizontal.

## Langkah 5: Menyimpan Presentasi

Setelah kita mengambil nilai sumbu, kita dapat menyimpan presentasi:

```java
pres.save(dataDir + "ChartValues.pptx", SaveFormat.Pptx);
```

Kode ini menyimpan presentasi dengan nilai sumbu yang diambil ke file PowerPoint.

## Kode Sumber Lengkap Untuk Mendapatkan Nilai dan Skala Unit dari Axis di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 100, 100, 500, 350);
	chart.validateChartLayout();
	double maxValue = chart.getAxes().getVerticalAxis().getActualMaxValue();
	double minValue = chart.getAxes().getVerticalAxis().getActualMinValue();
	double majorUnit = chart.getAxes().getHorizontalAxis().getActualMajorUnit();
	double minorUnit = chart.getAxes().getHorizontalAxis().getActualMinorUnit();
	// Menyimpan presentasi
	pres.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi cara mendapatkan nilai dan skala unit dari sumbu di Java Slides menggunakan Aspose.Slides untuk Java. Ini bisa sangat berharga ketika bekerja dengan grafik dan menganalisis data dalam aplikasi Java Anda. Aspose.Slides untuk Java menyediakan alat yang Anda perlukan untuk bekerja dengan presentasi secara terprogram, memberi Anda kendali atas data bagan dan banyak lagi.

## FAQ

### Bagaimana cara menyesuaikan tipe bagan di Aspose.Slides untuk Java?

 Untuk menyesuaikan jenis bagan, cukup ganti`ChartType.Area` dengan tipe bagan yang diinginkan saat menambahkan bagan ke presentasi Anda.

### Bisakah saya mengubah tampilan label sumbu bagan?

Ya, Anda dapat menyesuaikan tampilan label sumbu bagan menggunakan Aspose.Slides untuk Java. Lihat dokumentasi untuk panduan rinci.

### Apakah Aspose.Slides for Java kompatibel dengan versi Java terbaru?

Aspose.Slides untuk Java diperbarui secara berkala untuk mendukung versi Java terbaru, memastikan kompatibilitas dengan perkembangan Java terbaru.

### Bisakah saya menggunakan Aspose.Slides untuk Java dalam proyek komersial?

Ya, Anda dapat menggunakan Aspose.Slides untuk Java dalam proyek komersial. Ia menawarkan opsi lisensi untuk memenuhi berbagai kebutuhan proyek.

### Di mana saya dapat menemukan lebih banyak sumber daya dan dokumentasi untuk Aspose.Slides untuk Java?

 Anda dapat menemukan dokumentasi komprehensif dan sumber daya tambahan di[Aspose.Slides untuk dokumentasi Java](https://reference.aspose.com/slides/java/) situs web.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
