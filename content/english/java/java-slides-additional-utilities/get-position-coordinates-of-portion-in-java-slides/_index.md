---
title: Get Position Coordinates of Portion in Java Slides
linktitle: Get Position Coordinates of Portion in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-slides-additional-utilities/get-position-coordinates-of-portion-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
        try
        {
            IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
            ITextFrame textFrame = shape.getTextFrame();
            for (IParagraph paragraph : textFrame.getParagraphs())
            {
                for (IPortion portion : paragraph.getPortions())
                {
                    Point2D.Float point = portion.getCoordinates();
                    System.out.println("Corrdinates X =" + point.getX() + " Corrdinates Y =" + point.getY());
                }
            }
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
