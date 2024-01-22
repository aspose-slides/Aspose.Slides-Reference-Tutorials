---
title: Java スライドのグラフの 2 番目のプロット オプション
linktitle: Java スライドのグラフの 2 番目のプロット オプション
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java Slides のグラフをカスタマイズする方法を学びます。 2 番目のプロット オプションを検討し、プレゼンテーションを強化します。
type: docs
weight: 12
url: /ja/java/chart-creation/second-plot-options-charts-java-slides/
---

## Java スライドのグラフの 2 番目のプロット オプションの概要

このチュートリアルでは、Aspose.Slides for Java を使用してグラフに 2 番目のプロット オプションを追加する方法を説明します。 2 番目のプロット オプションを使用すると、特に円グラフのようなシナリオで、グラフの外観と動作をカスタマイズできます。これを実現するための段階的な手順とソース コードの例を提供します。 

## 前提条件
始める前に、Aspose.Slides for Java がインストールされ、Java プロジェクトに設定されていることを確認してください。

## ステップ 1: プレゼンテーションを作成する
新しいプレゼンテーションを作成することから始めましょう。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
// Presentationクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

## ステップ 2: グラフをスライドに追加する
次に、スライドにグラフを追加します。この例では、円グラフを作成します。

```java
//スライドにグラフを追加する
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## ステップ 3: グラフのプロパティをカスタマイズする
次に、2 番目のプロット オプションを含む、グラフのさまざまなプロパティを設定しましょう。

```java
//最初のシリーズのデータ ラベルを表示する
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// 番目の円のサイズを設定します (パーセント単位)。
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

//円をパーセンテージで分割する
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

//スプリットの位置を設定する
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## ステップ 4: プレゼンテーションを保存する
最後に、グラフと 2 番目のプロット オプションを指定してプレゼンテーションを保存します。

```java
//プレゼンテーションをディスクに書き込む
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## 番目のプロット オプションの完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
// Presentationクラスのインスタンスを作成する
Presentation presentation = new Presentation();
//スライドにグラフを追加する
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
//さまざまなプロパティを設定する
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
//プレゼンテーションをディスクに書き込む
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して Java Slides のグラフに 2 番目のプロット オプションを追加する方法を学習しました。さまざまなプロパティをカスタマイズしてグラフの外観と機能を強化し、プレゼンテーションをより有益で視覚的に魅力的なものにすることができます。

## よくある質問

### 円グラフの 2 番目の円のサイズを変更するにはどうすればよいですか?

円グラフの 2 番目の円のサイズを変更するには、`setSecondPieSize`上記のコード例に示されているメソッド。値を調整してサイズをパーセンテージで指定します。

### どういうことですか`PieSplitBy` control in a Pie of Pie chart?

の`PieSplitBy`プロパティは、円グラフの分割方法を制御します。どちらかに設定できます`PieSplitType.ByPercentage`または`PieSplitType.ByValue`グラフをパーセンテージまたは特定の値ごとにそれぞれ分割します。

### 円グラフで分割の位置を設定するにはどうすればよいですか?

円グラフの分割の位置は、`setPieSplitPosition`方法。値を調整して希望の位置を指定します。