---
title: Set Data Range in Java Slides
linktitle: Set Data Range in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 18
url: /java/java-slides-data-manipulation/set-data-range-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate Presentation class that represents PPTX file
        Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
        // Access first slideMarker and add chart with default data
        ISlide slide = presentation.getSlides().get_Item(0);
        IChart chart = (IChart) slide.getShapes().get_Item(0);
        chart.getChartData().setRange("Sheet1!A1:B4");
        presentation.save(dataDir + "SetDataRange_out.pptx", SaveFormat.Pptx);
```
