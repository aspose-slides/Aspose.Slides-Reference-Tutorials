---
title: Set Layout Mode in Java Slides
linktitle: Set Layout Mode in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 23
url: /java/java-slides-data-manipulation/set-layout-mode-java-slides/
---

## Complete Source Code
```java
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation();
        try
        {
            ISlide slide = presentation.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
            chart.getPlotArea().setX(0.2f);
            chart.getPlotArea().setY(0.2f);
            chart.getPlotArea().setWidth(0.7f);
            chart.getPlotArea().setHeight(0.7f);
            chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
            presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
