---
title: Check Password Example in Java Slides
linktitle: Check Password Example in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-slides-presentation-properties/check-password-example-in-java-slides/
---

## Complete Source Code
```java
        //Path for source presentation
        String pptFile = RunExamples.getDataDir_PresentationProperties() + "open_pass1.ppt";
        // Check the Password via IPresentationInfo Interface
        IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
        boolean isPasswordCorrect = presentationInfo.checkPassword("my_password");
        System.out.println("The password \"my_password\" for the presentation is " + isPasswordCorrect);
        isPasswordCorrect = presentationInfo.checkPassword("pass1");
        System.out.println("The password \"pass1\" for the presentation is " + isPasswordCorrect);
```
