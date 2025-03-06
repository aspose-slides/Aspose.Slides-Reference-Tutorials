---
title: Mengatur Warna Irisan Diagram Lingkaran Otomatis di Slide Java
linktitle: Mengatur Warna Irisan Diagram Lingkaran Otomatis di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat diagram lingkaran dinamis dengan warna irisan otomatis dalam presentasi Java PowerPoint menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber.
weight: 24
url: /id/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Pengantar Pengaturan Warna Irisan Diagram Lingkaran Otomatis di Slide Java

Dalam tutorial ini, kita akan mempelajari cara membuat diagram lingkaran dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java dan mengatur warna irisan otomatis untuk diagram. Kami akan memberikan panduan langkah demi langkah beserta kode sumbernya.

## Prasyarat

 Sebelum memulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda. Anda dapat mengunduh perpustakaan dari situs web Aspose:[Unduh Aspose.Slide untuk Java](https://releases.aspose.com/slides/java/).

## Langkah 1: Impor Paket yang Diperlukan

Pertama, Anda perlu mengimpor paket yang diperlukan dari Aspose.Slides untuk Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Langkah 2: Buat Presentasi PowerPoint

 Buat instance`Presentation` kelas untuk membuat presentasi PowerPoint baru:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Langkah 3: Tambahkan Slide

Akses slide pertama presentasi dan tambahkan bagan ke dalamnya dengan data default:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Langkah 4: Tetapkan Judul Bagan

Tetapkan judul untuk bagan:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Langkah 5: Konfigurasikan Data Bagan

Atur bagan agar memperlihatkan nilai untuk rangkaian pertama dan konfigurasikan data bagan:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Langkah 6: Tambahkan Kategori dan Seri

Tambahkan kategori dan rangkaian baru ke bagan:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Langkah 7: Isi Data Seri

Isi data seri untuk diagram lingkaran:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Langkah 8: Aktifkan Warna Irisan Bervariasi

Aktifkan beragam warna irisan untuk diagram lingkaran:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Langkah 9: Simpan Presentasi

Terakhir, simpan presentasi ke file PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Kode Sumber Lengkap Untuk Mengatur Warna Irisan Diagram Lingkaran Otomatis di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi yang mewakili file PPTX
Presentation presentation = new Presentation();
try
{
	// Akses slide pertama
	ISlide slides = presentation.getSlides().get_Item(0);
	// Tambahkan bagan dengan data default
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Judul bagan pengaturan
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Setel seri pertama ke Tampilkan Nilai
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Mengatur indeks lembar data grafik
	int defaultWorksheetIndex = 0;
	// Mendapatkan lembar kerja data bagan
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Hapus seri dan kategori yang dihasilkan secara default
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Menambahkan kategori baru
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Menambahkan seri baru
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Sekarang mengisi data seri
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Anda telah berhasil membuat diagram lingkaran dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java dan mengonfigurasinya agar memiliki warna irisan otomatis. Panduan langkah demi langkah ini memberi Anda kode sumber yang diperlukan untuk mencapai hal ini. Anda dapat menyesuaikan lebih lanjut bagan dan presentasi sesuai kebutuhan.

## FAQ

### Bagaimana cara menyesuaikan warna masing-masing irisan dalam diagram lingkaran?

 Untuk menyesuaikan warna masing-masing irisan dalam diagram lingkaran, Anda dapat menggunakan`getAutomaticSeriesColors` metode untuk mengambil skema warna default dan kemudian memodifikasi warna sesuai kebutuhan. Berikut ini contohnya:

```java
//Dapatkan skema warna default
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Ubah warna sesuai kebutuhan
colors.get_Item(0).setColor(Color.RED); // Atur warna irisan pertama menjadi merah
colors.get_Item(1).setColor(Color.BLUE); // Atur warna irisan kedua menjadi biru
// Tambahkan lebih banyak modifikasi warna sesuai kebutuhan
```

### Bagaimana cara menambahkan legenda ke diagram lingkaran?

 Untuk menambahkan legenda ke diagram lingkaran, Anda dapat menggunakan`getLegend` metode dan konfigurasikan sebagai berikut:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Tetapkan posisi legenda
legend.setOverlay(true); // Tampilkan legenda di atas grafik
```

### Bisakah saya mengubah font dan gaya judul?

Ya, Anda dapat mengubah font dan gaya judul. Gunakan kode berikut untuk mengatur font dan gaya judul:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Atur ukuran font
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Buatlah judul menjadi tebal
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Buatlah judul menjadi miring
```

Anda dapat menyesuaikan ukuran font, ketebalan, dan gaya miring sesuai kebutuhan.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
