---
title: Fonts Substitution in Java PowerPoint
linktitle: Fonts Substitution in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-powerpoint-font-management/fonts-substitution-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.FontSubstitutionInfo;
import com.aspose.slides.Presentation;


public class GetFontsSubstitution
{
    public static void main(String[] args)
    {
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        //ExStart:GetFontsSubstitution
        Presentation pres = new Presentation(dataDir + "PresFontsSubst.pptx");
        try {
            for (FontSubstitutionInfo fontSubstitution : pres.getFontsManager().getSubstitutions())
            {
                System.out.println(fontSubstitution.getOriginalFontName() + " -> " + fontSubstitution.getSubstitutedFontName());
            }
        } finally {
            if (pres != null) pres.dispose();
        }
        //ExEnd:GetFontsSubstitution
    }
}

```
