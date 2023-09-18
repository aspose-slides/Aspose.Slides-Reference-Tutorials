---
title: Set Invert Fill Color Chart in Java Slides
linktitle: Set Invert Fill Color Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 22
url: /java/java-slides-data-manipulation/set-invert-fill-color-chart-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Color inverColor = Color.RED;
        Presentation pres = new Presentation();
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
            IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            // Adding new series and categories
            chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
            chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
            chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
            chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
            // Take first chart series and populating series data.
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
            series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
            series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
            Color seriesColor = series.getAutomaticSeriesColor();
            series.setInvertIfNegative(true);
            series.getFormat().getFill().setFillType(FillType.Solid);
            series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
            series.getInvertedSolidFillColor().setColor(Color.RED);
            pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
