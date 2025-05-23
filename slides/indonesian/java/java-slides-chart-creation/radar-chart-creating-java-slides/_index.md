---
"description": "Pelajari cara membuat Bagan Radar dalam presentasi PowerPoint Java menggunakan Aspose.Slides untuk Java API."
"linktitle": "Pembuatan Grafik Radar di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Pembuatan Grafik Radar di Java Slides"
"url": "/id/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Pembuatan Grafik Radar di Java Slides


## Pengantar Pembuatan Grafik Radar di Java Slides

Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan Bagan Radar menggunakan API Aspose.Slides for Java. Bagan radar berguna untuk memvisualisasikan data dalam pola melingkar, sehingga memudahkan untuk membandingkan beberapa seri data. Kami akan memberikan petunjuk langkah demi langkah beserta kode sumber Java.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah mengintegrasikan pustaka Aspose.Slides for Java ke dalam proyek Anda. Anda dapat mengunduh pustaka tersebut dari [Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Menyiapkan Presentasi

Mari kita mulai dengan menyiapkan presentasi PowerPoint baru dan menambahkan slide ke dalamnya.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Langkah 2: Menambahkan Bagan Radar

Selanjutnya, kita akan menambahkan grafik radar ke slide. Kita akan menentukan posisi dan dimensi grafik.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Langkah 3: Mengatur Data Bagan

Sekarang kita akan mengatur data grafik. Ini melibatkan pembuatan buku kerja data, penambahan kategori, dan penambahan seri.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Tetapkan judul grafik
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Hapus seri dan kategori yang dihasilkan secara default
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Menambahkan kategori baru
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Menambahkan seri baru
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Langkah 4: Mengisi Data Seri

Sekarang, kita akan mengisi data seri untuk bagan radar kita.

```java
// Mengisi data seri untuk Seri 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Atur warna seri
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Mengisi data seri untuk Seri 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Atur warna seri
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Langkah 5: Menyesuaikan Sumbu dan Legenda

Mari sesuaikan sumbu dan legenda untuk bagan radar kita.

```java
// Tetapkan posisi legenda
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Mengatur Properti Teks Sumbu Kategori
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Mengatur Properti Teks Legenda
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Mengatur Properti Teks Sumbu Nilai
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Mengatur format angka sumbu nilai
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Mengatur nilai unit utama grafik
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Langkah 6: Menyimpan Presentasi

Terakhir, simpan presentasi yang dihasilkan dengan grafik radar

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Selesai! Anda telah berhasil membuat diagram radar dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Kini Anda dapat menyesuaikan contoh ini lebih lanjut agar sesuai dengan kebutuhan spesifik Anda.

## Source Code Lengkap Pembuatan Radar Chart di Java Slides

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Akses slide pertama
	ISlide sld = pres.getSlides().get_Item(0);
	// Tambahkan bagan Radar
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Mengatur indeks lembar data grafik
	int defaultWorksheetIndex = 0;
	// Mendapatkan data grafik WorkSheet
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Tetapkan judul grafik
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Hapus seri dan kategori yang dihasilkan secara default
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Menambahkan kategori baru
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Menambahkan seri baru
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Sekarang mengisi data seri
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Atur warna seri
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Sekarang sedang mengisi data seri lainnya
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Atur warna seri
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Tetapkan posisi legenda
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Mengatur Properti Teks Sumbu Kategori
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Mengatur Properti Teks Legenda
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Mengatur Properti Teks Sumbu Nilai
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Mengatur format angka sumbu nilai
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Mengatur nilai unit utama grafik
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Simpan presentasi yang dihasilkan
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara membuat diagram radar dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Anda dapat menerapkan konsep ini untuk memvisualisasikan dan menyajikan data secara efektif dalam aplikasi Java Anda.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah judul grafik?

Untuk mengubah judul grafik, ubah baris berikut:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Bisakah saya menambahkan lebih banyak rangkaian data ke bagan radar?

Ya, Anda dapat menambahkan lebih banyak seri data dengan mengikuti langkah-langkah di "Langkah 3" dan "Langkah 4" untuk setiap seri tambahan yang ingin Anda sertakan.

### Bagaimana cara menyesuaikan warna grafik?

Anda dapat menyesuaikan warna seri dengan memodifikasi garis yang mengatur `SolidFillColor` properti untuk setiap seri. Misalnya:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Bagaimana cara mengubah label dan format sumbu?

Lihat "Langkah 5" untuk menyesuaikan label dan pemformatan sumbu, termasuk ukuran dan warna font.

### Bagaimana cara menyimpan grafik ke format file yang berbeda?

Anda dapat mengubah format output dengan memodifikasi ekstensi file di `outPath` variabel dan menggunakan yang sesuai `SaveFormat`Misalnya, untuk menyimpan sebagai PDF, gunakan `SaveFormat.Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}