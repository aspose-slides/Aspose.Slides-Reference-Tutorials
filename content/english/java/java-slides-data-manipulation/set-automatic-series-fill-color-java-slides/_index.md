---
title: Set Automatic Series Fill Color in Java Slides
linktitle: Set Automatic Series Fill Color in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-slides-data-manipulation/set-automatic-series-fill-color-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation();
        try
        {
            // Creating a clustered column chart
            IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
            // Setting series fill format to automatic
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
            }
            // Write the presentation file to disk
            presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
