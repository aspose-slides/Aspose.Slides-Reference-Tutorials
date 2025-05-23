---
"description": "Pelajari Cara Menyiapkan Callout untuk Label Data di Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber."
"linktitle": "Mengatur Callout Untuk Label Data di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Callout Untuk Label Data di Java Slides"
"url": "/id/java/data-manipulation/setting-callout-data-label-java-slides/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Callout Untuk Label Data di Java Slides


## Pengantar Pengaturan Callout untuk Label Data di Aspose.Slides untuk Java

Dalam tutorial ini, kami akan menunjukkan cara menyiapkan callout untuk label data dalam bagan menggunakan Aspose.Slides untuk Java. Callout dapat berguna untuk menyorot titik data tertentu dalam bagan Anda. Kami akan memandu Anda melalui kode langkah demi langkah dan menyediakan kode sumber yang diperlukan.

## Prasyarat

- Anda harus menginstal Aspose.Slides untuk Java.
- Buat proyek Java dan tambahkan pustaka Aspose.Slides ke proyek Anda.

## Langkah 1: Buat Presentasi dan Tambahkan Bagan

Pertama, kita perlu membuat presentasi dan menambahkan diagram ke slide. Pastikan untuk mengganti `"Your Document Directory"` dengan jalur sebenarnya ke direktori dokumen Anda.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Langkah 2: Konfigurasikan Bagan

Berikutnya, kita akan mengonfigurasi bagan dengan mengatur properti seperti legenda, seri, dan kategori.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Konfigurasikan seri dan kategori (Anda dapat menyesuaikan jumlah seri dan kategori)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Tambahkan titik data di sini
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Langkah 3: Kustomisasi Label Data

Sekarang, kita akan menyesuaikan label data, termasuk menyiapkan keterangan untuk seri terakhir.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Sesuaikan pemformatan titik data (Isi, Garis, dll.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        // Sesuaikan pemformatan label (Font, Isi, dll.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Aktifkan panggilan keluar
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Langkah 4: Simpan Presentasi

Terakhir, simpan presentasi dengan bagan yang dikonfigurasi.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Sekarang, Anda telah berhasil menyiapkan callout untuk label data dalam bagan menggunakan Aspose.Slides untuk Java. Sesuaikan kode sesuai dengan bagan dan persyaratan data spesifik Anda.

## Source Code Lengkap Untuk Setting Callout Label Data di Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(benar);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save("chart.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Dalam tutorial ini, kami telah mempelajari cara menyiapkan callout untuk label data dalam bagan menggunakan Aspose.Slides untuk Java. Callout adalah alat yang berharga untuk menekankan titik data tertentu dalam bagan dan presentasi Anda. Kami telah menyediakan panduan langkah demi langkah beserta kode sumber untuk membantu Anda mencapai penyesuaian ini.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menyesuaikan tampilan label data?

Untuk menyesuaikan tampilan label data, Anda dapat mengubah properti seperti gaya font, isian, dan garis. Misalnya:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### Bagaimana cara mengaktifkan atau menonaktifkan keterangan untuk label data?

Untuk mengaktifkan atau menonaktifkan panggilan untuk label data, gunakan `setShowLabelAsDataCallout` metode. Atur ke `true` untuk mengaktifkan panggilan keluar dan `false` untuk menonaktifkannya.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Aktifkan panggilan keluar
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Nonaktifkan panggilan keluar
```

### Dapatkah saya menyesuaikan garis pemimpin untuk label data?

Ya, Anda dapat menyesuaikan garis batas untuk label data menggunakan properti seperti gaya garis, warna, dan lebar. Misalnya:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Aktifkan garis pemimpin
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Berikut ini adalah beberapa opsi penyesuaian umum untuk label data dan keterangan di Aspose.Slides untuk Java. Anda dapat menyesuaikan tampilan lebih lanjut dengan kebutuhan spesifik Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}