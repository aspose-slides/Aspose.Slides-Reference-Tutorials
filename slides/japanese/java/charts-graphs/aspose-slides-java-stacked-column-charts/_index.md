---
date: '2026-02-22'
description: Aspose.Slides を使用して Java で積み上げ縦棒グラフの作成方法を学びます。このチュートリアルでは、Aspose Slides
  の Maven 依存関係、パーセンテージ積み上げグラフの追加、チャート データ ラベルの書式設定、プレゼンテーションを PPTX として保存する方法をカバーしています。
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Java と Aspose.Slides を使用した積み上げ縦棒グラフの作成方法 – 包括的ガイド
url: /ja/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java と Aspose.Slides で積み上げ縦棒グラフを作成する方法 – 包括的ガイド

## Introduction

Aspose.Slides for Java のパワーを活用して、洞察に満ちたデータ ビジュアライゼーションをプレゼンテーションに組み込むことで、資料の質を向上させましょう。このガイドでは、**積み上げ縦棒グラフ** スライドを作成し、ビジネスレポートやプロジェクト統計の提示にプロフェッショナルな外観を提供します。チュートリアルの最後までに、以下ができるようになります。

- Aspose Slides の Maven 依存関係で環境をセットアップする
- ゼロからプレゼンテーションを作成する
- **パーセンテージ積み上げチャート** を追加し外観をカスタマイズする
- **チャート データ ラベルをフォーマット** し、**縦軸の書式を変更**する
- **1 行のコードで PPTX として保存**する

さあ、各ステップを順に確認し、すぐに魅力的なプレゼンテーション作成を始めましょう。

## Quick Answers
- **What library do I need?** `aspose-slides` Maven/Gradle dependency (see “aspose slides maven dependency” below)  
- **Which chart type is used?** `ChartType.PercentsStackedColumn` for a percentage‑stacked column chart  
- **How do I change the axis number format?** Use `IAxis.setNumberFormat()` and disable linking to source  
- **Can I customize data labels?** Yes – iterate through `IChartDataPoint` objects and set a custom `ITextFrame`  
- **How do I save the file?** Call `presentation.save("output.pptx", SaveFormat.Pptx)`

## What is a stacked column chart?
A stacked column chart visualizes multiple data series stacked on top of each other in vertical columns. When you use the **percentage‑stacked** variant, each column always totals 100 %, making it easy to compare proportional contributions across categories.

## Why use Aspose.Slides for Java?
Aspose.Slides provides a pure‑Java API that works on any platform without Microsoft Office installed. It offers fine‑grained control over chart objects, supports a wide range of formats, and lets you generate presentations programmatically—perfect for automated reporting or server‑side document generation.

## Prerequisites
- **Java Development Kit (JDK):** 8 or higher  
- **IDE:** IntelliJ IDEA, Eclipse, or any Java‑compatible editor  
- **Build Tool:** Maven or Gradle (optional but recommended)  
- **Basic Java knowledge** – you should be comfortable with classes and methods  

## Setting Up Aspose.Slides for Java
To start, add the Aspose.Slides library to your project.

### Aspose Slides Maven Dependency
Add the following to your `pom.xml` (this is the **aspose slides maven dependency** you’ll need):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Alternative
If you prefer Gradle, include this line in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Alternatively, download the latest JAR from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition
You can start with a free trial to explore Aspose.Slides features. To remove evaluation limitations, consider obtaining a temporary or purchased license.

- **Free Trial:** Access limited features without immediate costs.  
- **Temporary License:** Request via [Aspose’s site](https://purchase.aspose.com/temporary-license/).  
- **Purchase:** Visit the purchase page for full access.

### Basic Initialization
Here’s a minimal snippet that shows how to create a `Presentation` object:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Implementation Guide

### Creating a Presentation and Adding a Slide
**Overview:**  
First, we’ll create a blank presentation and verify that a slide exists.

#### Step 1: Initialize Presentation Object
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Step 2: Save the Presentation
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Adding Percentage Stacked Column Chart to a Slide
**Overview:**  
Now we’ll place a **percentage stacked chart** onto the first slide.

#### Step 1: Initialize and Access Slide
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Step 2: Add Chart to Slide
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Customizing Chart Axis Number Format
**Overview:**  
For better readability we’ll **change vertical axis format** to show percentages.

#### Step 1: Add and Access Chart
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Step 2: Set Custom Number Format
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Adding Series and Data Points to Chart
**Overview:**  
We’ll populate the chart with sample data series.

#### Step 1: Initialize Presentation and Chart
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Step 2: Add Data Series
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatting Series Fill Color
**Overview:**  
Give each series a distinct color to make the chart easier to read.

#### Step 1: Initialize and Access Chart
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Step 2: Set Fill Colors
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatting Data Labels
**Overview:**  
Now we’ll **format chart data labels** so they display custom text.

#### Step 1: Access Chart Series and Data Points
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Step 2: Customize Data Labels
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Common Issues and Solutions
- **Chart appears empty:** Ensure you have added at least one data series and data point before saving.  
- **Axis numbers not showing percentages:** Remember to set `verticalAxis.setNumberFormatLinkedToSource(false)`; otherwise the custom format is ignored.  
- **License evaluation message:** Apply a valid license file before creating the `Presentation` object to suppress the evaluation banner.

## Frequently Asked Questions

**Q: Can I use this code with Java 11 or newer?**  
A: Yes. The library supports JDK 8+; just use the appropriate classifier (e.g., `jdk16` for JDK 16 or later).

**Q: How do I export the chart as an image instead of a PPTX?**  
A: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding the chart to the slide.

**Q: Is it possible to add a legend to the stacked column chart?**  
A: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My Chart");` and configure `chart.getLegend()` as needed.

**Q: What if I need to update data after the presentation is generated?**  
A: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();` to reflect changes.

**Q: Does Aspose.Slides work on Linux servers?**  
A: Yes. The library is pure Java and runs on any OS with a compatible JRE.

## Conclusion
By following this guide you’ve learned how to **create stacked column chart** presentations with Aspose.Slides for Java, from environment setup to fine‑tuned visual styling. Experiment with different data sets, colors, and label formats to make your reports truly stand out.

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}