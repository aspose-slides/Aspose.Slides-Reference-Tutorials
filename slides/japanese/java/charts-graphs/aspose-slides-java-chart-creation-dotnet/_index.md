---
date: '2026-06-03'
description: .NETプレゼンテーションでチャートを作成し、Aspose.Slides for Javaを使用してスライドにチャートを追加する方法を学びます。データ可視化のためのステップバイステップガイドに従ってください。
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: .NETでAspose.Slides for Javaを使用してチャートを作成する
url: /ja/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# .NETでAspose.Slides for Javaを使用してチャートを作成する

## はじめに
魅力的なプレゼンテーションを作成するには、聴衆の理解とエンゲージメントを高めるために、チャートなどの視覚的なデータ表現を統合することがよくあります。**.NETでチャートを作成したい場合**、Aspose.Slides for Java は、.NET アプリケーション内でシームレスに動作する強力な言語非依存 API を提供します。このチュートリアルでは、プレゼンテーションの初期化、さまざまなチャートタイプの追加、チャートデータワークブックの管理、シリーズデータの書式設定（負の値の処理を含む）方法を学びます。最後には、数行のコードだけでプログラム的にプレゼンテーションファイルにチャートを生成し、スライドにチャートを追加できるようになります。

## クイック回答
- **主な目的は何ですか？** .NET プレゼンテーションで Aspose.Slides for Java を使用してチャートを作成する。  
- **必要なライブラリのバージョンは？** Aspose.Slides for Java 25.4 以降。  
- **ライセンスは必要ですか？** 開発には無料トライアルが使用できますが、製品版には商用ライセンスが必要です。  
- **Maven または Gradle を使用できますか？** はい、両方のビルドシステムがサポートされています。  
- **利用可能なチャートタイプは何ですか？** クラスター化された縦棒、折れ線、円グラフ、棒グラフ、エリア、その他多数。

## Aspose.Slides for Java を使用して .NET プレゼンテーションでチャートを作成する方法は？
`Presentation` クラスは PowerPoint ファイルを表し、スライドを操作するためのメソッドを提供します。新しい `Presentation` オブジェクトをロードし、`slides.addEmptySlide()` を呼び出してスライドを取得し、次に `slide.getShapes().addChart()` を使用して指定した座標に目的のチャートタイプを挿入します。チャートが追加されたら、シリーズとカテゴリでデータワークブックを埋め、負の値の色付けなどの書式設定を適用し、最後にプレゼンテーションを .pptx ファイルとして保存します。このフローにより、**.NETでチャートを作成する**ための簡潔な API 呼び出しが可能になります。

## Aspose.Slides for Java とは何ですか？
Aspose.Slides for Java は、Microsoft Office を使用せずに PowerPoint ファイルの作成、変更、レンダリングを可能にするクロスプラットフォーム API です。**50+ 入出力フォーマット** をサポートし、メモリ使用量を 200 MB 未満に抑えながら、数千枚のスライドを含むプレゼンテーションを処理できます。

## .NET プロジェクトで Aspose.Slides for Java を使用する理由は？
Aspose.Slides for Java は Java 仮想マシン上で動作し、ネイティブラッパーを介して .NET から呼び出すことができるため、.NET 開発者は成熟したチャートエンジン、高性能な大規模データセットの処理、既存の Java コードとの完全な互換性を、ロジックを書き換えることなく利用できます。

## 前提条件
Aspose.Slides for Java を使用したチャート作成に入る前に、必要なものを整理しましょう。

### 必要なライブラリとバージョン
- **Aspose.Slides for Java**: バージョン 25.4 以降。

### 環境設定要件
- .NET アプリケーションをサポートする開発環境。  
- Java プログラミングの基本的な概念の理解。

### 知識の前提条件
- .NET アプリケーション環境でのプレゼンテーション作成に慣れていること。  
- Java の依存関係とその管理（Maven/Gradle）についての理解。

## Aspose.Slides for Java の設定
Aspose.Slides の使用を開始するには、プロジェクトに依存関係として追加する必要があります。以下にその方法を示します。

