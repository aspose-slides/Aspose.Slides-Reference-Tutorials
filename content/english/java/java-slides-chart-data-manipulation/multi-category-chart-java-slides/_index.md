---
title: Multi-Category Chart in Java Slides
linktitle: Multi-Category Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 20
url: /java/java-slides-chart-data-manipulation/multi-category-chart-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        ISlide slide = pres.getSlides().get_Item(0);
        IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
        ch.getChartData().getSeries().clear();
        ch.getChartData().getCategories().clear();
        IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
        fact.clear(0);
        int defaultWorksheetIndex = 0;
        IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
        category.getGroupingLevels().setGroupingItem(1, "Group1");
        category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
        category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
        category.getGroupingLevels().setGroupingItem(1, "Group2");
        category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
        category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
        category.getGroupingLevels().setGroupingItem(1, "Group3");
        category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
        category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
        category.getGroupingLevels().setGroupingItem(1, "Group4");
        category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
        //            Adding Series
        IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
                ChartType.ClusteredColumn);
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
        series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
        // Save presentation with chart
        pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
