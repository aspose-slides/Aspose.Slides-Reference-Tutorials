---
title: Embed Fonts in HTML using Aspose.Slides for Java
linktitle: Embed Fonts in HTML using Aspose.Slides for Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-powerpoint-font-management/embed-fonts-in-html/
---

## Complete Source Code
```java


import com.aspose.slides.*;


public class EmbedFontsInHtml
{
    public static void main(String[] args)
    {
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        String outPath = "Your Output Directory";

        //ExStart:EmbedFontsInHtml
        Presentation pres = new Presentation(dataDir + "Presentation.pptx");
        try
        {
            // exclude default presentation fonts
            String[] fontNameExcludeList = { "Arial" };

            EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

            HtmlOptions htmlOptionsEmbed = new HtmlOptions();
            htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));

            pres.save(outPath + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:EmbedFontsInHtml
    }
}


```
