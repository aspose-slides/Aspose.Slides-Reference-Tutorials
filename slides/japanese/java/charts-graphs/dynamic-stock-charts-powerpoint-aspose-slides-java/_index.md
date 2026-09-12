---
date: '2026-09-12'
description: Maven Aspose Slides の使い方を学び、Java で PowerPoint に dynamic stock charts
  を追加・カスタマイズする方法を紹介します。セットアップ、data series の追加、line formatting、saving が含まれます。
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Maven Aspose Slides チュートリアルでは、Java を使用して PowerPoint で dynamic stock
  charts を作成・カスタマイズする方法を示し、data series、line formatting、saving を取り上げています。
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Maven Aspose Slides ガイド: PowerPoint で dynamic stock charts を作成'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: Java を使用して PowerPoint で dynamic stock charts を作成'
url: /ja/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: JavaでPowerPointの動的株価チャートを作成

## はじめに

**Maven Aspose Slides** は、Java からプログラムで高度な PowerPoint プレゼンテーションを生成できるようにします。このチュートリアルでは、動的な株価チャートの作成、データ系列の追加と書式設定、チャートラインのカスタマイズ、そして最終的にファイルを保存する方法を学びます。四半期レポートを作成する金融アナリストや、自動スライドデッキを構築する開発者のいずれであっても、以下の手順は完全な本番環境向けソリューションを提供します。

**学べること**
- Maven と Aspose.Slides for Java のセットアップ方法  
- 株価チャートを追加し、デフォルトデータをクリアする方法  
- **add data series chart** と **format chart lines** を追加する方法  
- **customize chart java**‑specific visual elements をカスタマイズする方法  
- 更新されたプレゼンテーションを保存する方法

生の数値を目を引く株価ビジュアルに変える準備はできましたか？さあ始めましょう！

## クイック回答
- **必要な Maven アーティファクトはどれですか？** `aspose-slides` バージョン 25.4（またはそれ以降）。  
- **任意の OS で実行できますか？** はい – ライブラリは純粋な Java で、Windows、macOS、Linux で動作します。  
- **開発にライセンスは必要ですか？** テスト用の無料トライアルライセンスで動作しますが、本番環境では正式なライセンスが必要です。  
- **サポートされているチャートタイプは何ですか？** 70 種類以上の組み込みチャートがあり、Stock、Line、Bar チャートなどが含まれます。  
- **どのくらい大きなプレゼンテーションを処理できますか？** Aspose.Slides は、ファイル全体をメモリに読み込まずに 500 枚以上のスライドを扱えます。

## Maven Aspose Slides とは？

`Aspose.Slides for Java` は、Microsoft Office を使用せずに PowerPoint ファイルの作成、操作、変換を可能にする Java API です。Maven との統合により依存関係の管理が簡素化され、Maven Central から直接ライブラリを取得できます。

## 株価チャートに Maven Aspose Slides を使用する理由

Aspose.Slides は **70 以上のチャートタイプ** をサポートし、一般的なサーバーハードウェア上で数百ページのプレゼンテーションを 1 秒未満でレンダリングできます。**high‑low line** と **up/down bar** 機能により、PowerPoint の UI が提供する以上の金融ビジュアルの細かな制御が可能です。

## 前提条件

- **Java Development Kit (JDK)** – バージョン 11 以上。  
- **IDE** – IntelliJ IDEA、Eclipse、またはお好みのエディタ。  
- **Aspose.Slides for Java** – バージョン 25.4（執筆時点での最新）。

### Aspose.Slides for Java の設定

