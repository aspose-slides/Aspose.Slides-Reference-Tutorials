---
title: Histogram Chart in Java Slides
linktitle: Histogram Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 19
url: /java/java-slides-chart-data-manipulation/histogram-chart-java-slides/
---

## Complete Source Code
```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
            series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
            series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
            series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
            series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
            series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
            series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
            chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
            pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
