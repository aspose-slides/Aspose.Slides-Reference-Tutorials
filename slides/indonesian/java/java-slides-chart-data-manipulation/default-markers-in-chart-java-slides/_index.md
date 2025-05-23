---
"description": "Pelajari cara membuat Slide Java dengan penanda default dalam bagan menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber."
"linktitle": "Penanda Default dalam Bagan di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Penanda Default dalam Bagan di Slide Java"
"url": "/id/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Penanda Default dalam Bagan di Slide Java


## Pengenalan Penanda Default pada Bagan di Slide Java

Dalam tutorial ini, kita akan menjelajahi cara membuat bagan dengan penanda default menggunakan Aspose.Slides untuk Java. Penanda default adalah simbol atau bentuk yang ditambahkan ke titik data dalam bagan untuk menyorotnya. Kita akan membuat bagan garis dengan penanda untuk memvisualisasikan data.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda.

## Langkah 1: Buat Presentasi

Pertama, mari kita buat presentasi dan tambahkan slide ke dalamnya. Kemudian kita akan menambahkan diagram ke slide tersebut.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Langkah 2: Tambahkan Bagan Garis dengan Penanda

Sekarang, mari tambahkan diagram garis dengan penanda ke slide. Kita juga akan menghapus data default dari diagram.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Langkah 3: Mengisi Data Bagan

Kita akan mengisi diagram dengan data sampel. Dalam contoh ini, kita akan membuat dua seri dengan titik data dan kategori.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Seri 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Seri 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Mengisi data seri
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Langkah 4: Sesuaikan Bagan

Anda dapat menyesuaikan bagan lebih lanjut, seperti menambahkan legenda dan menyesuaikan tampilannya.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Langkah 5: Simpan Presentasi

Terakhir, simpan presentasi dengan bagan di lokasi yang Anda inginkan.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Selesai! Anda telah membuat diagram garis dengan penanda default menggunakan Aspose.Slides untuk Java.

## Source Code Lengkap Untuk Penanda Default pada Bagan di Java Slides

```java
        // Jalur ke direktori dokumen.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Ambil seri grafik kedua
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Sekarang mengisi data seri
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Kesimpulan

Dalam tutorial lengkap ini, Anda telah mempelajari cara membuat Java Slides dengan penanda default dalam bagan menggunakan Aspose.Slides untuk Java. Kami membahas seluruh proses, mulai dari menyiapkan presentasi hingga menyesuaikan tampilan bagan dan menyimpan hasilnya.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah simbol penanda?

Anda dapat menyesuaikan simbol penanda dengan mengatur gaya penanda untuk setiap titik data. Gunakan `IDataPoint.setMarkerStyle()` untuk mengubah simbol penanda.

### Bagaimana cara menyesuaikan warna grafik?

Untuk mengubah warna grafik, Anda dapat menggunakan `IChartSeriesFormat` Dan `IShapeFillFormat` antarmuka untuk mengatur properti isi dan garis.

### Bisakah saya menambahkan label ke titik data?

Ya, Anda dapat menambahkan label ke titik data menggunakan `IDataPoint.getLabel()` metode dan menyesuaikannya sesuai kebutuhan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}