---
date: '2026-03-20'
description: Aspose.Slides を使用して Java のプレゼンテーションにチャートを追加し、プレゼンテーションのチャートファイルを迅速に生成する方法を学びましょう。
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Aspose.Slides を使用して Java プレゼンテーションにチャートを追加する方法
url: /ja/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java を使用してプレゼンテーションにチャートを追加する方法

## Introduction

データを効果的に伝える動的なプレゼンテーションは、今日のスピーディなビジネス環境で不可欠です。財務レポート、マーケティング資料、プロジェクトステータスの更新など、**スライドにチャートを追加する方法**を知っていれば、聴衆のエンゲージメントを大幅に向上させることができます。このチュートリアルでは、3D 積み上げ縦棒グラフを追加し、データを設定し、最終ファイルを保存する手順を Aspose.Slides for Java を使ってステップバイステップで学びます。

### Quick Answers
- **What is the primary library?** Aspose.Slides for Java  
- **Which chart type is demonstrated?** 3D Stacked Column  
- **Can I generate presentation chart files programmatically?** Yes, using the API methods shown below  
- **What Java version is recommended?** JDK 16 or later  
- **Do I need a license for production?** A valid Aspose.Slides license is required for commercial use  

## What is “how to add chart” in Aspose.Slides?

Aspose.Slides for Java は、Microsoft Office を使用せずに PowerPoint ファイルの作成、編集、エクスポートを行える豊富なオブジェクト群を提供します。チャートの追加は、`Presentation` オブジェクトを作成し、チャートシェイプを挿入し、組み込みのワークブックにデータを供給するだけで完了します。

## Why add chart to Java presentations?

- **Visual impact:** チャートは生の数値をすぐに理解できるビジュアルに変換します。  
- **Automation:** レポートをその場で生成でき、定期的なメール配信やダッシュボードに最適です。  
- **Consistency:** すべての生成資料で同じスタイリングとブランディングを維持できます。  
- **Portability:** 1 つのメソッド呼び出しで PPTX、PDF、画像へエクスポートできます。

## Prerequisites

- **Libraries and Dependencies:** Aspose.Slides for Java をインストールしておく必要があります。  
- **Environment Setup:** Java 環境で作業します（推奨は JDK 16 以降）。  
- **Knowledge Base:** 基本的な Java プログラミングの知識があるとスムーズです。

## Setting Up Aspose.Slides for Java

### Installation

Aspose.Slides をプロジェクトに組み込むには、以下のいずれかの方法でインストールしてください。

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**: あるいは、[Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) から最新バージョンを直接ダウンロードします。

### License Acquisition
- **Free Trial:** 無料トライアルで機能を試すことができます。  
- **Temporary License:** 長期テスト用に一時ライセンスを取得できます。  
- **Purchase:** 商用利用には正式ライセンスの取得が必要です。

インストールが完了したら、`Presentation` クラスのインスタンスを作成します。これがすべてのチャート関連操作のエントリーポイントになります。

## Implementation Guide

### How to add chart to a presentation with a 3D stacked column

#### Overview
Aspose.Slides を使えば、ゼロからプレゼンテーションを作成するのは簡単です。このセクションでは、プレゼンテーションの最初のスライドに 3D 積み上げ縦棒グラフを追加します。

**Steps:**

1. **Initialize Presentation Object**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Explain Parameters**  
   - `ChartType.StackedColumn3D`: チャートの種類を指定します。  
   - 位置とサイズ `(0, 0, 500, 500)`: スライド上でチャートが表示される場所と大きさを決定します。

### Configure Chart Data

#### Overview
チャートを意味のあるものにするには、データ系列とカテゴリを設定する必要があります。このセクションでは、特定のデータポイントをチャートに追加する方法を示します。

**Steps:**

1. **Access Chart's Data Workbook**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Set Rotation3D Properties for Chart

#### Overview
3D 回転プロパティでチャートの視覚的魅力を高めましょう。このカスタマイズにより、視点と奥行きを調整できます。

**Steps:**

1. **Configure 3D Rotations**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Explain Parameters**  
   - `setRightAngleAxes(true)`: 軸が直角になるようにします。  
   - Rotation values: 3D 表示の角度と奥行きを調整します。

### Populate Series Data in Chart

#### Overview
データポイントをチャートに入力することは、分析に不可欠です。ここでは、系列に具体的な値を追加します。

**Steps:**

1. **Add Data Points**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Adjust Series Overlap in Chart

#### Overview
チャートの外観を微調整すると、可読性が向上します。このセクションでは、データ可視化を改善するためのオーバーラッププロパティの調整方法を説明します。

**Steps:**

1. **Set Series Overlap**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Save Presentation

#### Overview
プレゼンテーションの設定が完了したら、目的の形式でディスクに保存します。この手順で変更内容がすべて保持されます。

**Steps:**

1. **Save the Presentation**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Common Issues and Solutions

| Issue | Cause | Solution |
|-------|-------|----------|
| **Chart appears flat** | 3D rotation not set | Call `setRotation3D` with appropriate X/Y values. |
| **Data not showing** | Workbook cells not linked | Ensure `fact.getCell` references correct row/column indices. |
| **File not saved** | Incorrect path or missing permissions | Verify `outputFilePath` is writable and folder exists. |

## Frequently Asked Questions

**Q: Can I generate presentation chart files in formats other than PPTX?**  
A: Yes, Aspose.Slides supports PDF, ODP, and image formats via the `SaveFormat` enum.

**Q: Do I need a license to run the code in development?**  
A: A temporary or evaluation license works for development, but a full license is required for production deployments.

**Q: Is it possible to add multiple charts to the same slide?**  
A: Absolutely. Call `slide.getShapes().addChart` multiple times with different positions or sizes.

**Q: How do I change the chart’s color palette?**  
A: Use the `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` and set a `SolidFillColor`.

**Q: Can I bind the chart to an external data source like a database?**  
A: Yes. Retrieve data with JDBC, then populate the workbook cells programmatically before saving.

## Conclusion

You have now learned **how to add chart** to a Java presentation, configure its data, customize 3D rotation, adjust series overlap, and save the final file. This knowledge lets you automate report generation, create consistent branding, and deliver data‑driven presentations without manual effort. For deeper customization—such as styling legends, axes, or applying themes—explore the full capabilities in the official documentation.

For more advanced features and customization options, refer to the [Aspose.Slides for Java documentation](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose