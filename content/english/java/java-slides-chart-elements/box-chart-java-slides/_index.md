---
title: Box Chart in Java Slides
linktitle: Box Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-slides-chart-elements/box-chart-java-slides/
---

## Complete Source Code
```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
            series.setQuartileMethod(QuartileMethodType.Exclusive);
            series.setShowMeanLine(true);
            series.setShowMeanMarkers(true);
            series.setShowInnerPoints(true);
            series.setShowOutlierPoints(true);
            series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
            series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
            series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
            series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
            series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
            series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
            pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
