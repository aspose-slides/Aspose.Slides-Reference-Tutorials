---
title: Edit Chart Data in External Workbook in Java Slides
linktitle: Edit Chart Data in External Workbook in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to edit chart data in an external workbook using Aspose.Slides for Java. Step-by-step guide with source code.
type: docs
weight: 17
url: /java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

## Introduction to Edit Chart Data in External Workbook in Java Slides

In this guide, we will demonstrate how to edit chart data in an external workbook using Aspose.Slides for Java. You'll learn how to modify chart data within a PowerPoint presentation programmatically. Make sure you have the Aspose.Slides library for Java installed and configured in your project.

## Prerequisites

- Aspose.Slides for Java
- Java development environment

## Step 1: Load the Presentation

First, we need to load the PowerPoint presentation that contains the chart whose data we want to edit. Replace `"Your Document Directory"` with the actual path to your presentation file.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Step 2: Access the Chart

Once the presentation is loaded, we need to access the chart within the presentation. In this example, we assume the chart is on the first slide and is the first shape on that slide.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Step 3: Modify Chart Data

Now, let's modify the chart data. We'll focus on changing a specific data point in the chart. In this example, we set the value of the first data point in the first series to 100. You can adjust this value as needed.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Step 4: Save the Presentation

After making the necessary changes to the chart data, save the modified presentation to a new file. You can specify the output file path and format according to your requirements.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Step 5: Cleanup

Don't forget to dispose of the presentation object to release any resources.

```java
if (pres != null) pres.dispose();
```

Now you have successfully edited the chart data in an external workbook within your PowerPoint presentation using Aspose.Slides for Java. You can customize this code to suit your specific needs and integrate it into your Java applications.

## Complete Source Code

```java
        // Pay attention the path to external workbook is hardly saved in the presentation
        // so please copy file externalWorkbook.xlsx from Data/Chart directory D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ before run the example
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save(RunExamples.getOutPath() + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusion

In this comprehensive guide, we have explored how to edit chart data in external workbooks within PowerPoint presentations using Aspose.Slides for Java. By following the step-by-step instructions and source code examples, you've gained the knowledge and skills to programmatically modify chart data with ease.

## FAQ's

### How do I specify a different chart or slide?

To access a different chart or slide, modify the appropriate index in the `getSlides().get_Item()` and `getShapes().get_Item()` methods. Remember that indexing starts from 0.

### Can I edit data in multiple charts within the same presentation?

Yes, you can edit data in multiple charts within the same presentation by repeating the chart data modification steps for each chart.

### What if I want to edit data in an external workbook with a different format?

You can adapt the code to handle different external workbook formats by using the appropriate Aspose.Cells classes and methods for reading and writing data in that format.

### How can I automate this process for multiple presentations?

You can create a loop to process multiple presentations, loading each one, making the desired changes, and saving the modified presentations one by one.
