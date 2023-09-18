---
title: Animating Series in Java Slides
linktitle: Animating Series in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-slides-animation-and-layout/animating-series-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate Presentation class that represents a presentation file 
        Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
        try
        {
            // Get reference of the chart object
            ISlide slide = presentation.getSlides().get_Item(0);
            IShapeCollection shapes = slide.getShapes();
            IChart chart = (IChart) shapes.get_Item(0);
            // Animate the series
            slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None,
                    EffectTriggerType.AfterPrevious);
            ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
                    EffectChartMajorGroupingType.BySeries, 0,
                    EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
            ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
                    EffectChartMajorGroupingType.BySeries, 1,
                    EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
            ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
                    EffectChartMajorGroupingType.BySeries, 2,
                    EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
            ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
                    EffectChartMajorGroupingType.BySeries, 3,
                    EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
            // Write the modified presentation to disk 
            presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
