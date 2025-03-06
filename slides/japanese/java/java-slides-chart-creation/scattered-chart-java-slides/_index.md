---
title: Java スライドの散布図
linktitle: Java スライドの散布図
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して Java で散布図を作成する方法を学びます。プレゼンテーションでデータを視覚化するための Java ソース コードを使用したステップバイステップ ガイドです。
type: docs
weight: 11
url: /ja/java/chart-creation/scattered-chart-java-slides/
---

## Aspose.Slides for Java の散布図の概要

このチュートリアルでは、Aspose.Slides for Java を使用して散布図を作成する手順を説明します。散布図は、2 次元平面上のデータ ポイントを視覚化するのに役立ちます。ステップ バイ ステップの手順を示し、便宜上 Java ソース コードも含めます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. [Java 用 Aspose.Slides](https://products.aspose.com/slides/java)インストールされました。
2. Java 開発環境をセットアップしました。

## ステップ1: プレゼンテーションを初期化する

まず、必要なライブラリをインポートして新しいプレゼンテーションを作成します。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";

//ディレクトリがまだ存在しない場合は作成します。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

//新しいプレゼンテーションを作成する
Presentation pres = new Presentation();
```

## ステップ2: スライドを追加して散布図を作成する

次に、スライドを追加して散布図を作成します。`ScatterWithSmoothLines`この例ではチャートの種類です。

```java
//最初のスライドを取得する
ISlide slide = pres.getSlides().get_Item(0);

//散布図の作成
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## ステップ3: チャートデータを準備する

次に、散布図のデータを準備しましょう。それぞれ複数のデータ ポイントを持つ 2 つのシリーズを追加します。

```java
//デフォルトのグラフデータワークシートインデックスを取得する
int defaultWorksheetIndex = 0;

//チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

//デモシリーズを削除
chart.getChartData().getSeries().clear();

//最初のシリーズを追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

//最初のチャートシリーズを見てみましょう
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

//最初のシリーズにデータポイントを追加する
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

//シリーズの種類を編集する
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); //マーカーのサイズを変更する
series.getMarker().setSymbol(MarkerStyleType.Star); //マーカーシンボルの変更

//2番目のチャートシリーズを見てみましょう
series = chart.getChartData().getSeries().get_Item(1);

//2番目のシリーズにデータポイントを追加する
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

//2番目のシリーズのマーカースタイルを変更する
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## ステップ4: プレゼンテーションを保存する

最後に、散布図を含むプレゼンテーションを PPTX ファイルに保存します。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

これで完了です。Aspose.Slides for Java を使用して散布図を正常に作成できました。この例をさらにカスタマイズして、特定のデータとデザインの要件に合わせることができます。

## Java スライドの散布図の完全なソース コード
```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//ディレクトリがまだ存在しない場合は作成します。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//デフォルトのチャートを作成する
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
//デフォルトのグラフデータワークシートインデックスを取得する
int defaultWorksheetIndex = 0;
//チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//デモシリーズを削除
chart.getChartData().getSeries().clear();
//新しいシリーズを追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
//最初のチャートシリーズ
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//そこに新しいポイント（1:3）を追加します。
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
//新しいポイントを追加 (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
//シリーズの種類を編集する
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
//チャートシリーズマーカーの変更
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
//第2チャートシリーズ
series = chart.getChartData().getSeries().get_Item(1);
//そこに新しいポイント（5:2）を追加します。
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
//新しいポイントを追加 (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
//新しいポイントを追加 (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
//新しいポイントを追加 (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
//チャートシリーズマーカーの変更
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して散布図を作成する手順について説明しました。散布図は、2 次元空間でデータ ポイントを視覚化する強力なツールであり、複雑なデータ関係の分析と理解を容易にします。

## よくある質問

### グラフの種類を変更するにはどうすればよいですか?

チャートの種類を変更するには、`setType`チャートシリーズにメソッドを適用し、希望するチャートタイプを指定します。たとえば、`series.setType(ChartType.Line)`系列を折れ線グラフに変更します。

### マーカーのサイズとスタイルをカスタマイズするにはどうすればよいですか?

マーカーのサイズとスタイルを変更するには、`getMarker`シリーズにメソッドを適用し、サイズとシンボルのプロパティを設定します。例:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Aspose.Slides for Java のドキュメントで、さらに多くのカスタマイズ オプションを自由に調べてください。

交換を忘れないでください`"Your Document Directory"`プレゼンテーションを保存する実際のパスを入力します。