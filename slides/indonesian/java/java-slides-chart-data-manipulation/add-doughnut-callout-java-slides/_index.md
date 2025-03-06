---
title: Tambahkan Info Donat di Slide Java
linktitle: Tambahkan Info Donat di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Belajar Menambahkan Info Donat di Slide Java menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber untuk presentasi yang lebih baik.
weight: 12
url: /id/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengantar Menambahkan Info Donat di Slide Java menggunakan Aspose.Slides untuk Java

Dalam tutorial ini, kami akan memandu Anda melalui proses menambahkan Info Donat ke slide di Java menggunakan Aspose.Slides untuk Java. Info Donat adalah elemen bagan yang dapat digunakan untuk menyorot titik data tertentu dalam bagan Donat. Kami akan memberi Anda petunjuk langkah demi langkah dan kode sumber lengkap untuk kenyamanan Anda.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Lingkungan Pengembangan Jawa
2. Aspose.Slide untuk perpustakaan Java
3. Lingkungan Pengembangan Terintegrasi (IDE) seperti Eclipse atau IntelliJ IDEA
4. Presentasi PowerPoint tempat Anda ingin menambahkan Info Donat

## Langkah 1: Siapkan Proyek Java Anda

1. Buat proyek Java baru di IDE pilihan Anda.
2. Tambahkan pustaka Aspose.Slides for Java ke proyek Anda sebagai dependensi.

## Langkah 2: Inisialisasi Presentasi

Untuk memulai, Anda perlu menginisialisasi presentasi PowerPoint dan membuat slide tempat Anda ingin menambahkan Info Donat. Berikut kode untuk mencapai hal ini:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 Pastikan untuk mengganti`"Your Document Directory"` dengan jalur sebenarnya ke file presentasi PowerPoint Anda.

## Langkah 3: Buat Bagan Donat

Selanjutnya, Anda akan membuat bagan Donat pada slide. Anda dapat menyesuaikan posisi dan ukuran bagan sesuai kebutuhan Anda. Berikut kode untuk menambahkan diagram Donat:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Langkah 4: Sesuaikan Bagan Donat

Sekarang, saatnya menyesuaikan bagan Donat. Kita akan mengatur berbagai properti seperti menghilangkan legenda, mengonfigurasi ukuran lubang, dan menyesuaikan sudut irisan pertama. Berikut kodenya:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Cuplikan kode ini menyetel properti untuk bagan Donat. Anda dapat menyesuaikan nilainya untuk memenuhi kebutuhan spesifik Anda.

## Langkah 5: Tambahkan Data ke Bagan Donat

Sekarang, mari tambahkan data ke bagan Donat. Kami juga akan menyesuaikan tampilan titik data. Berikut kode untuk mencapai hal ini:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Sesuaikan tampilan titik data di sini
        i++;
    }
    categoryIndex++;
}
```

Dalam kode ini, kami menambahkan kategori dan titik data ke bagan Donat. Anda dapat menyesuaikan lebih lanjut tampilan titik data sesuai kebutuhan.

## Langkah 6: Simpan Presentasi

Terakhir, jangan lupa untuk menyimpan presentasi Anda setelah menambahkan Donut Callout. Berikut kode untuk menyimpan presentasi:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 Pastikan untuk mengganti`"chart.pptx"` dengan nama file yang Anda inginkan.

Selamat! Anda telah berhasil menambahkan Info Donat ke slide Java menggunakan Aspose.Slides untuk Java. Anda sekarang dapat menjalankan aplikasi Java untuk menghasilkan presentasi PowerPoint dengan bagan Donat dan Callout.

## Kode Sumber Lengkap Untuk Menambahkan Info Donat di Slide Java

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
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Dalam tutorial ini, kita telah membahas proses menambahkan Donut Callout ke slide Java menggunakan Aspose.Slides untuk Java. Anda telah mempelajari cara membuat bagan Donat, menyesuaikan tampilannya, dan menambahkan titik data. Jangan ragu untuk lebih menyempurnakan presentasi Anda dengan perpustakaan canggih ini dan menjelajahi lebih banyak opsi pembuatan bagan.

## FAQ

### Bagaimana cara mengubah tampilan Donut Callout?

Anda dapat mengkustomisasi tampilan Donut Callout dengan memodifikasi properti titik data dalam bagan. Pada kode yang disediakan, Anda dapat melihat cara mengatur warna isian, warna garis, gaya font, dan atribut titik data lainnya.

### Bisakah saya menambahkan lebih banyak titik data ke bagan Donat?

Ya, Anda dapat menambahkan titik data sebanyak yang diperlukan ke bagan Donat. Cukup perpanjang loop dalam kode tempat kategori dan titik data ditambahkan, dan berikan data dan format yang sesuai.

### Bagaimana cara menyesuaikan posisi dan ukuran bagan Donat pada slide?

 Anda dapat mengubah posisi dan ukuran bagan Donat dengan memodifikasi parameter di`addChart` metode. Keempat angka dalam metode tersebut masing-masing sesuai dengan koordinat X dan Y dari sudut kiri atas grafik serta lebar dan tingginya.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
