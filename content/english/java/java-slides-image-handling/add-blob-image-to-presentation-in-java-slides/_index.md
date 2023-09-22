---
title: Add Blob Image to Presentation in Java Slides
linktitle: Add Blob Image to Presentation in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-slides-image-handling/add-blob-image-to-presentation-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        String pathToLargeImage = dataDir + "large_image.jpg";
        // create a new presentation which will contain this image
        Presentation pres = new Presentation();
        try
        {
            // supposed we have the large image file we want to include into the presentation
            FileInputStream fip = new FileInputStream(dataDir + "large_image.jpg");
            try
            {
                // let's add the image to the presentation - we choose KeepLocked behavior, because we not
                // have an intent to access the "largeImage.png" file.
                IPPImage img = pres.getImages().addImage(fip, LoadingStreamBehavior.KeepLocked);
                pres.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, 300, 200, img);
                // save the presentation. Despite that the output presentation will be
                // large, the memory consumption will be low the whole lifetime of the pres object
                pres.save(dataDir + "presentationWithLargeImage.pptx", SaveFormat.Pptx);
            }
            finally
            {
                fip.close();
            }
        }
        catch (java.io.IOException e)
        {
            e.printStackTrace();
        }
        finally
        {
            pres.dispose();
        }
```
