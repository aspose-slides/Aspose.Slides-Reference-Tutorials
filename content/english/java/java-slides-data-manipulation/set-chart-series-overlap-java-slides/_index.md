---
title: Set Chart Series Overlap in Java Slides
linktitle: Set Chart Series Overlap in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 16
url: /java/java-slides-data-manipulation/set-chart-series-overlap-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation();
        try
        {
            // Adding chart
            IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
            IChartSeriesCollection series = chart.getChartData().getSeries();
            if (series.get_Item(0).getOverlap() == 0)
            {
                // Setting series overlap
                series.get_Item(0).getParentSeriesGroup().setOverlap((byte) -30);
            }
            // Write the presentation file to disk
            presentation.save(dataDir + "SetChartSeriesOverlap_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
