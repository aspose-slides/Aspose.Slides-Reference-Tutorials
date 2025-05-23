---
"description": "Pelajari cara menambahkan callout donat di slide Java menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber untuk presentasi yang lebih baik."
"linktitle": "Tambahkan Panggilan Donat di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Tambahkan Panggilan Donat di Java Slides"
"url": "/id/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Panggilan Donat di Java Slides


## Pengantar untuk Menambahkan Callout Donat di Java Slides menggunakan Aspose.Slides untuk Java

Dalam tutorial ini, kami akan memandu Anda melalui proses penambahan Doughnut Callout ke slide di Java menggunakan Aspose.Slides untuk Java. Doughnut Callout adalah elemen bagan yang dapat digunakan untuk menyorot titik data tertentu dalam bagan Doughnut. Kami akan memberi Anda petunjuk langkah demi langkah dan kode sumber lengkap demi kenyamanan Anda.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Lingkungan Pengembangan Java
2. Aspose.Slides untuk pustaka Java
3. Lingkungan Pengembangan Terpadu (IDE) seperti Eclipse atau IntelliJ IDEA
4. Presentasi PowerPoint tempat Anda ingin menambahkan Donut Callout

## Langkah 1: Siapkan Proyek Java Anda

1. Buat proyek Java baru di IDE pilihan Anda.
2. Tambahkan pustaka Aspose.Slides untuk Java ke proyek Anda sebagai dependensi.

## Langkah 2: Inisialisasi Presentasi

Untuk memulai, Anda perlu menginisialisasi presentasi PowerPoint dan membuat slide tempat Anda ingin menambahkan Donut Callout. Berikut kode untuk mencapainya:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Pastikan untuk mengganti `"Your Document Directory"` dengan jalur sebenarnya ke berkas presentasi PowerPoint Anda.

## Langkah 3: Buat Bagan Donat

Selanjutnya, Anda akan membuat diagram Donat pada slide. Anda dapat menyesuaikan posisi dan ukuran diagram sesuai kebutuhan Anda. Berikut kode untuk menambahkan diagram Donat:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Langkah 4: Sesuaikan Bagan Donat

Sekarang, saatnya untuk menyesuaikan diagram Donat. Kita akan mengatur berbagai properti seperti menghapus legenda, mengonfigurasi ukuran lubang, dan menyesuaikan sudut irisan pertama. Berikut kodenya:

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

Potongan kode ini menetapkan properti untuk diagram Donat. Anda dapat menyesuaikan nilai untuk memenuhi kebutuhan spesifik Anda.

## Langkah 5: Tambahkan Data ke Bagan Donat

Sekarang, mari tambahkan data ke diagram Donat. Kita juga akan menyesuaikan tampilan titik data. Berikut kode untuk melakukannya:

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

Dalam kode ini, kami menambahkan kategori dan titik data ke diagram Donat. Anda dapat menyesuaikan tampilan titik data lebih lanjut sesuai kebutuhan.

## Langkah 6: Simpan Presentasi

Terakhir, jangan lupa untuk menyimpan presentasi Anda setelah menambahkan Donut Callout. Berikut kode untuk menyimpan presentasi:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Pastikan untuk mengganti `"chart.pptx"` dengan nama berkas yang Anda inginkan.

Selamat! Anda telah berhasil menambahkan Donut Callout ke slide Java menggunakan Aspose.Slides untuk Java. Anda sekarang dapat menjalankan aplikasi Java untuk membuat presentasi PowerPoint dengan bagan Donut dan Callout.

## Source Code Lengkap Untuk Menambahkan Callout Donat di Java Slides

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

Dalam tutorial ini, kami telah membahas proses penambahan Donut Callout ke slide Java menggunakan Aspose.Slides untuk Java. Anda telah mempelajari cara membuat bagan Donut, menyesuaikan tampilannya, dan menambahkan titik data. Jangan ragu untuk lebih menyempurnakan presentasi Anda dengan pustaka yang hebat ini dan menjelajahi lebih banyak opsi pembuatan bagan.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah tampilan Donat Callout?

Anda dapat menyesuaikan tampilan Donut Callout dengan mengubah properti titik data dalam bagan. Dalam kode yang diberikan, Anda dapat melihat cara mengatur warna isian, warna garis, gaya font, dan atribut titik data lainnya.

### Bisakah saya menambahkan lebih banyak titik data ke diagram Donat?

Ya, Anda dapat menambahkan titik data sebanyak yang diperlukan ke diagram Donat. Cukup perluas loop dalam kode tempat kategori dan titik data ditambahkan, lalu berikan data dan format yang sesuai.

### Bagaimana cara menyesuaikan posisi dan ukuran diagram Donat pada slide?

Anda dapat mengubah posisi dan ukuran grafik Donat dengan memodifikasi parameter di `addChart` metode. Keempat angka dalam metode tersebut masing-masing sesuai dengan koordinat X dan Y dari sudut kiri atas grafik serta lebar dan tingginya.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}