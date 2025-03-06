---
title: Dapatkan Posisi Sebenarnya Label Data Bagan di Slide Java
linktitle: Dapatkan Posisi Sebenarnya Label Data Bagan di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mendapatkan posisi sebenarnya dari label data bagan di Java Slides menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber.
weight: 18
url: /id/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dapatkan Posisi Sebenarnya Label Data Bagan di Slide Java


## Pengantar Mendapatkan Posisi Sebenarnya Label Data Bagan di Slide Java

Dalam tutorial ini, Anda akan mempelajari cara mengambil posisi sebenarnya dari label data bagan menggunakan Aspose.Slides untuk Java. Kita akan membuat program Java yang menghasilkan presentasi PowerPoint dengan bagan, mengkustomisasi label data, dan kemudian menambahkan bentuk yang mewakili posisi label data tersebut.

## Prasyarat

Sebelum memulai, pastikan Anda telah menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda.

## Langkah 1: Buat Presentasi PowerPoint

Pertama, mari buat presentasi PowerPoint baru dan tambahkan bagan ke dalamnya. Kita akan menyesuaikan label data bagan nanti di tutorial.

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

## Langkah 2: Sesuaikan Label Data
Sekarang, mari sesuaikan label data untuk rangkaian bagan. Kami akan menetapkan posisi mereka dan menunjukkan nilainya.

```java
try {
    // ... (kode sebelumnya)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (kode yang tersisa)
} finally {
    if (pres != null) pres.dispose();
}
```

## Langkah 3: Dapatkan Posisi Label Data Sebenarnya
Pada langkah ini, kita akan mengulangi titik data rangkaian bagan dan mengambil posisi sebenarnya dari label data yang memiliki nilai lebih besar dari 4. Kemudian kita akan menambahkan elips untuk mewakili posisi ini.

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
    // ... (kode yang tersisa)
} finally {
    if (pres != null) pres.dispose();
}
```

## Langkah 4: Simpan Presentasi
Terakhir, simpan presentasi yang dihasilkan ke file.

```java
try {
    // ... (kode sebelumnya)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Kode Sumber Lengkap untuk Mendapatkan Posisi Sebenarnya Label Data Bagan di Slide Java

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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//MELAKUKAN
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

## FAQ

### Bagaimana cara mengkustomisasi label data dalam bagan?

 Untuk mengkustomisasi label data dalam bagan, Anda dapat menggunakan`setDefaultDataLabelFormat` metode pada rangkaian bagan dan mengatur properti seperti posisi dan visibilitas. Misalnya:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Bagaimana cara menambahkan bentuk untuk mewakili posisi label data?

 Anda dapat melakukan iterasi melalui titik data rangkaian bagan dan menggunakan`getActualX`, `getActualY`, `getActualWidth` , Dan`getActualHeight`metode label data untuk mendapatkan posisinya. Kemudian, Anda dapat menambahkan bentuk menggunakan`addAutoShape` metode. Berikut ini contohnya:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Bagaimana cara menyimpan presentasi yang dihasilkan?

 Anda dapat menyimpan presentasi yang dihasilkan menggunakan`save` metode. Berikan jalur file yang diinginkan dan`SaveFormat` sebagai parameter. Misalnya:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
