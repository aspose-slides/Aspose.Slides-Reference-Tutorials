---
title: Font Properties for Individual Legend in Java Slides
linktitle: Font Properties for Individual Legend in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-slides-customization-and-formatting/font-properties-individual-legend-java-slides/
---

## Complete Source Code
```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
            IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
            tf.getPortionFormat().setFontBold(NullableBool.True);
            tf.getPortionFormat().setFontHeight(20);
            tf.getPortionFormat().setFontItalic(NullableBool.True);
            tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
            pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
