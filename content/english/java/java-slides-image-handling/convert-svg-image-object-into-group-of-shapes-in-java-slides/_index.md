---
title: Convert SVG Image Object into Group of Shapes in Java Slides
linktitle: Convert SVG Image Object into Group of Shapes in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-slides-image-handling/convert-svg-image-object-into-group-of-shapes-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "image.pptx");
        try
        {
            PictureFrame pFrame = (PictureFrame) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ISvgImage svgImage = pFrame.getPictureFormat().getPicture().getImage().getSvgImage();
            if (svgImage != null)
            {
                // Convert svg image into group of shapes
                IGroupShape groupShape = pres.getSlides().get_Item(0).getShapes().
                        addGroupShape(svgImage, pFrame.getFrame().getX(), pFrame.getFrame().getY(),
                                pFrame.getFrame().getWidth(), pFrame.getFrame().getHeight());
                // remove source svg image from presentation
                pres.getSlides().get_Item(0).getShapes().remove(pFrame);
            }
            pres.save(dataDir + "image_group.pptx", SaveFormat.Pptx);
        }
        finally
        {
            pres.dispose();
        }
```
