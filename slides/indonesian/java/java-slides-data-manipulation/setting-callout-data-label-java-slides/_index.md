---
title: Mengatur Callout Untuk Label Data di Slide Java
linktitle: Mengatur Callout Untuk Label Data di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari Cara Mengatur Info untuk Label Data di Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber.
type: docs
weight: 25
url: /id/java/data-manipulation/setting-callout-data-label-java-slides/
---

## Pengenalan Pengaturan Callout untuk Label Data di Aspose.Slides untuk Java

Dalam tutorial ini, kami akan mendemonstrasikan cara menyiapkan info untuk label data dalam bagan menggunakan Aspose.Slides untuk Java. Info dapat berguna untuk menyorot titik data tertentu dalam bagan Anda. Kami akan memandu kode langkah demi langkah dan memberikan kode sumber yang diperlukan.

## Prasyarat

- Anda harus menginstal Aspose.Slides untuk Java.
- Buat proyek Java dan tambahkan perpustakaan Aspose.Slides ke proyek Anda.

## Langkah 1: Buat Presentasi dan Tambahkan Bagan

 Pertama, kita perlu membuat presentasi dan menambahkan grafik ke slide. Pastikan untuk mengganti`"Your Document Directory"` dengan jalur sebenarnya ke direktori dokumen Anda.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Langkah 2: Konfigurasikan Bagan

Selanjutnya, kita akan mengonfigurasi bagan dengan mengatur properti seperti legenda, seri, dan kategori.

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

## Langkah 3: Sesuaikan Label Data

Sekarang, kita akan menyesuaikan label data, termasuk menyiapkan info untuk rangkaian terakhir.

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
        //Sesuaikan format label (Font, Isi, dll.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Aktifkan info
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

Sekarang, Anda telah berhasil menyiapkan info untuk label data dalam bagan menggunakan Aspose.Slides untuk Java. Sesuaikan kode sesuai dengan bagan spesifik dan kebutuhan data Anda.

## Kode Sumber Lengkap Untuk Mengatur Callout Untuk Label Data di Slide Java

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

Dalam tutorial ini, kita telah menjelajahi cara menyiapkan info untuk label data dalam bagan menggunakan Aspose.Slides untuk Java. Info adalah alat berharga untuk menekankan titik data tertentu dalam bagan dan presentasi Anda. Kami telah menyediakan panduan langkah demi langkah bersama dengan kode sumber untuk membantu Anda mencapai penyesuaian ini.

## FAQ

### Bagaimana cara menyesuaikan tampilan label data?

Untuk mengkustomisasi tampilan label data, Anda dapat mengubah properti seperti font, isian, dan gaya garis. Misalnya:

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

### Bagaimana cara mengaktifkan atau menonaktifkan info untuk label data?

 Untuk mengaktifkan atau menonaktifkan info untuk label data, gunakan`setShowLabelAsDataCallout` metode. Setel ke`true` untuk mengaktifkan info dan`false`untuk menonaktifkannya.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Aktifkan info
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Nonaktifkan info
```

### Bisakah saya menyesuaikan garis pemimpin untuk label data?

Ya, Anda dapat menyesuaikan garis pemimpin untuk label data menggunakan properti seperti gaya garis, warna, dan lebar. Misalnya:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Aktifkan garis pemimpin
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Ini adalah beberapa opsi penyesuaian umum untuk label data dan info di Aspose.Slides untuk Java. Anda selanjutnya dapat menyesuaikan tampilan dengan kebutuhan spesifik Anda.