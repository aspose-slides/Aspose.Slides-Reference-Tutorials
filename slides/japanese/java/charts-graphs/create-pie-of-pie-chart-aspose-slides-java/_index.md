---
date: '2026-07-17'
description: Aspose.Slides for Java を使用して Pie of Pie チャートを作成し、PowerPoint にチャートを追加する方法を学びます。セットアップ、コード、カスタマイズ、PPTX
  への保存が含まれます。
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Aspose.Slides for Java を使用して PowerPoint にチャートを追加します。このガイドでは、数分で Pie
  of Pie チャートを作成、カスタマイズ、PPTX として保存する方法を示します。
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: PowerPoint にチャートを追加 – Java で Pie of Pie Chart を作成
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: PowerPoint にチャートを追加 – Java と Aspose.Slides を使用して Pie of Pie Chart を作成
url: /ja/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPointにチャートを追加 – Aspose.Slides for Javaでパイ・オブ・パイチャートを作成

## チャートとグラフ

### はじめに

現代のデータ駆動型プレゼンテーションでは、**PowerPointにチャートを追加**することが、生データを視覚的な洞察に変える最速の方法です。通常の円グラフは少数のカテゴリには適していますが、いくつかのスライスが非常に小さい場合、読めなくなります。*Pie of Pie* チャートは、これらの小さなスライスを二次円グラフに抽出することで、メインのチャートをすっきりさせ、詳細を見やすくします。

このチュートリアルでは、Aspose.Slides for Javaを使用してPie of Pieチャートを作成し、**PowerPointにチャートを追加**する方法を学びます。環境設定、チャート作成、ラベルのカスタマイズ、分割位置の調整、そして最終的にプレゼンテーションをPPTXファイルとして保存する手順を順に解説します。最後まで実施すれば、任意のスライドデッキに高度なチャートを埋め込む準備が整います。

## クイック回答
Aspose.Slidesでは、`Presentation` がPPTXファイルを表し、`ChartType.PieOfPie` がPie of Pieチャートを選択し、`setShowValue(true)` がラベルに値を表示し、`save` がファイルを書き出します。

- **PowerPoint操作の主なクラスは何ですか？** `Presentation` – メモリ内のPPTX全体を表します。  
- **小さなスライス用に二次円を作成するチャートタイプはどれですか？** `ChartType.PieOfPie`。  
- **各スライスに値を表示するには？** `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)` を設定します。  
- **ファイルを直接PPTXとして保存できますか？** はい – `presentation.save("output.pptx", SaveFormat.Pptx)` を呼び出します。  
- **開発にライセンスは必要ですか？** 無料の30日間トライアルでテスト可能です。永続ライセンスを取得すれば評価ウォーターマークが除去されます。

## Pie of Pieチャートとは？

**Pie of Pie chart** は、2層の円グラフで、小さなスライスを別のリンクされた円に分離し、読みやすくする可視化です。Aspose.Slidesはこのチャートタイプを標準でサポートしており、分割サイズ、位置、ラベルの書式設定を制御できます。

## なぜAspose.SlidesでPowerPointにチャートを追加するのか？

Aspose.Slidesは、Microsoft OfficeをインストールせずにPowerPointファイルの生成、編集、レンダリングが可能です。**50以上の入力および出力フォーマット**をサポートし、**最大500枚のスライド**を典型的なサーバーハードウェアで1秒未満で処理し、チャートのスタイリング、データラベル、レイアウトに対する**フルAPI制御**を提供します。自動レポートパイプラインに最適です。

## 前提条件

- **Java Development Kit (JDK) 16+** がインストールされていること。  
- **IntelliJ IDEA**、**Eclipse**、**NetBeans** などの IDE。  
- 依存関係管理のための Maven または Gradle（以下のセクション参照）。  
- 基本的な Java の知識とプロジェクト構築の経験。

## Aspose.Slides for Java の設定

### インストール情報

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**直接ダウンロード:** 最新バージョンは [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) からダウンロードできます。

### ライセンス取得手順

- **無料トライアル:** すべての機能を試すために30日間のトライアルから開始します。  
- **一時ライセンス:** 延長評価のために一時キーをリクエストします。  
- **購入:** 本番使用のために永続ライセンスを取得し、評価ウォーターマークを除去します。

### 基本的な初期化と設定

`Presentation` はPowerPointファイル作成のメインオブジェクトで、`Chart` はスライド内のチャートシェイプを表します。

```java
Presentation presentation = new Presentation();
```  

これにより、スライドとチャートを追加できる空のプレゼンテーションが作成されます。

## 実装ガイド

