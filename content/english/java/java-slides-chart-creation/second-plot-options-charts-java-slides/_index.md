---
title: Second Plot Options for Charts in Java Slides
linktitle: Second Plot Options for Charts in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-slides-chart-creation/second-plot-options-charts-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        // Add chart on slide
        IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
        // Set different properties
        chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
        chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
        chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
        chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
        // Write presentation to disk
        presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```
