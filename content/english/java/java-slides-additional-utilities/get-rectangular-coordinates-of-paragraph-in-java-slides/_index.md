---
title: Get Rectangular Coordinates of Paragraph in Java Slides
linktitle: Get Rectangular Coordinates of Paragraph in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-slides-additional-utilities/get-rectangular-coordinates-of-paragraph-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
        try
        {
            IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
            ITextFrame textFrame = shape.getTextFrame();
            Rectangle2D.Float rect = (textFrame.getParagraphs().get_Item(0)).getRect();
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
