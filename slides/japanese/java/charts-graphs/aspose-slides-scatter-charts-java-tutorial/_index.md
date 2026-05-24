---
date: '2026-02-24'
description: Aspose.Slides for Java を使用して散布図をカスタマイズする方法を学びましょう。このガイドでは、プレゼンテーション内で動的な散布図を作成し、スタイルを設定し、保存する手順を順に案内します。
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: JavaでAsposeの散布図をカスタマイズ
url: /ja/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java で Aspose の散布図をカスタマイズする

このチュートリアルでは、強力な Aspose.Slides for Java ライブラリを使用して **customize scatter chart aspose** を学びます。プロジェクトの設定、散布図の作成、シリーズタイプやマーカーの調整、最終的なプレゼンテーションの保存まで順を追って説明します。最後には、プログラムでプロフェッショナルな外観の散布図を生成し、ブランドやレポートの要件に合わせてすべてのビジュアル詳細を調整できるようになります。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Slides for Java (v25.4+)。  
- **サポートされている Java バージョンは？** JDK 8 以上。  
- **マーカーの形状を変更できますか？** はい – `MarkerStyleType` を使用して星形、円形などを選択できます。  
- **ファイルはどう保存しますか？** `pres.save("output.pptx", SaveFormat.Pptx)` を呼び出します。  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、製品版には商用ライセンスが必要です。

## “customize scatter chart aspose” とは何ですか？
Aspose で散布図をカスタマイズするとは、PowerPoint を手動で開くことなく、チャートのデータ、外観、動作をプログラムで定義することを意味します。ポイントの座標からマーカー記号まで、すべてをコードで設定できます。この手法は、レポートの自動化、データ駆動型プレゼンテーション、または繰り返し利用できる高品質な可視化が必要なあらゆるシナリオに最適です。

## Aspose.Slides で散布図をカスタマイズする理由
- **フルコントロール** – Java コードでシリーズタイプ、マーカースタイル、色などを変更できます。  
- **自動化** – ダッシュボードやバッチレポート向けに、リアルタイムで多数のチャートを生成できます。  
- **クロスプラットフォーム** – Java が動作する任意の OS で使用でき、Office のインストールは不要です。  
- **パフォーマンス** – 大規模データセットを効率的に処理できる軽量 API です。

## 前提条件
以下を用意して、チュートリアルを進めてください。

- **Aspose.Slides for Java** (v25.4 以上)。  
- **Java Development Kit (JDK)** 8 以上がインストールされていること。  
- 依存関係管理のための Maven または Gradle（または JAR を手動でダウンロード）  
- 基本的な Java の知識と、使用するビルドツールに慣れていること。

## Aspose.Slides for Java の設定
以下のいずれかの方法でライブラリをプロジェクトに統合します。

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

または最新リリースを [Aspose Releases](https://releases.aspose.com/slides/java/) から取得してください。

#### ライセンス取得
- **無料トライアル** – 30 日間の評価。  
- **一時ライセンス** – テスト期間の延長。  
- **フルライセンス** – 本番利用およびプレミアムサポート付き。

## 散布図 Aspose カスタマイズのステップバイステップガイド

### 1️⃣ Prepare a folder for your presentation files
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*重要な理由:* 出力フォルダーが存在することを確認することで、後で PPTX を保存するときに `FileNotFoundException` が発生するのを防げます。

### 2️⃣ Create a new presentation and grab the first slide
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
新しい `Presentation` はクリーンなキャンバスを提供します。最初のスライドにチャートを配置します。

### 3️⃣ Add a scatter chart with smooth lines
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` は滑らかな線の散布図を作成し、トレンドの可視化に最適です。

### 4️⃣ Clear any default series and add your own
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
デフォルトのシリーズを削除することで、表示するデータを完全にコントロールできます。

### 5️⃣ Populate the first series with data points
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` は X 値セルと Y 値セルを受け取り、散布図のポイントを一つずつ構築します。

### 6️⃣ Customize series type and marker appearance
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
ここでは、直線に切り替え、マーカーを拡大し、視覚的な明瞭さのために異なるシンボル（星形と円形）を選択することで **customize the scatter chart aspose** を行います。

### 7️⃣ Save the presentation
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
`Pptx` として保存することで、すべてのチャートカスタマイズが保持され、共有やさらに編集できる状態になります。

## カスタマイズされた散布図の一般的なユースケース
- **金融ダッシュボード** – 株価と取引量をプロット。  
- **科学研究** – 誤差マーカー付きの実験測定値を表示。  
- **プロジェクト管理** – タスクごとの計画と実績の工数を比較。  

## パフォーマンスのヒント
- 保存後に `Presentation` オブジェクト (`pres.dispose()`) を破棄して、ネイティブリソースを解放します。  
- 大規模データセットの場合、まずワークブックにデータを入力し、シリーズをバインドすることで UI の再描画を繰り返さないようにします。  
- 多数のシリーズを追加する際は、単一の `IChartDataWorkbook` インスタンスを再利用します。

## よくある質問

### マーカーの色を変更するには？
`series.getMarker().getFillFormat().setFillColor(Color)` を使用します。`Color` は `java.awt.Color` のインスタンスです（例: `Color.RED`）。

### 散布図に 2 系列以上追加できますか？
もちろんです。追加のシリーズごとに `chart.getChartData().getSeries().add(...)` を呼び出し、対応するデータポイントを設定してください。

### 各シリーズにカスタム凡例を設定できますか？
はい。シリーズを作成した後、`series.getLegend().setText("Your Legend Text")` を呼び出してデフォルト名を上書きします。

### チャートを PPTX ではなく画像としてエクスポートするには？
チャート設定後に `chart.getImage().save("chart.png", ImageFormat.Png)` を呼び出します。これにより単体の PNG ファイルが得られます。

### 散布点にアニメーションを付けたい場合は？
Aspose.Slides はアニメーション効果をサポートしています。`chart.getTimeline().getMainSequence().addEffect(...)` を使用して、チャート全体または個別のシリーズに出現や強調のアニメーションを追加できます。

---

**最終更新日:** 2026-02-24  
**テスト環境:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}