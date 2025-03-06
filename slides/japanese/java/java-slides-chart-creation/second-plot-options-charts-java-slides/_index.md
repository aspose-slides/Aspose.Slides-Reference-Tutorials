---
title: Java スライドのチャートの 2 番目のプロット オプション
linktitle: Java スライドのチャートの 2 番目のプロット オプション
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java スライドのグラフをカスタマイズする方法を学びます。2 番目のプロット オプションを調べて、プレゼンテーションを強化します。
weight: 12
url: /ja/java/chart-creation/second-plot-options-charts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java スライドのチャートの 2 番目のプロット オプションの紹介

このチュートリアルでは、Aspose.Slides for Java を使用してチャートに 2 番目のプロット オプションを追加する方法について説明します。2 番目のプロット オプションを使用すると、特に円グラフなどのシナリオでチャートの外観と動作をカスタマイズできます。これを実現するための手順とソース コードの例を示します。 

## 前提条件
始める前に、Aspose.Slides for Java がインストールされ、Java プロジェクトに設定されていることを確認してください。

## ステップ1: プレゼンテーションを作成する
まず、新しいプレゼンテーションを作成しましょう。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

## ステップ2: スライドにグラフを追加する
次に、スライドにグラフを追加します。この例では、円グラフを作成します。

```java
//スライドにグラフを追加する
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## ステップ3: グラフのプロパティをカスタマイズする
ここで、2 番目のプロット オプションを含む、グラフのさまざまなプロパティを設定しましょう。

```java
//最初の系列のデータラベルを表示する
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

//2番目の円グラフのサイズを設定します（パーセンテージ）
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

//割合でパイを分割する
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

//分割位置を設定する
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## ステップ4: プレゼンテーションを保存する
最後に、グラフと 2 番目のプロット オプションを含むプレゼンテーションを保存します。

```java
//プレゼンテーションをディスクに書き込む
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## 番目のプロット オプションの完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
//スライドにグラフを追加する
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
//異なるプロパティを設定する
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
//プレゼンテーションをディスクに書き込む
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して、Java スライドのグラフに 2 番目のプロット オプションを追加する方法を学習しました。さまざまなプロパティをカスタマイズしてグラフの外観と機能を強化し、プレゼンテーションをより情報豊富で視覚的に魅力的なものにすることができます。

## よくある質問

### 円グラフの 2 番目の円グラフのサイズを変更するにはどうすればよいですか?

円グラフの2番目の円グラフのサイズを変更するには、`setSecondPieSize`上記のコード例に示すように、メソッドを使用します。値を調整して、サイズをパーセンテージで指定します。

### 何が`PieSplitBy` control in a Pie of Pie chart?

の`PieSplitBy`プロパティは円グラフの分割方法を制御します。`PieSplitType.ByPercentage`または`PieSplitType.ByValue`それぞれパーセンテージまたは特定の値でチャートを分割します。

### 円グラフの分割位置を設定するにはどうすればよいですか?

円グラフの分割位置は、`setPieSplitPosition`方法。値を調整して目的の位置を指定します。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
