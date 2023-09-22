---
title: Update Presentation Properties in Java Slides
linktitle: Update Presentation Properties in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-slides-media-controls/update-presentation-properties-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // read the info of presentation 
        IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "ModifyBuiltinProperties1.pptx");
        // obtain the current properties 
        IDocumentProperties props = info.readDocumentProperties();
        // set the new values of Author and Title fields 
        props.setAuthor("New Author");
        props.setTitle("New Title");
        // update the presentation with a new values 
        info.updateDocumentProperties(props);
        info.writeBindedPresentation(dataDir + "ModifyBuiltinProperties1.pptx");
```
