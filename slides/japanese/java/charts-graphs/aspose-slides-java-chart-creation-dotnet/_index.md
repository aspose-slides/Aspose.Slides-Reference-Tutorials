---
date: '2026-01-14'
description: Aspose.Slides for Java を使用して、.NET プレゼンテーションにクラスター化された縦棒グラフを追加し、スライドにチャートを挿入する方法を学びましょう。完全なコード例付きのステップバイステップガイドをご覧ください。
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: .NET スライドにクラスター化された縦棒グラフを追加 Aspose.Slides Java
url: /ja/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java を使用した .NET プレゼンテーションでのチャート作成
## Introduction
魅力的なプレゼンテーションを作成するには、チャートなどの視覚的なデータ表現を組み込んで、聴衆の理解とエンゲージメントを高めることがよくあります。Aspose.Slides for Java を使用して .NET プレゼンテーションに動的でカスタマイズ可能なチャートを追加したい開発者の方に向けたチュートリアルです。プレゼンテーションの初期化、さまざまなチャートタイプの追加、チャートデータの管理、シリーズデータの書式設定方法を詳しく解説します。

**What You'll Learn:**
- .NET 環境で Aspose.Slides for Java を設定し使用する方法
- Aspose.Slides を使用した新規プレゼンテーションの初期化
- スライドへのチャートの追加とカスタマイズ
- チャートデータ ワークブックの管理
- 特に負の値の取り扱いに焦点を当てたシリーズデータの書式設定

次の前提条件セクションに進めば、スムーズに作業を開始できるようになります。

## Quick Answers
- **What is the primary goal?** .NET スライドにクラスター化された縦棒グラフ（clustered column chart）を追加すること。
- **Which library is required?** Aspose.Slides for Java（v25.4 以上）。
- **Can I use it in a .NET project?** はい – Java ライブラリは Java‑to‑.NET ブリッジを介して動作します。
- **Do I need a license?** 開発用途は無料トライアルで可能です。商用環境ではライセンスが必要です。
- **How long does the implementation take?** 基本的なチャートであれば約 10‑15 分です。

## What is a clustered column chart?
クラスター化された縦棒グラフは、各カテゴリごとに複数のデータ系列が横に並んで表示され、グループ間の値を比較しやすくします。このビジュアルはビジネス ダッシュボード、パフォーマンス レポート、複数指標を対比させたいシナリオに最適です。

## Why add chart to slide with Aspose.Slides for Java?
Aspose.Slides を使用すれば、Microsoft PowerPoint をインストールせずにプレゼンテーションの生成・変更・保存が可能です。チャートタイプ、データ、スタイリングをフルコントロールできるため、.NET アプリケーションから直接レポート生成を自動化できます。

## Prerequisites
Aspose.Slides for Java を使ってチャートを作成する前に、必要なものを整理しましょう。

### Required Libraries and Versions
- **Aspose.Slides for Java**: バージョン 25.4 以降。

### Environment Setup Requirements
- .NET アプリケーションをサポートする開発環境。
- Java の基本的なプログラミング概念の理解。

### Knowledge Prerequisites
- .NET アプリケーションでプレゼンテーションを作成した経験。
- Maven/Gradle などの Java 依存管理ツールの取り扱い。

## Setting Up Aspose.Slides for Java
Aspose.Slides をプロジェクトに組み込むには、依存関係として追加する必要があります。以下の手順をご参照ください。

### Maven
`pom.xml` に次の依存関係を追加します:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` に次を記述します:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
または、[Aspose.Slides for Java リリース](https://releases.aspose.com/slides/java/) から最新バージョンをダウンロードしてください。

#### License Acquisition Steps
- **Free Trial**: 機能を試すための一時ライセンスを取得します。
- **Purchase**: 本格的に使用する場合は商用ライセンスの購入を検討してください。

#### Basic Initialization and Setup
以下は Aspose.Slides の初期化例です:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
この設定により、リソース管理が適切に行われます。

## Implementation Guide
機能を段階的に実装する手順を示します。

### Initializing Presentation
**Overview:**  
プレゼンテーション インスタンスを作成すると、以降のすべての操作の基盤が整います。このセクションでは、Aspose.Slides を使用してゼロから開始する方法を示します。

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
```

#### Step 2: Create a New Presentation Object
以下のように実装します:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*これにより、使用後にプレゼンテーション オブジェクトが適切に破棄され、メモリリークを防止します。*

### Adding Chart to Slide
**Overview:**  
スライドにチャートを追加すると、データの可視化がより効果的で魅力的になります。

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Step 2: Initialize Presentation and Add Chart
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*ここでは、指定した座標とサイズで最初のスライドにクラスター化された縦棒グラフを追加しています。*

### Managing Chart Data Workbook
**Overview:**  
チャートのデータ ワークブックを効率的に管理すれば、シリーズやカテゴリの操作がスムーズになります。

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Step 2: Access and Clear Data Workbook
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*新しいシリーズやカテゴリを追加する前に、ワークブックをクリアしてクリーンな状態にすることが重要です。*

### Adding Series and Categories to Chart
**Overview:**  
シリーズとカテゴリを追加して、意味のあるデータポイントを構築します。

#### Step 1: Add Series and Categories
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*シリーズとカテゴリを追加することで、データの提示が整理されます。*

### Populating Series Data and Formatting
**Overview:**  
データポイントをチャートに入力し、特に負の値の表示を改善するために書式設定を行います。

#### Step 1: Populate Series Data
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*このセクションでは、データの入力と色の書式設定方法を示しています。*

## Common Issues and Solutions
- **Memory leaks:** `Presentation` オブジェクトは必ず `finally` ブロックで `dispose()` を呼び出してください。
- **Incorrect chart type:** クラスター化された縦棒グラフが必要な場合は `ChartType.ClusteredColumn` を使用してください。別のタイプを指定すると異なるビジュアルになります。
- **Negative value colors not applied:** `IDataPoint` の値が `Number` に正しくキャストされているか確認してください。

## Frequently Asked Questions

**Q: Can I use Aspose.Slides for Java in a pure .NET project without Java?**  
A: はい。Java‑to‑.NET ブリッジを介して、.NET 言語から Java API を呼び出すことができます。

**Q: Does the free trial support chart creation?**  
A: トライアル版でもチャート機能はフルに利用可能ですが、生成されたファイルには小さな評価用透かしが入ります。

**Q: Which .NET versions are compatible?**  
A: Java 16 以上と連携できる .NET であれば、.NET Framework 4.6 以降、.NET Core 3.1 以降、.NET 5/6/7 で動作します。

**Q: How do I handle large presentations with many charts?**  
A: 可能な限り同一の `IChartDataWorkbook` インスタンスを再利用し、各 `Presentation` を速やかに破棄してメモリを解放してください。

**Q: Is it possible to export the chart as an image?**  
A: はい。`chart.getImage()` または `chart.exportChartImage()` メソッドを使用して PNG/JPEG 形式の画像を取得できます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose  

---