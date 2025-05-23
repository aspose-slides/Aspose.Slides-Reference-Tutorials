---
"description": "Buat Bagan Donat dengan Ukuran Lubang Kustom di Java Slides menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber untuk kustomisasi bagan."
"linktitle": "Lubang Bagan Donat di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Lubang Bagan Donat di Slide Java"
"url": "/id/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lubang Bagan Donat di Slide Java


## Pengenalan Bagan Donat dengan Lubang di Slide Java

Dalam tutorial ini, kami akan memandu Anda membuat diagram donat berlubang menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah ini akan memandu Anda melalui proses tersebut dengan contoh kode sumber.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal dan mengatur pustaka Aspose.Slides for Java di proyek Java Anda. Anda dapat mengunduhnya dari [Dokumentasi Aspose.Slides untuk Java](https://reference.aspose.com/slides/java/).

## Langkah 1: Impor Pustaka yang Diperlukan

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
    // Buat diagram donat pada slide pertama
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Mengatur ukuran lubang pada diagram donat (dalam persentase)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Simpan presentasi ke disk
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Buang objek presentasi
    if (presentation != null) presentation.dispose();
}
```

## Langkah 4: Jalankan Kode

Jalankan kode Java di IDE atau editor teks Anda untuk membuat diagram donat dengan ukuran lubang tertentu. Pastikan untuk mengganti `"Your Document Directory"` dengan jalur sebenarnya tempat Anda ingin menyimpan presentasi.

## Source Code Lengkap Untuk Lubang Bagan Donat di Java Slides

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

Dalam tutorial ini, Anda mempelajari cara membuat bagan donat berlubang menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan ukuran lubang dengan menyesuaikan `setDoughnutHoleSize` parameter metode.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah warna segmen bagan?

Untuk mengubah warna segmen grafik, Anda dapat menggunakan `setDataPointsInLegend` metode pada `IChart` objek dan mengatur warna yang diinginkan untuk setiap titik data.

### Dapatkah saya menambahkan label ke segmen diagram donat?

Ya, Anda dapat menambahkan label ke segmen diagram donat menggunakan `setDataPointsLabelValue` metode pada `IChart` obyek.

### Apakah mungkin untuk menambahkan judul pada bagan?

Tentu saja! Anda dapat menambahkan judul ke grafik menggunakan `setTitle` metode pada `IChart` objek dan memberikan teks judul yang diinginkan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}