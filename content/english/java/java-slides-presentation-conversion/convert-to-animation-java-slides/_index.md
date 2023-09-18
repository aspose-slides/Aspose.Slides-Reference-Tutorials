---
title: Convert to Animation in Java Slides
linktitle: Convert to Animation in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 21
url: /java/java-slides-presentation-conversion/convert-to-animation-java-slides/
---

## Complete Source Code
```java
        String presentationName = RunExamples.getDataDir_Conversion() + "SimpleAnimations.pptx";
        final String outPath = RunExamples.getOutPath();
        final int FPS = 30;
        Presentation pres = new Presentation(presentationName);
        try {
            PresentationAnimationsGenerator animationsGenerator = new PresentationAnimationsGenerator(pres);
            try {
                PresentationPlayer player = new PresentationPlayer(animationsGenerator, 33);
                try {
                    player.setFrameTick(new PresentationPlayer.FrameTick() {
                        public void invoke(PresentationPlayer sender, FrameTickEventArgs arg) {
                            try {
                                ImageIO.write(arg.getFrame(), "PNG", new java.io.File(outPath + "frame_" + sender.getFrameIndex() + ".png"));
                            } catch (IOException e) {
                                throw new RuntimeException(e);
                            }
                        }
                    });
                    animationsGenerator.run(pres.getSlides());
                } finally {
                    if (player != null) player.dispose();
                }
            } finally {
                if (animationsGenerator != null) animationsGenerator.dispose();
            }
        } finally {
            if (pres != null) pres.dispose();
        }
```
