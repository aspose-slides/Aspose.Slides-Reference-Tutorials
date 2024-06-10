---
title: Rule Based Fonts Replacement in Java PowerPoint
linktitle: Rule Based Fonts Replacement in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-powerpoint-text-font-customization/rule-based-fonts-replacement-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;


public class RuleBasedFontsReplacement
{
    public static void main(String[] args) throws IOException
    {
        //ExStart:RuleBasedFontsReplacement
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Load presentation
        Presentation presentation = new Presentation(dataDir + "Fonts.pptx");

        // Load source font to be replaced
        IFontData sourceFont = new FontData("SomeRareFont");

        // Load the replacing font
        IFontData destFont = new FontData("Arial");

        // Add font rule for font replacement
        IFontSubstRule fontSubstRule = new FontSubstRule(sourceFont, destFont, FontSubstCondition.WhenInaccessible);

        // Add rule to font substitute rules collection
        IFontSubstRuleCollection fontSubstRuleCollection = new FontSubstRuleCollection();
        fontSubstRuleCollection.add(fontSubstRule);

        // Add font rule collection to rule list
        presentation.getFontsManager().setFontSubstRuleList(fontSubstRuleCollection);

        // Arial font will be used instead of SomeRareFont when inaccessible
        BufferedImage bmp = presentation.getSlides().get_Item(0).getThumbnail(1f, 1f);

        // Save the image to disk in JPEG format
        ImageIO.write(bmp, "jpeg", new File(dataDir + "Thumbnail_out.jpg"));
        //ExEnd:RuleBasedFontsReplacement
    }
}

```
