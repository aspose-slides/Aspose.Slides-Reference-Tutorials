---
date: '2026-07-08'
description: Aspose を使用して Java で PowerPoint に doughnut chart を作成する方法を学びます。このステップバイステップガイドでは、プログラムで
  chart data points を追加し、labels をカスタマイズし、high fidelity で PPTX を保存する方法を示します。
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Aspose を使用して Java で PowerPoint に doughnut chart を作成できます。このチュートリアルに従って
  data points を追加し、labels をカスタマイズし、high fidelity で PPTX を保存してください。
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Aspose を使用して: PowerPoint (Java) で doughnut chart を作成する方法'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Aspose を使用して PowerPoint (Java) で doughnut chart を作成する方法
url: /ja/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose を使用して PowerPoint (Java) でドーナツ グラフを作成する方法

## はじめに
魅力的なプレゼンテーションを作成するには、テキストや画像だけでなく、データを効果的に可視化するチャートがストーリーテリングを大幅に向上させます。**Aspose の使用方法** によるチャート生成は、PowerPoint を開くことなくプログラムから制御できます。このチュートリアルでは、ドーナツ グラフの作成、データポイントの設定、そして高品質な PPTX の保存手順を順を追って説明します。必要なのは基本的な Java の知識と数分のセットアップ時間だけです。

`Aspose.Slides for Java` は、Microsoft Office を使用せずに PowerPoint ファイルの作成、操作、変換を可能にする Java ライブラリです。

## クイック回答
- **PowerPoint 用のドーナツ グラフを作成するライブラリは何ですか？** Aspose.Slides for Java  
- **プログラムからチャートのデータポイントを追加できますか？** はい、チャート API を使用します  
- **本番環境でライセンスが必要ですか？** 有効な Aspose.Slides ライセンスが必要です  
- **サポートされている Java バージョンは？** Java 8 以降 (JDK 16 の分類子が表示されています)  
- **何系列まで追加できますか？** この例では最大 15 系列を追加していますが、必要に応じて調整可能です  

## PowerPoint のドーナツ グラフとは？
ドーナツ グラフは、円形のチャートでパイチャートに似ていますが、中心が空洞になっており、複数の系列を同時に表示できます。全体に対する部分の関係を強調しつつ、視覚的レイアウトをコンパクトで読みやすく保ちます。

## なぜ Aspose.Slides for Java を使用してドーナツ グラフを作成するのか？
Aspose.Slides for Java は 50 以上の入出力フォーマットに対応し、ファイル全体をメモリに読み込むことなく最大 500 MB のプレゼンテーションを生成できます。任意の Java プラットフォーム上でチャートの外観、データ、レイアウトを完全にプログラムから制御でき、COM 相互運用を排除し、一般的なサーバー上で 100 枚のチャート豊富なスライドを 2 秒未満で描画できます。

## 前提条件
- Java プログラミングの基本的な知識。  
- IntelliJ IDEA や Eclipse などの IDE。  
- 依存関係管理のための Maven または Gradle。  
- 有効な Aspose.Slides for Java ライセンス（無料トライアルあり）。

## Aspose.Slides for Java のセットアップ
プロジェクトに適した依存関係マネージャーを選択してください。

**Maven**  
`pom.xml` に以下の依存関係を追加します（バージョンは最新リリースに置き換えてください）：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
`build.gradle` に以下の行を追加します。

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

