---
title: Default Fonts in PowerPoint with Aspose.Slides for Java
linktitle: Default Fonts in PowerPoint with Aspose.Slides for Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-powerpoint-font-management/default-fonts-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.LoadFormat;
import com.aspose.slides.LoadOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;


import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;


public class DefaultFonts
{
    public static void main(String[] args)
    {
        //ExStart:DefaultFonts
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Use load options to define the default regualr and asian fonts// Use load options to define the default regualr and asian fonts
        LoadOptions loadOptions = new LoadOptions(LoadFormat.Auto);
        loadOptions.setDefaultRegularFont("Wingdings");
        loadOptions.setDefaultAsianFont("Wingdings");

        // Load the presentation
        Presentation pptx = new Presentation(dataDir + "DefaultFonts.pptx", loadOptions);
        try
        {
            // Generate slide thumbnail
            BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
            ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));

            // Generate PDF
            pptx.save(dataDir + "output_out.pdf", SaveFormat.Pdf);

            // Generate XPS
            pptx.save(dataDir + "output_out.xps", SaveFormat.Xps);
        }
        catch (IOException e)
        {
            e.printStackTrace();
        }
        finally
        {
            if (pptx != null) pptx.dispose();
        }
        //ExEnd:DefaultFonts
    }
}

```
