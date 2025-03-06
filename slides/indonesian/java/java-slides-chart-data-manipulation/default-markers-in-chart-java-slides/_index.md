---
title: Penanda Default dalam Bagan di Slide Java
linktitle: Penanda Default dalam Bagan di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat Slide Java dengan penanda default di bagan menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber.
weight: 16
url: /id/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Pengenalan Penanda Default pada Bagan di Slide Java

Dalam tutorial ini, kita akan mempelajari cara membuat bagan dengan penanda default menggunakan Aspose.Slides untuk Java. Penanda default adalah simbol atau bentuk yang ditambahkan ke titik data dalam bagan untuk menyorotnya. Kami akan membuat diagram garis dengan penanda untuk memvisualisasikan data.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda.

## Langkah 1: Buat Presentasi

Pertama, mari buat presentasi dan tambahkan slide ke dalamnya. Kami kemudian akan menambahkan grafik ke slide.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Langkah 2: Tambahkan Bagan Garis dengan Penanda

Sekarang, mari tambahkan diagram garis dengan penanda ke slide. Kami juga akan menghapus semua data default dari grafik.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Langkah 3: Isi Data Bagan

Kami akan mengisi grafik dengan data sampel. Dalam contoh ini, kita akan membuat dua rangkaian dengan titik data dan kategori.

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

Terakhir, simpan presentasi dengan bagan ke lokasi yang Anda inginkan.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Itu dia! Anda telah membuat diagram garis dengan penanda default menggunakan Aspose.Slides untuk Java.

## Kode Sumber Lengkap Untuk Penanda Default pada Bagan di Slide Java

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

Dalam tutorial komprehensif ini, Anda telah mempelajari cara membuat Slide Java dengan penanda default di bagan menggunakan Aspose.Slides untuk Java. Kami membahas keseluruhan proses, mulai dari menyiapkan presentasi hingga menyesuaikan tampilan bagan dan menyimpan hasilnya.

## FAQ

### Bagaimana cara mengubah simbol penanda?

Anda dapat mengkustomisasi simbol penanda dengan mengatur gaya penanda untuk setiap titik data. Menggunakan`IDataPoint.setMarkerStyle()` untuk mengubah simbol penanda.

### Bagaimana cara menyesuaikan warna grafik?

 Untuk mengubah warna bagan, Anda dapat menggunakan`IChartSeriesFormat` Dan`IShapeFillFormat` antarmuka untuk mengatur properti isian dan garis.

### Bisakah saya menambahkan label ke titik data?

 Ya, Anda dapat menambahkan label ke titik data menggunakan`IDataPoint.getLabel()` metode dan sesuaikan sesuai kebutuhan.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
