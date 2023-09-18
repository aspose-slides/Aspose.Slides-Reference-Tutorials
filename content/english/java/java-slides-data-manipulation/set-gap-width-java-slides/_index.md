---
title: Set Gap Width in Java Slides
linktitle: Set Gap Width in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 21
url: /java/java-slides-data-manipulation/set-gap-width-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Creating empty presentation 
        Presentation presentation = new Presentation();
        // Access first slide
        ISlide slide = presentation.getSlides().get_Item(0);
        // Add chart with default data
        IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
        // Setting the index of chart data sheet
        int defaultWorksheetIndex = 0;
        // Getting the chart data worksheet
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        // Add series
        chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
        chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
        // Add Catrgories
        chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
        chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
        chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
        // Take second chart series
        IChartSeries series = chart.getChartData().getSeries().get_Item(1);
        // Now populating series data
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
        // Set GapWidth value
        series.getParentSeriesGroup().setGapWidth(50);
        // Save presentation with chart
        presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```