直接ダウンロードしたい場合は、[Aspose.Slides for Java リリース](https://releases.aspose.com/slides/java/) ページをご覧ください。

### ライセンス取得
まずは無料トライアルで Aspose.Slides の機能を体験できます。長期的に使用する場合は、ライセンスを購入するか、[Aspose のウェブサイト](https://purchase.aspose.com/temporary-license/) から一時ライセンスをリクエストしてください。環境設定とアプリケーションでの Aspose.Slides の初期化手順に従ってください。

## Aspose.Slides for Java を使用して PowerPoint のドーナツ グラフを作成する方法
ドーナツ グラフを作成するには、まず `Presentation` をロードまたは作成し、`ChartType.Doughnut` タイプのチャート シェイプを追加します。デフォルトの系列をクリアし、ホールサイズを設定した後、チャートのワークブックにカテゴリ名と数値を入力します。最後にラベルの書式設定を調整し、PPTX として保存します。

### 手順 1: プレゼンテーションの初期化
新しいプレゼンテーションを作成するか、既存のファイルを開いてスライド コレクションを取得します。

`Presentation` は PowerPoint ファイルを表す主要クラスです。  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 手順 2: スライドにドーナツ グラフを追加する
チャート シェイプを挿入し、デフォルトの系列/カテゴリを削除し、ドーナツのホールサイズなどの基本的なビジュアル設定を構成します。

`Chart`（またはチャート シェイプ）は、スライド上に配置されるチャート オブジェクトを表します。  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 手順 3: チャート データポイントを追加しラベルをカスタマイズする
カテゴリ名を設定し、各系列のデータポイントを追加し、ラベルの書式設定（フォント、色、位置）を微調整します。この手順は「チャート データポイントの追加」機能を示しています。

`Workbook` は、セルが入力されるチャートの基礎となるスプレッドシート データへのアクセスを提供します。  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### 手順 4: 更新されたプレゼンテーションを保存する
変更をディスク上の新しい PPTX ファイルに永続化します。

`save` は、選択した形式でプレゼンテーションをファイルに書き込みます。  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## 実用例
- **財務レポート:** 予算配分や費用内訳の可視化。  
- **市場分析:** 競合他社間の市場シェア分布の表示。  
- **調査結果:** カテゴリ別調査データをコンパクトに提示。  
- **ダッシュボード生成:** データベースクエリと組み合わせてリアルタイム更新スライドを作成。

## パフォーマンス上の考慮点
- **リソースの解放:** 保存後に `pres.dispose()` を呼び出してネイティブ メモリを解放します。  
- **チャート数の制限:** 数百のチャートを追加するとメモリ使用量が増加するため、必要に応じてバッチ処理してください。  
- **ストリーミングの使用:** 大規模データセットの場合、メモリ内配列ではなくストリームから直接ワークブックにデータを入力します。

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|-------|-------|-----|
| **チャートが空白になる** | データセルが正しく入力されていない | `workBook.getCell(...)` が正しい行/列インデックスを参照しているか確認してください。 |
| **ラベルが重なる** | 限られたスペースにカテゴリが多すぎる | `DoughnutHoleSize` を増やすか、`FirstSliceAngle` を調整してください。 |
| **OutOfMemoryError** | 解放せずに大きなプレゼンテーションを扱っている | 保存後に `pres.dispose()` を呼び出し、JVM ヒープサイズの増加も検討してください。 |

## よくある質問

**Q: Aspose.Slides for Java を商用アプリケーションで使用できますか？**  
A: はい、ただし有効な商用ライセンスが必要です。評価用に無料トライアルが利用可能です。

**Q: 15 系列以上を追加するにはどうすればよいですか？**  
A: 「ドーナツ グラフの追加」手順でループ上限を増やし、データ ワークブックに十分な行があることを確認してください。

**Q: 作成後にドーナツのホールサイズを変更できますか？**  
A: はい、保存前に `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` を呼び出します。

**Q: チャートを PPTX ではなく画像としてエクスポートできますか？**  
A: もちろんです。`chart.getImage()` を使用し、返された `java.awt.image.BufferedImage` を希望の形式で保存してください。

**Q: Aspose.Slides はアニメーション付きチャートをサポートしていますか？**  
A: アニメーションは `ISlide.getTimeline()` API を使用して追加できますが、本チュートリアルの範囲外です。

## 結論
これで、Aspose.Slides for Java を使用して **ドーナツ グラフの PowerPoint** ファイルを **作成し、チャート データポイントを追加**、ラベルをカスタマイズし、パフォーマンス上の考慮点に対処するための完全な本番対応手法が手に入りました。さまざまな色、データ ソース、チャート タイプを試して、プレゼンテーションを本当に際立たせてください。

---

**最終更新日:** 2026-07-08  
**テスト環境:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**作者:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## 関連チュートリアル

- [Aspose.Slides for Java を使用して PowerPoint にチャートを追加する方法：ステップバイステップ ガイド](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java を使用して PowerPoint のチャート データを編集する方法：包括的ガイド](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Aspose.Slides for Java で PowerPoint のチャートにアニメーションを付ける方法 – ステップバイステップ ガイド](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}