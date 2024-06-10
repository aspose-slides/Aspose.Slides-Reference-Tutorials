---
title: Render with Fallback Font in Java PowerPoint
linktitle: Render with Fallback Font in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;


public class RenderingWithFallBackFont
{
    public static void main(String[] args)
    {

        //ExStart:RenderingWithFallBackFont

        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create new instance of a rules collection
        IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();

        // create a number of rules
        rulesList.add(new FontFallBackRule(0x400, 0x4FF, "Times New Roman"));
        //rulesList.add(new FontFallBackRule(...));

        for (IFontFallBackRule fallBackRule : (Iterable<IFontFallBackRule>) rulesList)
        {
            //Trying to remove FallBack font "Tahoma" from loaded rules
            fallBackRule.remove("Tahoma");

            //And to update of rules for specified range
            if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000))
                fallBackRule.addFallBackFonts("Verdana");
        }

        //Also we can remove any existing rules from list
        if (rulesList.size() > 0)
            rulesList.remove(rulesList.get_Item(0));

        Presentation pres = new Presentation(dataDir + "input.pptx");
        try
        {
            //Assigning a prepared rules list for using
            pres.getFontsManager().setFontFallBackRulesCollection(rulesList);

            // Rendering of thumbnail with using of initialized rules collection and saving to PNG
            BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
            ImageIO.write(image, ".png", new File(dataDir + "Slide_0.png"));
        }
        catch (IOException e)
        {
            e.printStackTrace();
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:RenderingWithFallBackFont

    }
}


```
