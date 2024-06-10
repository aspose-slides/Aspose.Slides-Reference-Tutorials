---
title: Set Bullet Fill Format in SmartArt using Java
linktitle: Set Bullet Fill Format in SmartArt using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 18
url: /java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;


public class BulletFillFormat
{
    public static void main(String[] args) throws IOException
    {

        //ExStart:BulletFillFormat
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation presentation = new Presentation();
        try
        {
            ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
            ISmartArtNode node = smart.getAllNodes().get_Item(0);

            if (node.getBulletFillFormat() != null)
            {
                BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
                IPPImage image = presentation.getImages().addImage(img);
                node.getBulletFillFormat().setFillType(FillType.Picture);
                node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
                node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
            }
            presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:BulletFillFormat
    }
}


```
