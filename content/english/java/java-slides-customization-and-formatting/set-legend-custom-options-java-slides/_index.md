---
title: Set Legend Custom Options in Java Slides
linktitle: Set Legend Custom Options in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-slides-customization-and-formatting/set-legend-custom-options-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        try
        {
            // Get reference of the slide
            ISlide slide = presentation.getSlides().get_Item(0);
            // Add a clustered column chart on the slide
            IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
            // Set Legend Properties
            chart.getLegend().setX(50 / chart.getWidth());
            chart.getLegend().setY(50 / chart.getHeight());
            chart.getLegend().setWidth(100 / chart.getWidth());
            chart.getLegend().setHeight(100 / chart.getHeight());
            // Write presentation to disk
            presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
