---
title: Sembunyikan Informasi dari Bagan di Slide Java
linktitle: Sembunyikan Informasi dari Bagan di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menyembunyikan elemen bagan di Java Slides dengan Aspose.Slides for Java. Sesuaikan presentasi untuk kejelasan dan estetika dengan panduan langkah demi langkah dan kode sumber.
weight: 13
url: /id/java/customization-and-formatting/hide-information-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Pengantar Menyembunyikan Informasi dari Bagan di Slide Java

Dalam tutorial ini, kita akan mempelajari cara menyembunyikan berbagai elemen dari bagan di Java Slides menggunakan Aspose.Slides for Java API. Anda dapat menggunakan kode ini untuk menyesuaikan bagan sesuai kebutuhan presentasi Anda.

## Langkah 1: Menyiapkan Lingkungan

 Sebelum kita mulai, pastikan Anda telah menambahkan pustaka Aspose.Slides untuk Java ke proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 2: Buat Presentasi Baru

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 3: Menambahkan Bagan ke Slide

Kita akan menambahkan diagram garis dengan penanda ke slide dan kemudian melanjutkan untuk menyembunyikan berbagai elemen diagram.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Langkah 4: Sembunyikan Judul Bagan

Anda dapat menyembunyikan judul grafik sebagai berikut:

```java
chart.setTitle(false);
```

## Langkah 5: Sembunyikan Sumbu Nilai

Untuk menyembunyikan sumbu nilai (sumbu vertikal), gunakan kode berikut:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Langkah 6: Sembunyikan Sumbu Kategori

Untuk menyembunyikan sumbu kategori (sumbu horizontal), gunakan kode ini:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Langkah 7: Sembunyikan Legenda

Anda dapat menyembunyikan legenda grafik seperti ini:

```java
chart.setLegend(false);
```

## Langkah 8: Sembunyikan Garis Kisi Utama

Untuk menyembunyikan garis grid utama pada sumbu horizontal, Anda dapat menggunakan kode berikut:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Langkah 9: Hapus Seri

Jika Anda ingin menghapus semua rangkaian dari grafik, Anda dapat menggunakan perulangan seperti ini:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Langkah 10: Sesuaikan Seri Bagan

Anda dapat menyesuaikan rangkaian bagan sesuai kebutuhan. Dalam contoh ini, kita mengubah gaya penanda, posisi label data, ukuran penanda, warna garis, dan gaya tanda hubung:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## Langkah 11: Simpan Presentasi

Terakhir, simpan presentasi ke file:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

Itu dia! Anda telah berhasil menyembunyikan berbagai elemen dari bagan di Java Slides menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan lebih lanjut bagan dan presentasi sesuai kebutuhan untuk kebutuhan spesifik Anda.

## Kode Sumber Lengkap Untuk Menyembunyikan Informasi dari Bagan di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Menyembunyikan Judul bagan
	chart.setTitle(false);
	///Menyembunyikan sumbu Nilai
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Visibilitas Sumbu Kategori
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Menyembunyikan Legenda
	chart.setLegend(false);
	//Menyembunyikan Garis MajorGrid
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//Mengatur warna garis seri
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## Kesimpulan

Dalam panduan langkah demi langkah ini, kita telah menjelajahi cara menyembunyikan berbagai elemen dari bagan di Java Slides menggunakan Aspose.Slides for Java API. Ini bisa sangat berguna ketika Anda perlu menyesuaikan bagan untuk presentasi dan membuatnya lebih menarik secara visual atau disesuaikan dengan kebutuhan spesifik Anda.

## FAQ

### Bagaimana cara menyesuaikan tampilan elemen bagan lebih lanjut?

Anda dapat menyesuaikan berbagai properti elemen bagan seperti warna garis, warna isian, gaya penanda, dan lainnya dengan mengakses properti yang sesuai dari rangkaian bagan, penanda, label, dan format.

### Bisakah saya menyembunyikan titik data tertentu di bagan?

Ya, Anda dapat menyembunyikan titik data tertentu dengan memanipulasi data dalam rangkaian bagan. Anda dapat menghapus titik data atau mengatur nilainya menjadi null untuk menyembunyikannya.

### Bagaimana cara menambahkan seri tambahan ke grafik?

 Anda dapat menambahkan lebih banyak rangkaian ke bagan dengan menggunakan`IChartData.getSeries().add` metode dan menentukan titik data untuk seri baru.

### Apakah mungkin mengubah tipe grafik secara dinamis?

Ya, Anda dapat mengubah tipe bagan secara dinamis dengan membuat bagan baru dari tipe yang diinginkan dan menyalin data dari bagan lama ke bagan baru.

### Bagaimana cara mengubah judul bagan dan label sumbu secara terprogram?

Anda dapat mengatur judul dan label bagan dan sumbu dengan mengakses properti masing-masing dan mengatur teks dan format yang diinginkan.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
