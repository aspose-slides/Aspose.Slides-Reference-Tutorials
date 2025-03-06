---
title: Bagan Tersebar di Slide Java
linktitle: Bagan Tersebar di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat Bagan Sebar di Java menggunakan Aspose.Slides. Panduan langkah demi langkah dengan kode sumber Java untuk visualisasi data dalam presentasi.
weight: 11
url: /id/java/chart-creation/scattered-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengantar Bagan Tersebar di Aspose.Slide untuk Java

Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan Bagan Sebar menggunakan Aspose.Slides untuk Java. Bagan sebar berguna untuk memvisualisasikan titik data pada bidang dua dimensi. Kami akan memberikan petunjuk langkah demi langkah dan menyertakan kode sumber Java untuk kenyamanan Anda.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. [Aspose.Slide untuk Java](https://products.aspose.com/slides/java) dipasang.
2. Lingkungan pengembangan Java telah disiapkan.

## Langkah 1: Inisialisasi Presentasi

Pertama, impor perpustakaan yang diperlukan dan buat presentasi baru.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";

// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Buat presentasi baru
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Slide dan Buat Bagan Sebar

 Selanjutnya, tambahkan slide dan buat diagram sebar di atasnya. Kami akan menggunakan`ScatterWithSmoothLines`ketik bagan dalam contoh ini.

```java
// Dapatkan slide pertama
ISlide slide = pres.getSlides().get_Item(0);

// Membuat diagram sebar
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Langkah 3: Siapkan Data Bagan

Sekarang, mari siapkan data untuk diagram sebar kita. Kami akan menambahkan dua seri, masing-masing dengan beberapa titik data.

```java
// Mendapatkan indeks lembar kerja data bagan default
int defaultWorksheetIndex = 0;

// Mendapatkan lembar kerja data bagan
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Hapus seri demo
chart.getChartData().getSeries().clear();

// Tambahkan seri pertama
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Ambil seri grafik pertama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Tambahkan titik data ke seri pertama
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Edit jenis seri
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Ubah ukuran penanda
series.getMarker().setSymbol(MarkerStyleType.Star); // Ubah simbol penanda

// Ambil seri grafik kedua
series = chart.getChartData().getSeries().get_Item(1);

// Tambahkan titik data ke seri kedua
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Ubah gaya penanda untuk seri kedua
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Langkah 4: Simpan Presentasi

Terakhir, simpan presentasi dengan diagram sebar ke file PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Itu dia! Anda telah berhasil membuat Bagan Sebar menggunakan Aspose.Slides untuk Java. Anda sekarang dapat menyesuaikan contoh ini lebih lanjut agar sesuai dengan data spesifik dan persyaratan desain Anda.

## Kode Sumber Lengkap Untuk Bagan Tersebar di Slide Java
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//Membuat bagan default
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Mendapatkan indeks lembar kerja data bagan default
int defaultWorksheetIndex = 0;
// Mendapatkan lembar kerja data bagan
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Hapus seri demo
chart.getChartData().getSeries().clear();
// Tambahkan seri baru
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Ambil seri grafik pertama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Tambahkan poin baru (1:3) di sana.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Tambahkan poin baru (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Edit jenis seri
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Mengubah penanda rangkaian grafik
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Ambil seri grafik kedua
series = chart.getChartData().getSeries().get_Item(1);
// Tambahkan poin baru (5:2) di sana.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Tambahkan poin baru (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Tambahkan poin baru (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Tambahkan poin baru (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Mengubah penanda rangkaian grafik
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Dalam tutorial ini, kami telah memandu Anda melalui proses pembuatan Bagan Sebar menggunakan Aspose.Slides untuk Java. Bagan sebar adalah alat yang ampuh untuk memvisualisasikan titik data dalam ruang dua dimensi, sehingga memudahkan analisis dan pemahaman hubungan data yang kompleks.

## FAQ

### Bagaimana cara mengubah jenis grafik?

 Untuk mengubah jenis bagan, gunakan`setType` metode pada seri bagan dan berikan jenis bagan yang diinginkan. Misalnya,`series.setType(ChartType.Line)` akan mengubah seri menjadi diagram garis.

### Bagaimana cara menyesuaikan ukuran dan gaya penanda?

 Anda dapat mengubah ukuran dan gaya penanda menggunakan`getMarker` metode pada seri dan kemudian mengatur ukuran dan properti simbol. Misalnya:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Jangan ragu untuk menjelajahi opsi penyesuaian lainnya di dokumentasi Aspose.Slides untuk Java.

 Ingatlah untuk mengganti`"Your Document Directory"` dengan jalur sebenarnya tempat Anda ingin menyimpan presentasi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
