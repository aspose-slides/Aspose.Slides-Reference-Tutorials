---
title: Get Chart Image in Java Slides
linktitle: Get Chart Image in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 19
url: /java/java-slides-data-manipulation/get-chart-image-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
            BufferedImage img = chart.getThumbnail();
            ImageIO.write(img, ".png", new File(dataDir + "image.png"));
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
