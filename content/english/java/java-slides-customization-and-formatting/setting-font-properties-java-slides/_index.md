---
title: Setting Font Properties in Java Slides
linktitle: Setting Font Properties in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 15
url: /java/java-slides-customization-and-formatting/setting-font-properties-java-slides/
---

## Complete Source Code
```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
            chart.setDataTable(true);
            chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
            pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
