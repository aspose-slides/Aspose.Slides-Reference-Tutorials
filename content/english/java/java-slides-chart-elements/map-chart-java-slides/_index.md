---
title: Map Chart in Java Slides
linktitle: Map Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 15
url: /java/java-slides-chart-elements/map-chart-java-slides/
---

## Complete Source Code
```java
        String resultPath = RunExamples.getOutPath() +  "MapChart_out.pptx";
        Presentation presentation = new Presentation();
        try {
            //create empty chart
            IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            //Add series and few data points
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
            series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
            series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
            series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
            //add categories
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
            //change data point value
            IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
            dataPoint.getColorValue().getAsCell().setValue("15");
            //set data point appearance
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
            presentation.save(resultPath, SaveFormat.Pptx);
        } finally {
            if (presentation != null) presentation.dispose();
        }
```
