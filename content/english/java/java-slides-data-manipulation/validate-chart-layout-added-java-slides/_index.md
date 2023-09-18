---
title: Validate Chart Layout Added in Java Slides
linktitle: Validate Chart Layout Added in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-slides-data-manipulation/validate-chart-layout-added-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
            chart.validateChartLayout();
            double x = chart.getPlotArea().getActualX();
            double y = chart.getPlotArea().getActualY();
            double w = chart.getPlotArea().getActualWidth();
            double h = chart.getPlotArea().getActualHeight();
            // Saving presentation
            pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
