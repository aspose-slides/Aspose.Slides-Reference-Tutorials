---
title: Clear Specific Chart Series Data Points Data in Java Slides
linktitle: Clear Specific Chart Series Data Points Data in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 15
url: /java/java-slides-chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "TestChart.pptx");
        try
        {
            ISlide sl = pres.getSlides().get_Item(0);
            IChart chart = (IChart) sl.getShapes().get_Item(0);
            for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints())
            {
                dataPoint.getXValue().getAsCell().setValue(null);
                dataPoint.getYValue().getAsCell().setValue(null);
            }
            chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
            pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
