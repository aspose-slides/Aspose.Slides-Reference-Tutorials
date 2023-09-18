---
title: Leader Line Color in Java Slides
linktitle: Leader Line Color in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-slides-data-manipulation/leader-line-color-java-slides/
---

## Complete Source Code
```java
        String presentationName = RunExamples.getDataDir_Charts() + "LeaderLinesColor.pptx";
        String outPath = RunExamples.getOutPath() + "LeaderLinesColor-out.pptx";
        Presentation pres = new Presentation(presentationName);
        try {
            // Get the chart from the first slide
            IChart chart = (IChart)pres.getSlides().get_Item(0).getShapes().get_Item(0);
            // Get series of the chart
            IChartSeriesCollection series = chart.getChartData().getSeries();
            // Get lebels of the first serie
            IDataLabelCollection labels = series.get_Item(0).getLabels();
            // Change color of all leader lines in the collection
            labels.getLeaderLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
            // Save result
            pres.save(outPath, SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
```
