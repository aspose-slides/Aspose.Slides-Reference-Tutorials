---
title: Add Image from SVG Object in Java Slides
linktitle: Add Image from SVG Object in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-slides-image-handling/add-image-from-svg-object-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        String svgPath = dataDir + "sample.svg";
        String outPptxPath = dataDir + "presentation.pptx";
        Presentation p = new Presentation();
        try
        {
            String svgContent = new String(Files.readAllBytes(Paths.get(dataDir + "sample.svg")));
            ISvgImage svgImage = new SvgImage(svgContent);
            IPPImage ppImage = p.getImages().addImage(svgImage);
            p.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, ppImage.getWidth(), ppImage.getHeight(), ppImage);
            p.save(dataDir + "presentation.pptx", SaveFormat.Pptx);
        }
        finally
        {
            p.dispose();
        }
```
