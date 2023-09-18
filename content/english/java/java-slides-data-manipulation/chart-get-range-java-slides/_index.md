---
title: Chart Get Range in Java Slides
linktitle: Chart Get Range in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 16
url: /java/java-slides-data-manipulation/chart-get-range-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        Presentation pres = new Presentation();
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 400, 300);
            String result = chart.getChartData().getRange();
            System.out.println("GetRange result : " + result);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
