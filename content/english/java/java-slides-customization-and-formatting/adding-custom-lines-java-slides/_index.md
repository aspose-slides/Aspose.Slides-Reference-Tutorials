---
title: Adding Custom Lines in Java Slides
linktitle: Adding Custom Lines in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-slides-customization-and-formatting/adding-custom-lines-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
            IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
            shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
            shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
            pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
