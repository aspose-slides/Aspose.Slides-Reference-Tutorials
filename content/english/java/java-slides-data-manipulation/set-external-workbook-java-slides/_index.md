---
title: Set External Workbook in Java Slides
linktitle: Set External Workbook in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 19
url: /java/java-slides-data-manipulation/set-external-workbook-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
            IChartData chartData = chart.getChartData();
            chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
            chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
            chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
            chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
            chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
            chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
            chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
            chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
            pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
