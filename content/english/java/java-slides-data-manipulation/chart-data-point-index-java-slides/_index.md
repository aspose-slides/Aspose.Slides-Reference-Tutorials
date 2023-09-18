---
title: Chart Data Point Index in Java Slides
linktitle: Chart Data Point Index in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-slides-data-manipulation/chart-data-point-index-java-slides/
---

## Complete Source Code
```java
        String dataDir = "Your Document Directory";
        String pptxFile = dataDir + "ChartIndex.pptx";
        Presentation presentation = new Presentation(pptxFile);
        try {
            Chart chart = (Chart)presentation.getSlides().get_Item(0).getShapes().get_Item(0);
            for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints())
            {
                System.out.println("Point with index " + dataPoint.getIndex() + " is applied to " + dataPoint.getValue());
            }
        } finally {
            if (presentation != null) presentation.dispose();
        }
```
