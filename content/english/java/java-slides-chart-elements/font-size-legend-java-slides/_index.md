---
title: Font Size Legend in Java Slides
linktitle: Font Size Legend in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-slides-chart-elements/font-size-legend-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
            chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
            chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
            chart.getAxes().getVerticalAxis().setMinValue(-5);
            chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
            chart.getAxes().getVerticalAxis().setMaxValue(10);
            pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
