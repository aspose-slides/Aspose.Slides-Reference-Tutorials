---
title: Tree Map Chart in Java Slides
linktitle: Tree Map Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-slides-chart-creation/tree-map-chart-java-slides/
---

## Complete Source Code
```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            //branch 1
            IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
            leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
            leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
            chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
            leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
            leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
            chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
            //branch 2
            leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
            leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
            leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
            chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
            leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
            leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
            chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
            series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
            series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
            series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
            series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
            series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
            series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
            series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
            series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
            series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));
            series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);
            pres.save("Treemap.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
