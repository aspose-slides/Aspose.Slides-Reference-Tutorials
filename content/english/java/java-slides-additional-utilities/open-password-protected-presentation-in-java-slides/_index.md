---
title: Open Password-Protected Presentation in Java Slides
linktitle: Open Password-Protected Presentation in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 15
url: /java/java-slides-additional-utilities/open-password-protected-presentation-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // creating instance of load options to set the presentation access password
        LoadOptions loadOptions = new LoadOptions();
        // Setting the access password
        loadOptions.setPassword("pass");
        // Opening the presentation file by passing the file path and load options to the constructor of Presentation class
        Presentation pres = new Presentation(dataDir + "OpenPasswordPresentation.pptx", loadOptions);
        try
        {
            // Printing the total number of slides present in the presentation
            System.out.println(pres.getSlides().size());
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
