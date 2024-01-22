---
title: Tambahkan Kesalahan Khusus di Slide Java
linktitle: Tambahkan Kesalahan Khusus di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menambahkan bilah kesalahan khusus ke bagan PowerPoint di Java Slides menggunakan Aspose.Slides. Panduan langkah demi langkah dengan kode sumber untuk visualisasi data yang tepat.
type: docs
weight: 11
url: /id/java/chart-data-manipulation/add-custom-error-java-slides/
---

## Pengantar Menambahkan Bilah Kesalahan Kustom di Slide Java menggunakan Aspose.Slides

Dalam tutorial ini, Anda akan mempelajari cara menambahkan bilah kesalahan khusus ke bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Bilah kesalahan berguna untuk menampilkan variabilitas atau ketidakpastian titik data pada grafik.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Aspose.Slides untuk perpustakaan Java diinstal dan dikonfigurasi di proyek Anda.
- Lingkungan pengembangan Java telah disiapkan.

## Langkah 1: Buat Presentasi Kosong

Pertama, buat presentasi PowerPoint kosong.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Membuat presentasi kosong
Presentation presentation = new Presentation();
```

## Langkah 2: Tambahkan Bagan Gelembung

Selanjutnya, kita akan menambahkan diagram gelembung ke presentasi.

```java
// Membuat diagram gelembung
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Langkah 3: Tambahkan Bilah Kesalahan Khusus

Sekarang, mari tambahkan bilah kesalahan khusus ke rangkaian bagan.

```java
// Menambahkan bilah Kesalahan khusus dan mengatur formatnya
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Langkah 4: Tetapkan Data Bilah Kesalahan

Pada langkah ini, kita akan mengakses titik data rangkaian bagan dan menetapkan nilai bilah kesalahan khusus untuk setiap titik.

```java
// Mengakses titik data rangkaian bagan dan mengatur nilai bilah kesalahan untuk masing-masing titik
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Menetapkan bilah kesalahan untuk titik rangkaian bagan
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Langkah 5: Simpan Presentasi

Terakhir, simpan presentasi dengan bilah kesalahan khusus.

```java
// Menyimpan presentasi
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Itu dia! Anda telah berhasil menambahkan bilah kesalahan khusus ke bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java.

## Kode Sumber Lengkap Untuk Menambahkan Kesalahan Kustom di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Membuat presentasi kosong
Presentation presentation = new Presentation();
try
{
	// Membuat diagram gelembung
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Menambahkan bilah Kesalahan khusus dan mengatur formatnya
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Mengakses titik data seri bagan dan mengatur nilai bilah kesalahan untuk masing-masing titik
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Menetapkan bilah kesalahan untuk titik rangkaian bagan
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Menyimpan presentasi
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Dalam tutorial komprehensif ini, Anda telah mempelajari cara menyempurnakan presentasi PowerPoint Anda dengan menambahkan bilah kesalahan khusus ke bagan menggunakan Aspose.Slides untuk Java. Bilah kesalahan memberikan wawasan berharga mengenai variabilitas dan ketidakpastian data, menjadikan diagram Anda lebih informatif dan menarik secara visual.

## FAQ

### Bagaimana cara menyesuaikan tampilan bilah kesalahan?

 Anda dapat menyesuaikan tampilan bilah kesalahan dengan memodifikasi properti`IErrorBarsFormat` objek, seperti gaya garis, warna garis, dan lebar bilah kesalahan.

### Bisakah saya menambahkan bilah kesalahan ke jenis bagan lainnya?

Ya, Anda dapat menambahkan bilah kesalahan ke berbagai tipe bagan yang didukung oleh Aspose.Slides untuk Java, termasuk bagan batang, bagan garis, dan bagan sebar.

### Bagaimana cara menetapkan nilai bilah kesalahan yang berbeda untuk setiap titik data?

Anda dapat mengulang titik data dan menetapkan nilai bilah kesalahan khusus untuk setiap titik, seperti yang ditunjukkan pada kode di atas.

### Apakah mungkin menyembunyikan bilah kesalahan untuk titik data tertentu?

 Ya, Anda dapat mengontrol visibilitas bilah kesalahan untuk masing-masing titik data dengan mengatur`setVisible` properti dari`IErrorBarsFormat` obyek.