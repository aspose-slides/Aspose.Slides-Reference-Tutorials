---
"description": "Pelajari cara membuat dan menyesuaikan grafik Java Slides dengan Aspose.Slides. Sempurnakan presentasi Anda dengan entitas grafik yang canggih."
"linktitle": "Entitas Bagan dalam Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Entitas Bagan dalam Slide Java"
"url": "/id/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Entitas Bagan dalam Slide Java


## Pengenalan Entitas Bagan di Slide Java

Bagan merupakan alat yang ampuh untuk memvisualisasikan data dalam presentasi. Baik Anda membuat laporan bisnis, presentasi akademis, atau bentuk konten lainnya, bagan membantu menyampaikan informasi secara efektif. Aspose.Slides untuk Java menyediakan fitur-fitur yang tangguh untuk bekerja dengan bagan, menjadikannya pilihan utama bagi pengembang Java.

## Prasyarat

Sebelum kita menyelami dunia entitas grafik, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) terinstal
- Pustaka Aspose.Slides untuk Java diunduh dan ditambahkan ke proyek Anda
- Pengetahuan dasar tentang pemrograman Java

Sekarang, mari kita mulai membuat dan menyesuaikan bagan menggunakan Aspose.Slides untuk Java.

## Langkah 1: Membuat Presentasi

Langkah pertama adalah membuat presentasi baru tempat Anda akan menambahkan bagan. Berikut ini cuplikan kode untuk membuat presentasi:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 2: Menambahkan Bagan

Setelah presentasi Anda siap, saatnya menambahkan diagram. Dalam contoh ini, kita akan menambahkan diagram garis sederhana dengan penanda. Berikut cara melakukannya:

```java
// Mengakses slide pertama
ISlide slide = pres.getSlides().get_Item(0);

// Menambahkan bagan contoh
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Langkah 3: Menyesuaikan Judul Bagan

Bagan yang terdefinisi dengan baik harus memiliki judul. Mari kita tetapkan judul untuk bagan kita:

```java
// Menetapkan Judul Bagan
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Langkah 4: Memformat Garis Grid

Anda dapat memformat garis kisi mayor dan minor pada bagan Anda. Mari kita atur beberapa format untuk garis kisi sumbu vertikal:

```java
// Mengatur format garis kisi utama untuk sumbu nilai
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Mengatur format garis grid minor untuk sumbu nilai
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Langkah 5: Menyesuaikan Sumbu Nilai

Anda memiliki kendali atas format angka, nilai maksimum, dan minimum dari sumbu nilai. Berikut cara menyesuaikannya:

```java
// Mengatur format angka sumbu nilai
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Mengatur nilai maksimum dan minimum grafik
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Langkah 6: Menambahkan Judul Sumbu Nilai

Untuk membuat bagan Anda lebih informatif, Anda dapat menambahkan judul ke sumbu nilai:

```java
// Mengatur judul sumbu nilai
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Langkah 7: Memformat Sumbu Kategori

Sumbu kategori, yang biasanya mewakili kategori data, juga dapat disesuaikan:

```java
// Mengatur format garis kisi utama untuk sumbu Kategori
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Mengatur format garis grid Minor untuk sumbu Kategori
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Langkah 8: Menambahkan Legenda

Legenda membantu menjelaskan rangkaian data dalam bagan Anda. Mari kita sesuaikan legenda:

```java
// Mengatur Properti Teks Legenda
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Mengatur legenda grafik pertunjukan tanpa grafik yang tumpang tindih
chart.getLegend().setOverlay(true);
```

## Langkah 9: Menyimpan Presentasi

Terakhir, simpan presentasi Anda dengan bagan:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Source Code Lengkap untuk Entitas Bagan di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Membuat presentasi// Membuat presentasi
Presentation pres = new Presentation();
try
{
	// Mengakses slide pertama
	ISlide slide = pres.getSlides().get_Item(0);
	// Menambahkan bagan contoh
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Mengatur Judul Bagan
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Mengatur format garis kisi utama untuk sumbu nilai
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Mengatur format garis grid minor untuk sumbu nilai
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Mengatur format angka sumbu nilai
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Mengatur nilai maksimum dan minimum grafik
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Mengatur Properti Teks Sumbu Nilai
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Mengatur judul sumbu nilai
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Mengatur format garis sumbu nilai: Sekarang Tidak Berlaku
	// grafik.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// grafik.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Warna.Merah;
	// Mengatur format garis kisi utama untuk sumbu Kategori
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Mengatur format garis grid Minor untuk sumbu Kategori
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Mengatur Properti Teks Sumbu Kategori
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Pengaturan Kategori Judul
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Mengatur posisi label sumbu kategori
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Pengaturan kategori sumbu label sudut rotasi
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Mengatur Properti Teks Legenda
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Mengatur legenda grafik pertunjukan tanpa grafik yang tumpang tindih
	chart.getLegend().setOverlay(true);
	// Merencanakan seri pertama pada sumbu nilai sekunder
	// Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = benar;
	// Mengatur warna dinding belakang grafik
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Mengatur warna area plot
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Simpan Presentasi
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam artikel ini, kami telah menjelajahi dunia entitas bagan di Java Slides menggunakan Aspose.Slides untuk Java. Anda telah mempelajari cara membuat, menyesuaikan, dan memanipulasi bagan untuk menyempurnakan presentasi Anda. Bagan tidak hanya membuat data Anda menarik secara visual tetapi juga membantu audiens Anda memahami informasi yang kompleks dengan lebih mudah.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah jenis grafik?

Untuk mengubah jenis grafik, gunakan `chart.setType()` metode dan tentukan jenis bagan yang diinginkan.

### Bisakah saya menambahkan beberapa seri data ke dalam bagan?

Ya, Anda dapat menambahkan beberapa seri data ke bagan menggunakan `chart.getChartData().getSeries().addSeries()` metode.

### Bagaimana cara menyesuaikan warna grafik?

Anda dapat menyesuaikan warna bagan dengan mengatur format isian untuk berbagai elemen bagan, seperti garis kisi, judul, dan legenda.

### Bisakah saya membuat grafik 3D?

Ya, Aspose.Slides untuk Java mendukung pembuatan grafik 3D. Anda dapat mengatur `ChartType` ke jenis bagan 3D untuk membuatnya.

### Apakah Aspose.Slides untuk Java kompatibel dengan versi Java terbaru?

Ya, Aspose.Slides untuk Java diperbarui secara berkala untuk mendukung versi Java terbaru dan menyediakan kompatibilitas di berbagai lingkungan Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}