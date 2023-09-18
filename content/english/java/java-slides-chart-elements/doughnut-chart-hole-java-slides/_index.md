---
title: Doughnut Chart Hole in Java Slides
linktitle: Doughnut Chart Hole in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-slides-chart-elements/doughnut-chart-hole-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        try
        {
            IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
            chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
            // Write presentation to disk
            presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
