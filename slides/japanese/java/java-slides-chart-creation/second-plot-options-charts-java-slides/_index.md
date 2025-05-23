---
"description": "Aspose.Slides for Java を使用して、Java スライドのグラフをカスタマイズする方法を学びましょう。セカンドプロットオプションを活用して、プレゼンテーションの質を高めましょう。"
"linktitle": "Javaスライドのチャートの2番目のプロットオプション"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドのチャートの2番目のプロットオプション"
"url": "/ja/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドのチャートの2番目のプロットオプション


## Javaスライドのチャートの2番目のプロットオプションの紹介

このチュートリアルでは、Aspose.Slides for Java を使用してグラフにセカンドプロットオプションを追加する方法を説明します。セカンドプロットオプションを使用すると、特に円グラフのようなシナリオにおいて、グラフの外観と動作をカスタマイズできます。これを実現するための手順とソースコード例を段階的に紹介します。 

## 前提条件
始める前に、Aspose.Slides for Java がインストールされ、Java プロジェクトに設定されていることを確認してください。

## ステップ1：プレゼンテーションを作成する
まず、新しいプレゼンテーションを作成しましょう。

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

## ステップ2: スライドにグラフを追加する
次に、スライドにグラフを追加します。この例では、円グラフと円グラフを作成します。

```java
// スライドにグラフを追加する
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## ステップ3: グラフのプロパティをカスタマイズする
ここで、2 番目のプロット オプションを含む、グラフのさまざまなプロパティを設定しましょう。

```java
// 最初の系列のデータラベルを表示する
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// 2番目の円グラフのサイズを設定する（パーセンテージ）
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// 円グラフをパーセンテージで分割する
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// 分割位置を設定する
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## ステップ4: プレゼンテーションを保存する
最後に、グラフと 2 番目のプロット オプションを含むプレゼンテーションを保存します。

```java
// プレゼンテーションをディスクに書き込む
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## 2番目のプロットオプションの完全なソースコード

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
// スライドにグラフを追加する
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// さまざまなプロパティを設定する
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// プレゼンテーションをディスクに書き込む
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して、Java スライドのグラフに 2 番目のプロットオプションを追加する方法を学習しました。さまざまなプロパティをカスタマイズすることで、グラフの外観と機能を強化し、プレゼンテーションをより情報豊かで魅力的なものにすることができます。

## よくある質問

### 円グラフの 2 番目の円グラフのサイズを変更するにはどうすればよいですか?

円グラフの2番目の円グラフのサイズを変更するには、 `setSecondPieSize` 上記のコード例に示すように、メソッドを使用します。値を調整して、サイズをパーセンテージで指定します。

### 何が `PieSplitBy` 円グラフの円グラフでコントロールしますか?

その `PieSplitBy` プロパティは円グラフの分割方法を制御します。次のいずれかに設定できます。 `PieSplitType.ByPercentage` または `PieSplitType.ByValue` それぞれパーセンテージまたは特定の値でチャートを分割します。

### 円グラフの分割位置を設定するにはどうすればよいでしょうか?

円グラフの分割位置を設定するには、 `setPieSplitPosition` 方法。値を調整して目的の位置を指定します。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}