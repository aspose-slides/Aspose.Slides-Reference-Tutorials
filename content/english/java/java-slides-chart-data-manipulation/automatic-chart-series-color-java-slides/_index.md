---
title: Automatic Chart Series Color in Java Slides
linktitle: Automatic Chart Series Color in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-slides-chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        try
        {
            // Access first slide
            ISlide slide = presentation.getSlides().get_Item(0);
            // Add chart with default data
            IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
            // Set first series to Show Values
            chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
            // Setting the index of chart data sheet
            int defaultWorksheetIndex = 0;
            // Getting the chart data worksheet
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            // Delete default generated series and categories
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            int s = chart.getChartData().getSeries().size();
            s = chart.getChartData().getCategories().size();
            // Adding new series
            chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
            chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
            // Adding new categories
            chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
            chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
            chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
            // Take first chart series
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            // Now populating series data
            series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
            series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
            series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
            // Setting automatic fill color for series
            series.getFormat().getFill().setFillType(FillType.NotDefined);
            // Take second chart series
            series = chart.getChartData().getSeries().get_Item(1);
            // Now populating series data
            series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
            series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
            series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
            // Setting fill color for series
            series.getFormat().getFill().setFillType(FillType.Solid);
            series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
            // Save presentation with chart
            presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