### Maven
Maven の依存関係スニペットは、Aspose.Slides for Java をプロジェクトに追加します。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` ファイルにこの行を追加して、Maven Central からライブラリを取得します。

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接ダウンロード
あるいは、[Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) から最新バージョンをダウンロードできます。

#### ライセンス取得手順
- **Free Trial**: 機能を試すために一時ライセンスで開始します。  
- **Purchase**: 制限のない本番利用のためにライセンスを購入します。

#### 基本的な初期化と設定
`Slides` の初期化には、ライセンスの設定と `Presentation` インスタンスの作成が必要です。

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

この設定により、リソース管理が効果的に行われます。

## 実装ガイド
機能の実装手順をステップバイステップでご案内します。

### プレゼンテーションの初期化
**概要:**  
プレゼンテーションインスタンスを作成することで、以降のすべての操作の土台が整います。この機能では、Aspose.Slides を使用してゼロから開始する方法を示します。

#### ステップ 1: 必要なパッケージのインポート
`Presentation` および関連クラスは `com.aspose.slides` 名前空間に属しています。

```java
import com.aspose.slides.Presentation;
```

#### ステップ 2: 新しい Presentation オブジェクトの作成
`Presentation` オブジェクトをインスタンス化し、リソースの確実な解放を保証するために try‑with‑resources ブロックでラップします。

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*これにより、使用後にプレゼンテーションオブジェクトが適切に破棄され、メモリリークを防止します。*

### スライドへのチャート追加
**概要:**  
スライドにチャートを追加することで、データの可視化がより効果的かつ魅力的になります。

#### ステップ 1: 必要なパッケージのインポート
`Chart` クラスは、スライド上に配置してカスタマイズできるチャート形状を表します。

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### ステップ 2: プレゼンテーションの初期化とチャートの追加
スライドを作成し、`ChartType.ClusteredColumn` と希望する位置・サイズを指定して `addChart` を呼び出します。

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

*ここでは、指定された座標とサイズで最初のスライドにクラスター化された縦棒チャートを追加しています。*

### チャートデータワークブックの管理
**概要:**  
チャートのデータワークブックを効率的に管理することで、シリーズやカテゴリをシームレスに操作できます。

#### ステップ 1: 必要なパッケージのインポート
`IChartDataWorkbook` は、チャートが使用する Excel ライクな基盤ワークブックへのアクセスを提供します。

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### ステップ 2: データワークブックへのアクセスとクリア
チャートからワークブックを取得し、既存のデータをクリアして新規に開始します。

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

*新しいシリーズやカテゴリを追加する際に、クリーンな状態で開始するためにワークブックをクリアすることが重要です。*

### チャートへのシリーズとカテゴリの追加
**概要:**  
シリーズとカテゴリを管理して、意味のあるデータポイントを追加する方法を示します。

#### ステップ 1: シリーズとカテゴリの追加
`chart.getChartData().getSeries().add()` と `chart.getChartData().getCategories().add()` を使用して構造を定義します。

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

*シリーズとカテゴリを追加することで、データの提示がより整理されます。*

### シリーズデータの入力と書式設定
**概要:**  
チャートにデータポイントを入力し、特に負の値を扱う際に可読性を高めるよう外観を書式設定します。

#### ステップ 1: シリーズデータの入力
ワークブックの各セルに数値を割り当て、負の数値には赤色の塗りつぶしを適用します。

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

*このセクションでは、データの入力と可視化を向上させるための色書式設定の方法を示します。*

## 一般的な問題と解決策
- **LicenseNotFoundException** – ライセンスファイルのパスが正しく、実行時にファイルにアクセスできることを確認してください。  
- **NullPointerException on chart data** – 新しいシリーズを追加する前に必ずワークブックをクリアし、残存データを防止してください。  
- **Chart not rendering in .NET** – .NET 互換の Aspose.Slides JAR を使用していること、Java ランタイムが .NET プロジェクトで正しく構成されていることを確認してください。

## よくある質問

**Q: GUI なしでプレゼンテーションファイルにチャートを生成できますか？**  
A: はい、Aspose.Slides for Java は完全にヘッドレスで、グラフィカルコンポーネントなしのサーバー上でも動作します。

**Q: サポートされている .NET バージョンはどれですか？**  
A: .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5、.NET 6 がすべてサポートされています。

**Q: 追加できるチャートタイプは何種類ありますか？**  
A: 20 種類以上のチャートが利用可能で、縦棒、折れ線、円グラフ、エリア、レーダーなどがあります。

**Q: 個々のデータポイントにスタイルを適用できますか？**  
A: もちろんです。`IDataPoint` API を使用して、各データポイントの塗りつぶし色、枠線、マーカーを設定できます。

**Q: Java オブジェクトを .NET 型に手動で変換する必要がありますか？**  
A: いいえ、Aspose.Slides for Java の .NET ラッパーが型変換を自動的に処理します。

---

**最終更新日:** 2026-06-03  
**テスト環境:** Aspose.Slides for Java 25.4  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Slides を使用した .NET プレゼンテーションへのチャート埋め込みによる効果的なデータ可視化方法](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Aspose.Slides for .NET を使用したチャートデータソースタイプの取得方法 - チャートとグラフ](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Aspose.Slides .NET でのチャートシリーズ作成と操作のマスター - 効果的なデータ可視化](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}