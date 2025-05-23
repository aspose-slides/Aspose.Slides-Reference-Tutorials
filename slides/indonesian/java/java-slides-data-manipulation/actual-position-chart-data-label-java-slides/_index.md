---
"description": "Pelajari cara mendapatkan posisi sebenarnya dari label data grafik di Java Slides menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber."
"linktitle": "Mendapatkan Posisi Aktual Label Data Grafik di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mendapatkan Posisi Aktual Label Data Grafik di Java Slides"
"url": "/id/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mendapatkan Posisi Aktual Label Data Grafik di Java Slides


## Pengantar untuk Mendapatkan Posisi Aktual Label Data Grafik di Java Slides

Dalam tutorial ini, Anda akan mempelajari cara mengambil posisi sebenarnya dari label data bagan menggunakan Aspose.Slides untuk Java. Kita akan membuat program Java yang menghasilkan presentasi PowerPoint dengan bagan, menyesuaikan label data, lalu menambahkan bentuk yang mewakili posisi label data ini.

## Prasyarat

Sebelum memulai, pastikan Anda telah menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda.

## Langkah 1: Buat Presentasi PowerPoint

Pertama, mari kita buat presentasi PowerPoint baru dan tambahkan diagram ke dalamnya. Kita akan menyesuaikan label data diagram nanti dalam tutorial ini.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Langkah 2: Kustomisasi Label Data
Sekarang, mari kita sesuaikan label data untuk rangkaian grafik. Kita akan mengatur posisi label dan menampilkan nilainya.

```java
try {
    // ... (kode sebelumnya)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (kode tersisa)
} finally {
    if (pres != null) pres.dispose();
}
```

## Langkah 3: Dapatkan Posisi Aktual Label Data
Pada langkah ini, kita akan mengulangi titik-titik data dari rangkaian grafik dan mengambil posisi sebenarnya dari label data yang memiliki nilai lebih besar dari 4. Kita kemudian akan menambahkan elips untuk mewakili posisi ini.

```java
try {
    // ... (kode sebelumnya)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (kode tersisa)
} finally {
    if (pres != null) pres.dispose();
}
```

## Langkah 4: Simpan Presentasi
Terakhir, simpan presentasi yang dihasilkan ke sebuah berkas.

```java
try {
    // ... (kode sebelumnya)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Source Code Lengkap untuk Mendapatkan Posisi Aktual Label Data Grafik di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//YANG HARUS DILAKUKAN
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengambil posisi sebenarnya dari label data bagan di Java Slides menggunakan Aspose.Slides untuk Java. Anda sekarang dapat menggunakan pengetahuan ini untuk menyempurnakan presentasi PowerPoint Anda dengan label data yang disesuaikan dan representasi visual dari posisinya.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menyesuaikan label data dalam bagan?

Untuk menyesuaikan label data dalam bagan, Anda dapat menggunakan `setDefaultDataLabelFormat` metode pada rangkaian bagan dan tetapkan properti seperti posisi dan visibilitas. Misalnya:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Bagaimana cara menambahkan bentuk untuk merepresentasikan posisi label data?

Anda dapat mengulangi titik data dari rangkaian grafik dan menggunakan `getActualX`Bahasa Indonesia: `getActualY`Bahasa Indonesia: `getActualWidth`, Dan `getActualHeight` metode label data untuk mendapatkan posisinya. Kemudian, Anda dapat menambahkan bentuk menggunakan `addAutoShape` metode. Berikut contohnya:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Bagaimana cara menyimpan presentasi yang dihasilkan?

Anda dapat menyimpan presentasi yang dihasilkan menggunakan `save` metode. Berikan jalur file yang diinginkan dan `SaveFormat` sebagai parameter. Misalnya:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}