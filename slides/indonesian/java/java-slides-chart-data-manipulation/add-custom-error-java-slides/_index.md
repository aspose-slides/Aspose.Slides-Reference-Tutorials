---
"description": "Pelajari cara menambahkan bilah kesalahan khusus ke bagan PowerPoint di Java Slides menggunakan Aspose.Slides. Panduan langkah demi langkah dengan kode sumber untuk visualisasi data yang akurat."
"linktitle": "Menambahkan Kesalahan Kustom di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Menambahkan Kesalahan Kustom di Slide Java"
"url": "/id/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Kesalahan Kustom di Slide Java


## Pengantar Menambahkan Bar Kesalahan Kustom di Slide Java menggunakan Aspose.Slides

Dalam tutorial ini, Anda akan mempelajari cara menambahkan bilah kesalahan khusus ke bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Bilah kesalahan berguna untuk menampilkan variabilitas atau ketidakpastian dalam titik data pada bagan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Aspose.Slides untuk pustaka Java terinstal dan dikonfigurasi dalam proyek Anda.
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

Berikutnya, kita akan menambahkan diagram gelembung ke presentasi.

```java
// Membuat diagram gelembung
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Langkah 3: Tambahkan Bilah Kesalahan Kustom

Sekarang, mari tambahkan batang kesalahan khusus ke rangkaian grafik.

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

## Langkah 4: Mengatur Data Batang Kesalahan

Pada langkah ini, kita akan mengakses titik data rangkaian grafik dan menetapkan nilai batang kesalahan khusus untuk setiap titik.

```java
// Mengakses titik data seri grafik dan menetapkan nilai batang kesalahan untuk titik individual
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Menetapkan batang kesalahan untuk titik seri grafik
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

Selesai! Anda telah berhasil menambahkan bilah kesalahan khusus ke bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java.

## Source Code Lengkap Untuk Menambahkan Custom Error di Java Slides

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
	// Mengakses titik data seri grafik dan menetapkan nilai batang kesalahan untuk setiap titik
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Menetapkan batang kesalahan untuk titik seri grafik
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

Dalam tutorial lengkap ini, Anda telah mempelajari cara menyempurnakan presentasi PowerPoint dengan menambahkan bilah kesalahan khusus ke bagan menggunakan Aspose.Slides untuk Java. Bilah kesalahan memberikan wawasan berharga tentang variabilitas dan ketidakpastian data, sehingga membuat bagan Anda lebih informatif dan menarik secara visual.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menyesuaikan tampilan bilah kesalahan?

Anda dapat menyesuaikan tampilan bilah kesalahan dengan memodifikasi properti `IErrorBarsFormat` objek, seperti gaya garis, warna garis, dan lebar bilah kesalahan.

### Bisakah saya menambahkan batang kesalahan ke jenis bagan lainnya?

Ya, Anda dapat menambahkan batang kesalahan ke berbagai jenis bagan yang didukung oleh Aspose.Slides untuk Java, termasuk bagan batang, bagan garis, dan bagan sebar.

### Bagaimana cara menetapkan nilai bilah kesalahan yang berbeda untuk setiap titik data?

Anda dapat melakukan pengulangan melalui titik-titik data dan menetapkan nilai batang kesalahan khusus untuk setiap titik, seperti ditunjukkan dalam kode di atas.

### Apakah mungkin untuk menyembunyikan bilah kesalahan untuk titik data tertentu?

Ya, Anda dapat mengontrol visibilitas bilah kesalahan untuk titik data individual dengan mengatur `setVisible` milik `IErrorBarsFormat` obyek.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}