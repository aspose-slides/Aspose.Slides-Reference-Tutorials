---
date: '2026-03-23'
description: Aspose.Slides for Java を使用して、マーカー付きの折れ線グラフを作成し、第二系列を追加し、PowerPoint プレゼンテーションで
  null データを処理する方法を学びましょう。
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: Aspose.Slides for Java の使い方：デフォルトマーカー付き折れ線グラフの作成
url: /ja/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java を使用してデフォルトマーカー付き折れ線グラフを作成する

## Introduction
Aspose を **どのように使用して PowerPoint の自動生成を行うか** をお探しなら、ここが最適です。このチュートリアルでは、**マーカー付き折れ線グラフ** の作成、2 番目の系列の追加、null データの処理を Aspose.Slides for Java で実装する手順を解説します。最後まで読めば、PowerPoint を手動で開くことなく、プロフェッショナルな外観のグラフを生成できるコードスニペットが手に入ります。

### Quick Answers
- **必要なライブラリは？** Aspose.Slides for Java（最新バージョン推奨）  
- **2 番目の系列を追加できるか？** はい – API で簡単に複数系列を追加できます。  
- **null データポイントはどう扱うか？** セルの値に `null` を設定すれば、グラフはそのポイントをスキップします。  
- **Maven が必要か？** Maven でも Gradle でも構いません。下記 *aspose slides maven* セクションをご参照ください。  
- **ライセンスは必須か？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。

## How to Use Aspose.Slides for Java to Create Line Charts
プログラムでグラフを作成すれば、手作業でのフォーマットに費やす時間を大幅に削減でき、プレゼンテーション全体の一貫性も保証できます。**PowerPoint グラフ作成機能** をレポートツールに組み込む場合や、スライドデッキをリアルタイムで生成する場合でも、Aspose.Slides は Java コードからフルコントロールを提供します。

## Prerequisites
開始する前に、開発環境が整っていることを確認してください。

1. **ライブラリと依存関係**
   - Aspose.Slides for Java ライブラリ（バージョン 25.4 推奨） – これが *aspose slides maven* シナリオをカバーします。  
   - Java Development Kit (JDK) バージョン 16 以上。
2. **環境設定**
   - Maven または Gradle に対応した IDE。  
   - トライアル以外で実行する場合は有効な Aspose ライセンスファイル。
3. **前提知識**
   - 基本的な Java プログラミング。  
   - Maven または Gradle のビルドファイルに慣れていること。

## Setting Up Aspose.Slides for Java
### Maven
`pom.xml` に以下の依存関係を追加してください:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
`build.gradle` に以下を追加してください:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Direct Download
あるいは、最新バージョンを [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) からダウンロードできます。

**ライセンス取得手順:**
- 無料トライアルは [free trial page](https://releases.aspose.com/slides/java/) へ。  
- 一時ライセンスは [temporary license page](https://purchase.aspose.com/temporary-license/) から取得。  
- 正式ライセンスは [purchase portal](https://purchase.aspose.com/buy) で購入してください。

**基本的な初期化:**
Java アプリケーションで Aspose.Slides を初期化する例:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

それでは、グラフ作成に進みましょう！

## Implementation Guide
### Feature 1: Chart Creation with Default Markers
このセクションでは、トレンドライン上の個々のデータポイントを強調表示できる **マーカー付き折れ線グラフ** の作成方法を示します。

#### Adding a Line Chart
マーカー付き折れ線グラフを追加するには:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### Clearing Series and Categories
新規作成のためにクリアするには:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### Feature 2: Adding Series and Categories
系列とカテゴリを追加することは、グラフに意味のあるデータを入力する上で重要です。

#### Creating a New Series
「Series 1」という名前の新しい系列を追加するには:
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Populating Categories and Data Points
カテゴリと対応するデータポイントを追加するには:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### Feature 3: Adding Second Series and Populating Data Points
追加の系列を加えることで、分析の深みが増します。

#### Creating and Populating a Second Series
「Series 2」を追加するには:
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### Feature 4: Configuring Chart Legend
凡例を設定すると、特に **2 番目の系列を追加** したときにグラフの可読性が向上します。

#### Adjusting Legend Settings
凡例を構成するには:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### Feature 5: Saving the Presentation
グラフが完成したら、**PowerPoint グラフ** ファイルとして保存し、共有や追加編集ができるようにします。

```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## Practical Applications
1. **ビジネスレポート:** 四半期ごとの財務トレンドを示すマーカー付き折れ線グラフ。  
2. **データ分析:** 各測定ポイントをマーカーでハイライトした実験データの可視化。  
3. **教育資料:** プロセスの段階的変化を示すスライド作成。  
4. **プロジェクト管理:** 重要日付を示すマーカーでマイルストーンをタイムラインに表示。  
5. **マーケティングプレゼン:** キャンペーンのパフォーマンス急増を明確なマーカーで表現。

## Common Issues and Solutions
- **null データポイントでエラーが出る:** セル値に `null` を渡す（例参照） – Aspose はそのポイントを単に省略します。  
- **マーカーが表示されない:** `ChartType.LineWithMarkers` を使用し、`ChartType.Line` ではないことを確認。  
- **凡例がデータと重なる:** `chart.getLegend().setOverlay(false)` を設定して凡例を分離。

## Frequently Asked Questions

**Q: この手法を Web サービスでのチャート生成に利用できますか？**  
A: もちろんです。ライブラリはサーバーサイドを含む任意の Java 環境で動作します。

**Q: 開発ビルドでもライセンスは必要ですか？**  
A: 開発・テストは無料トライアルで可能です。商用環境では商用ライセンスが必要です。

**Q: 大規模データセットはどのように処理されますか？**  
A: API はデータを効率的にストリーム処理しますが、ファイルサイズが大きくなりすぎないようデータポイント数は適度に抑えてください。

**Q: 他のチャートタイプはサポートされていますか？**  
A: はい – Aspose.Slides は棒グラフ、円グラフ、散布図など多数のチャートタイプをサポートしています。

**Q: マーカーの形状や色はカスタマイズできますか？**  
A: 各データポイントの `Marker` プロパティを使用して、形状や色を変更できます。

## Conclusion
これで **Aspose を使用してデフォルトマーカー付き折れ線グラフを作成し、2 番目の系列を追加し、null データを処理し、PowerPoint ファイルとして保存** する方法が分かりました。これらのテクニックを活用すれば、レポート生成の自動化、データストーリーテリングの向上、プレゼンテーションの一貫性確保が実現できます。

さらに詳しくは、[official documentation](https://docs.aspose.com/slides/java/) をご覧いただくか、Stack Overflow などのコミュニティフォーラムに参加してください。

---

**Last Updated:** 2026-03-23  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}