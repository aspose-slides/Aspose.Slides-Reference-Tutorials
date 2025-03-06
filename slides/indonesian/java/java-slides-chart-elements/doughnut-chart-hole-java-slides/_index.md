---
title: Lubang Bagan Donat di Slide Java
linktitle: Lubang Bagan Donat di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Buat Bagan Donat dengan Ukuran Lubang Khusus di Slide Java menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber untuk penyesuaian bagan.
weight: 11
url: /id/java/chart-elements/doughnut-chart-hole-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lubang Bagan Donat di Slide Java


## Pengantar Bagan Donat Berlubang di Slide Java

Dalam tutorial ini, kami akan memandu Anda dalam membuat bagan donat berlubang menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah ini akan memandu Anda melalui proses dengan contoh kode sumber.

## Prasyarat

 Sebelum memulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda. Anda dapat mengunduhnya dari[Aspose.Slides untuk dokumentasi Java](https://reference.aspose.com/slides/java/).

## Langkah 1: Impor Perpustakaan yang Diperlukan

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Langkah 2: Inisialisasi Presentasi

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";

// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
```

## Langkah 3: Buat Bagan Donat

```java
try {
    // Buat bagan donat di slide pertama
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Atur ukuran lubang pada grafik donat (dalam persentase)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Simpan presentasi ke disk
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Buang objek presentasi
    if (presentation != null) presentation.dispose();
}
```

## Langkah 4: Jalankan Kode

 Jalankan kode Java di IDE atau editor teks Anda untuk membuat bagan donat dengan ukuran lubang tertentu. Pastikan untuk mengganti`"Your Document Directory"` dengan jalur sebenarnya tempat Anda ingin menyimpan presentasi.

## Kode Sumber Lengkap Untuk Lubang Bagan Donat di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Tulis presentasi ke disk
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

 Dalam tutorial ini, Anda mempelajari cara membuat bagan donat berlubang menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan ukuran lubang dengan menyesuaikannya`setDoughnutHoleSize` parameter metode.

## FAQ

### Bagaimana cara mengubah warna segmen bagan?

 Untuk mengubah warna segmen bagan, Anda dapat menggunakan`setDataPointsInLegend` metode pada`IChart` objek dan atur warna yang diinginkan untuk setiap titik data.

### Bisakah saya menambahkan label ke segmen bagan donat?

 Ya, Anda dapat menambahkan label ke segmen bagan donat menggunakan`setDataPointsLabelValue` metode pada`IChart` obyek.

### Apakah mungkin untuk menambahkan judul pada grafik?

 Tentu! Anda dapat menambahkan judul ke bagan menggunakan`setTitle` metode pada`IChart` objek dan memberikan judul teks yang diinginkan.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
