---
title: Get Fonts Folders in PowerPoint using Java
linktitle: Get Fonts Folders in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-powerpoint-font-management/get-fonts-folders-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.FontsLoader;



public class GetFontsFolders
{
    public static void main(String[] args)
    {
        //ExStart:GetFontsFolders
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        //The following line shall return folders where font files are searched.
        //Those are folders that have been added with LoadExternalFonts method as well as system font folders.
        String[] fontFolders = FontsLoader.getFontFolders();

        //ExEnd:GetFontsFolders
    }
}


```