### Aspose.Slides for Javaを使用してPowerPointにチャートを追加するにはどうすればよいですか？

`Presentation` を新規にロードし、スライドを追加し、`PieOfPie` タイプの `Chart` を挿入します。API呼び出しは簡潔で、チャート作成、シリーズデータの設定、ラベル表示の調整、二次円のサイズ設定、最後に保存という流れです。全体の手順は通常20行未満のコードで収まり、自動レポート生成に最適です。

### 'Pie of Pie' チャートの作成

#### 概要

最初のスライドにPie of Pieチャートを作成し、最小のスライスを分割し、各セグメントに値のラベルを付けます。

#### ステップ1: Presentation クラスのインスタンスを作成

```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  

これにより、以降のすべてのスライドとチャートのコンテナが初期化されます。

#### ステップ2: 最初のスライドに 'Pie of Pie' チャートを追加

```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  

ここでは `ChartType.PieOfPie` を指定し、スライドキャンバス上でチャートの位置 (X, Y) とサイズ (幅, 高さ) を定義します。

#### ステップ3: シリーズのデータラベルに値を表示するよう設定

```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  

`showValue` を有効にすると、各スライスに数値が表示され、迅速なデータ解釈に不可欠です。

#### ステップ4: 二次円のサイズとパーセンテージによる分割を設定

```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  

これらのオプションにより、チャートのどの程度を二次円に割り当てるか、またパーセンテージ閾値に基づいてどのスライスを移動させるかを決定できます。

#### ステップ5: プレゼンテーションをPPTX形式でディスクに保存

```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **プロのコツ:** 絶対パスまたは Java の `Paths.get()` を使用して、プラットフォーム固有の区切り文字を回避してください。

## 一般的な問題と解決策

`License` クラスは評価制限を解除するためにライセンスファイルをロードします。

- **ライセンスがない警告:** チャートに「Evaluation Only」と表示された場合、`License license = new License(); license.setLicense("Aspose.Slides.lic");` のように有効なライセンスファイルを適用してください。  
- **スライス分割が正しくない:** `splitBy` プロパティが `SplitBy.Percentage` に設定され、`secondPieSize` が 0〜100 の範囲の値であることを確認してください。  
- **データが表示されない:** チャートのシリーズに少なくとも1つのデータポイントが含まれていることを確認してください。含まれていない場合、チャートは空になります。

## よくある質問

`IChart` はスライドに追加できるチャートオブジェクトを表します。

**Q: 単一のプレゼンテーションで複数のチャートを生成できますか？**  
A: はい、各スライドまたは場所ごとに新しい `IChart` をインスタンス化できます。APIはファイルあたり無制限のチャートオブジェクトを許可します。

`SaveFormat.Pdf` は保存時のPDF出力フォーマットを指定します。

**Q: Aspose.SlidesはPDFとしての保存もサポートしていますか？**  
A: もちろんです。`presentation.save("output.pdf", SaveFormat.Pdf)` を呼び出すことで、同じスライドデッキをPDFにエクスポートできます。

`IPortion` は円グラフの個々のスライスを表します。

**Q: Pie of Pieチャートが処理できるデータポイントの最大数は？**  
A: ライブラリはシリーズあたり最大 **10,000** のデータポイントをサポートしており、利用可能なメモリが唯一の制限です。

**Q: 個々のスライスの色をカスタマイズできますか？**  
A: はい、`chart.getChartData().getSeries().get_Item(0).getPortions()` で各 `IPortion` にアクセスし、`portion.getFillFormat().setSolidFillColor(Color.getRGB(...))` で色を設定できます。

**Q: 生成した PPTX をウェブアプリケーションに埋め込むには？**  
A: ファイルを保存した後、`HttpServletResponse` を使用し、`Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation` を設定してクライアントに直接ストリームします。

## 結論

これで、Aspose.Slides for Java を使用して **PowerPointにチャートを追加** するための完全な本番対応レシピが手に入りました。さまざまな分割閾値、ラベル形式、カラースキームを試してブランドガイドラインに合わせてください。次は、積み上げ棒グラフやレーダーなど他のチャートタイプを探索し、自动化スライドデッキをさらに充実させましょう。

---

**最終更新日:** 2026-07-17  
**テスト環境:** Aspose.Slides for Java 24.12  
**作者:** Aspose

## 関連チュートリアル

- [動的チャート作成 Java – Aspose.Slides の PowerPoint チャートチュートリアル](/slides/java/charts-graphs/)
- [Aspose.Slides for JavaでPowerPointに円グラフを追加する方法](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Aspose.Slides for Javaを使用してPowerPointにチャートを追加する方法：ステップバイステップガイド](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}