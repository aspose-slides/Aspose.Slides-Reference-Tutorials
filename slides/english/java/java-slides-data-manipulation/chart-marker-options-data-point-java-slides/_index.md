---
title: Chart Marker Options on Data Point in Java Slides
linktitle: Chart Marker Options on Data Point in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Optimize your Java Slides with Custom Chart Marker Options. Learn to enhance data points visually using Aspose.Slides for Java. Explore step-by-step guidance and FAQs.
weight: 14
url: /java/data-manipulation/chart-marker-options-data-point-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chart Marker Options on Data Point in Java Slides


## Introduction to Chart Marker Options on Data Point in Java Slides

When it comes to creating impactful presentations, the ability to customize and manipulate chart markers on data points can make all the difference. With Aspose.Slides for Java, you have the power to transform your charts into dynamic and visually engaging elements.

## Prerequisites

Before we dive into the coding part, make sure you have the following prerequisites in place:

- Java Development Environment
- Aspose.Slides for Java Library
- A Java Integrated Development Environment (IDE)
- Sample Presentation Document (e.g., "Test.pptx")

## Step 1: Setting up the Environment

First, ensure you have the necessary tools installed and ready. Create a Java project in your IDE and import the Aspose.Slides for Java library.

## Step 2: Loading the Presentation

To get started, load your sample presentation document. In the provided code, we assume the document is named "Test.pptx."

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Step 3: Creating a Chart

Now, let's create a chart in the presentation. We'll use a Line Chart with Markers in this example.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Step 4: Working with Chart Data

To manipulate chart data, we need to access the chart data workbook and prepare the data series. We'll clear the default series and add our custom data.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Step 5: Adding Custom Markers

Here comes the exciting part - customizing the markers on data points. We'll use images as markers in this example.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Adding custom markers to data points
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Repeat for other data points
// ...

// Changing the chart series marker size
series.getMarker().setSize(15);
```

## Step 6: Saving the Presentation

Once you've customized your chart markers, save the presentation to see the changes in action.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Complete Source Code For Chart Marker Options on Data Point in Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Creating the default chart
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Getting the default chart data worksheet index
int defaultWorksheetIndex = 0;
//Getting the chart data worksheet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Delete demo series
chart.getChartData().getSeries().clear();
//Add new series
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Set the picture
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Set the picture
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Take first chart series
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Add new point (1:3) there.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//Changing the chart series marker
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Conclusion

With Aspose.Slides for Java, you can elevate your presentations by customizing chart markers on data points. This allows you to create visually stunning and informative slides that captivate your audience.

## FAQ's

### How can I change the marker size for data points?

To change the marker size for data points, use the `series.getMarker().setSize()` method and provide the desired size as an argument.

### Can I use images as custom markers?

Yes, you can use images as custom markers for data points. Set the fill type to `FillType.Picture` and provide the image you want to use.

### Is Aspose.Slides for Java suitable for creating dynamic charts?

Absolutely! Aspose.Slides for Java provides extensive capabilities for creating dynamic and interactive charts in your presentations.

### Can I customize other aspects of the chart using Aspose.Slides?

Yes, you can customize various aspects of the chart, including titles, axes, data labels, and more, using Aspose.Slides for Java.

### Where can I access the Aspose.Slides for Java documentation and downloads?

You can find the documentation at [here](https://reference.aspose.com/slides/java/) and download the library at [here](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