#### Maven
Maven を使用して Aspose.Slides をプロジェクトに統合するには、`pom.xml` に以下の依存関係を追加します。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Gradle ユーザーは、`build.gradle` に以下を含めます。

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### 直接ダウンロード
Alternatively, download the latest JAR from [Aspose.Slides for Java リリース](https://releases.aspose.com/slides/java/).

**ライセンス取得** – 無料トライアルで開始するか、一時ライセンスをリクエストしてください。商用利用の場合は、正式なライセンスを購入する必要があります。

For detailed API reference, see the [Aspose.Slides ドキュメント](https://docs.aspose.com/slides/java/).

## 動的株価チャートの作成手順

プレゼンテーションを読み込み、株価チャートを追加、デフォルトデータをクリアしてから、独自の系列とカテゴリを注入します。核心的な質問への直接的な回答は次のとおりです：

> 既存の PPTX を `new Presentation("template.pptx")` で読み込み、`ChartType.Stock` タイプの `Chart` を追加し、デフォルトの系列とカテゴリをクリアしてから、独自のデータポイントと書式設定オプションで埋めます。最後に `presentation.save("output.pptx", SaveFormat.Pptx)` を呼び出します。

### プレゼンテーションの初期化
#### 概要
既存の PowerPoint ファイルを読み込み、直接変更できるようにします。

#### 手順
1. **ライブラリのインポート** – `Presentation` クラスはすべてのスライド操作のエントリーポイントです。  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **プレゼンテーションファイルの読み込み** – テンプレート PPTX のパスを指定します。  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### スライドに株価チャートを追加
#### 概要
プレゼンテーションの最初のスライドに Stock チャートを挿入します。

`Chart` クラスは、スライドに追加できるチャートシェイプを表します。

#### 直接的な回答
`slide.getShapes().addChart(ChartType.Stock, x, y, width, height)` を呼び出すことで株価チャートを追加できます。これにより、すぐに操作できるチャートオブジェクトが作成されます。

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### チャートの既存データ系列とカテゴリをクリア
#### 概要
事前に設定された系列やカテゴリをすべて削除し、クリーンなデータセットから開始できるようにします。

`ChartData` オブジェクトは、チャートの系列とカテゴリを保持します。

#### 直接的な回答
独自のデータを追加する前に、`chart.getChartData().getSeries().clear()` と `chart.getChartData().getCategories().clear()` を呼び出してデフォルトの内容を消去します。

```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### チャートデータにカテゴリを追加
#### 概要
株価値をグループ化する X 軸のカテゴリ（例：日付）を定義します。

`ChartCategory` はチャートの X 軸ラベルを表します。

#### 直接的な回答
`chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")` のように各ラベルごとに新しい `ChartCategory` を作成し、各月または期間ごとに繰り返します。

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### チャートにデータ系列を追加
#### 概要
4 つの必須系列（Open、High、Low、Close）を追加します。

`ChartSeries` は、チャート内の特定系列のデータポイントのコレクションを保持します。

#### 直接的な回答
各系列について、`chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())` を呼び出します。これにより、系列がチャートのデータワークブックに登録されます。

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 系列にデータポイントを追加
#### 概要
各系列に株価を表す数値を設定します。

`DataPoint` は系列内の単一の値を表します。

#### 直接的な回答
データコレクションをループし、`series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)`（または系列タイプに適したメソッド）を使用して各ポイントを挿入します。

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### ハイロウラインとアップ/ダウンバーの書式設定
#### 概要
ハイロウコネクタとアップ/ダウンバーの塗りつぶしのビジュアルスタイルを調整します。

`Marker` はデータポイントの視覚シンボルを定義します。

#### 直接的な回答
`chart.getChartData().getSeries().get(0).getMarker().setSize(10)` を設定し、`chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` を構成して、線の太さと色を制御します。

```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### アップ/ダウンバーの表示
チャートの `setShowUpDownBars(true)` メソッドを使用して、アップ/ダウンバーを表示します。

```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### ハイロウライン上のデータラベルをカスタマイズ
#### 概要
ハイロウライン上に数値を直接表示して、すぐに参照できるようにします。

`DataLabel` はデータポイントに付随するラベルの外観を制御します。

#### 直接的な回答
`chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` でデータラベルを有効にし、必要に応じてスタイルを設定します。

```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### アップ/ダウンバーの塗りつぶし色を設定
#### 概要
アップバーには緑の塗りつぶし、ダウンバーには赤の塗りつぶしを設定し、市場の動きを直感的に伝えます。

`UpDownBars` オブジェクトは、アップバーとダウンバーの書式設定へのアクセスを提供します。

#### 直接的な回答
`chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` を適用し、塗りつぶし色を `Color.GREEN` に設定します。ダウンバーについても同様に `Color.RED` を設定します。

```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### PowerPoint ファイルを保存
#### 概要
変更を新しい PPTX ファイルに永続化します。

`save` メソッドは、指定された形式でプレゼンテーションをディスクに書き込みます。

#### 直接的な回答
`presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` を呼び出します。これにより、変更されたプレゼンテーションが標準の PowerPoint 形式でディスクに書き込まれます。

```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## よくある問題とトラブルシューティング

- **チャートが表示されない** – チャートの X/Y 座標とサイズがスライドの範囲内にあることを確認してください。  
- **データポイントが欠落している** – データワークブックのセルインデックスが、意図した系列/行と一致しているか確認してください。  
- **ライセンス例外** – 一時トライアルライセンスは 30 日で期限切れになるため、本番ビルドでは永続ライセンスに置き換えてください。  
- **大きなファイルでのパフォーマンス低下** – バッチで数千枚のスライドを処理する場合は、`Presentation.setCacheSize(0)` を使用してキャッシュを無効にします。

## よくある質問

**Q: このコードをウェブアプリケーションで使用できますか？**  
A: はい。ライブラリは純粋な Java で、任意のサーブレットコンテナや Spring Boot サービスで実行できます。

**Q: Aspose.Slides は Stock 以外のチャートタイプもサポートしていますか？**  
A: もちろんです。Line、Bar、Pie、Radar など、70 種類以上のチャートタイプをサポートしています。

**Q: プログラムでチャートタイトルを追加するには？**  
A: `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` を使用し、必要に応じてタイトルをフォーマットします。

**Q: 系列あたりのデータポイント数に制限はありますか？**  
A: 実質的には数万点まで追加可能で、メモリ使用量は線形に増加し、ライブラリはデータをストリーミングしてフットプリントを低く保ちます。

**Q: 最新バージョンの Maven 座標は何ですか？**  
A: 最新バージョンは常に Maven Central の `com.aspose:aspose-slides:25.4`（またはそれ以降）で利用可能です。

**最終更新日:** 2026-09-12  
**テスト環境:** Aspose.Slides for Java 25.4  
**作者:** Aspose

## 関連チュートリアル

- [aspose slides maven 依存関係: Aspose.Slides for Java を使用したプレゼンテーションへのチャート追加と設定](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [PowerPoint チャート作成 Java – Aspose.Slides を使用したチャート付きプレゼンテーションの保存](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [PowerPoint チャートの作成と書式設定 Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}