---
title: Save PowerPoint with Default Regular Font using Java
linktitle: Save PowerPoint with Default Regular Font using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

## Complete Source Code
```java


import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;



public class SaveWithDefaultRegularFont
{

    public static void main(String[] args)
    {
        String dataDir = "Your Document Directory";
        String outPath = "Your Output Directory";

        //ExStart:SaveWithDefaultRegularFont
        Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
        try
        {
            HtmlOptions htmlOpts = new HtmlOptions();
            htmlOpts.setDefaultRegularFont("Arial Black");
            pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
            htmlOpts.setDefaultRegularFont("Lucida Console");
            pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);

            PdfOptions pdfOpts = new PdfOptions();
            pdfOpts.setDefaultRegularFont("Arial Black");
            pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:SaveWithDefaultRegularFont
    }
}

```
