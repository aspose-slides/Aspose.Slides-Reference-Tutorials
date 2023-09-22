---
title: Support for Interrupt in Java Slides
linktitle: Support for Interrupt in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-slides-media-controls/support-for-interrupt-in-java-slides/
---

## Complete Source Code
```java
        final String[] dataDir = {RunExamples.getDataDir_PresentationProperties()};
        final InterruptionTokenSource tokenSource = new InterruptionTokenSource();
        Runnable interruption = new Runnable()
        {
            public void run()
            {
                LoadOptions options = new LoadOptions();
                options.setInterruptionToken(tokenSource.getToken());
                Presentation presentation = new Presentation(dataDir[0] + "pres.pptx", options);
                try
                {
                    presentation.save(dataDir[0] + "pres.ppt", SaveFormat.Ppt);
                }
                finally
                {
                    if (presentation != null) presentation.dispose();
                }
            }
        };
        Thread thread = new Thread(interruption);// run action in a separate thread
        thread.start();
        Thread.sleep(10000); // some work
        tokenSource.interrupt();
```
