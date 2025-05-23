---
"description": "Pelajari cara membuat diagram pai dinamis dengan warna irisan otomatis dalam presentasi PowerPoint Java menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber."
"linktitle": "Mengatur Warna Potongan Diagram Pai Otomatis di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Warna Potongan Diagram Pai Otomatis di Java Slides"
"url": "/id/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Warna Potongan Diagram Pai Otomatis di Java Slides


## Pengantar Pengaturan Warna Irisan Diagram Pai Otomatis di Java Slides

Dalam tutorial ini, kita akan mempelajari cara membuat diagram pai dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java dan mengatur warna irisan otomatis untuk diagram tersebut. Kami akan memberikan panduan langkah demi langkah beserta kode sumbernya.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides for Java di proyek Java Anda. Anda dapat mengunduh pustaka tersebut dari situs web Aspose: [Unduh Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/).

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

Membuat contoh `Presentation` kelas untuk membuat presentasi PowerPoint baru:

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

Atur bagan untuk menampilkan nilai untuk seri pertama dan konfigurasikan data bagan:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Langkah 6: Tambahkan Kategori dan Seri

Tambahkan kategori dan seri baru ke bagan:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Langkah 7: Mengisi Data Seri

Isi data seri untuk diagram lingkaran:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Langkah 8: Aktifkan Warna Irisan Beragam

Aktifkan warna irisan bervariasi untuk diagram pai:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Langkah 9: Simpan Presentasi

Terakhir, simpan presentasi ke file PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Source Code Lengkap Untuk Mengatur Warna Irisan Pie Chart Secara Otomatis di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Membuat instance kelas Presentasi yang merepresentasikan file PPTX
Presentation presentation = new Presentation();
try
{
	// Akses slide pertama
	ISlide slides = presentation.getSlides().get_Item(0);
	// Tambahkan bagan dengan data default
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Mengatur Judul Bagan
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Tetapkan seri pertama untuk Menampilkan Nilai
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Mengatur indeks lembar data grafik
	int defaultWorksheetIndex = 0;
	// Mendapatkan lembar kerja data grafik
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

Anda telah berhasil membuat diagram pai dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java dan mengonfigurasinya agar memiliki warna irisan otomatis. Panduan langkah demi langkah ini menyediakan kode sumber yang diperlukan untuk mencapainya. Anda dapat menyesuaikan diagram dan presentasi lebih lanjut sesuai kebutuhan.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menyesuaikan warna tiap irisan pada diagram lingkaran?

Untuk menyesuaikan warna setiap irisan pada diagram lingkaran, Anda dapat menggunakan `getAutomaticSeriesColors` metode untuk mengambil skema warna default dan kemudian mengubah warna sesuai kebutuhan. Berikut contohnya:

```java
// Dapatkan skema warna default
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Ubah warna sesuai kebutuhan
colors.get_Item(0).setColor(Color.RED); // Atur warna irisan pertama menjadi merah
colors.get_Item(1).setColor(Color.BLUE); // Atur warna irisan kedua menjadi biru
// Tambahkan lebih banyak modifikasi warna sesuai kebutuhan
```

### Bagaimana cara menambahkan legenda ke diagram lingkaran?

Untuk menambahkan legenda ke diagram lingkaran, Anda dapat menggunakan `getLegend` metode dan konfigurasikan sebagai berikut:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Mengatur posisi legenda
legend.setOverlay(true); // Menampilkan legenda di atas grafik
```

### Bisakah saya mengubah font dan gaya judul?

Ya, Anda dapat mengubah font dan gaya judul. Gunakan kode berikut untuk mengatur font dan gaya judul:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Mengatur ukuran font
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Buat judulnya tebal
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Buat judulnya miring
```

Anda dapat menyesuaikan ukuran font, ketebalan, dan gaya miring sesuai kebutuhan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}