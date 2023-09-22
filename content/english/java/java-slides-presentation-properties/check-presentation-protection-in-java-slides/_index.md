---
title: Check Presentation Protection in Java Slides
linktitle: Check Presentation Protection in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 15
url: /java/java-slides-presentation-properties/check-presentation-protection-in-java-slides/
---

## Complete Source Code
```java
        //Path for source presentation
        String pptxFile = RunExamples.getDataDir_PresentationProperties() + "modify_pass2.pptx";
        String pptFile = RunExamples.getDataDir_PresentationProperties() + "open_pass1.ppt";
        // Check the Write Protection Password via IPresentationInfo Interface
        IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
        boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
        System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
        // Check the Write Protection Password via IProtectionManager Interface
        Presentation presentation = new Presentation();
        try
        {
            boolean isWriteProtected = presentation.getProtectionManager().checkWriteProtection("pass2");
            System.out.println("Is presentation write protected = " + isWriteProtected);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        // Check Presentation Open Protection via IPresentationInfo Interface
        presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
        if (presentationInfo.isPasswordProtected())
        {
            System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
        }
```
