---
title: Java スライドのチャートトレンドライン
linktitle: Java スライドのチャートトレンドライン
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java スライドにさまざまなトレンド ラインを追加する方法を学びます。効果的なデータ視覚化のためのコード例を含むステップ バイ ステップ ガイド。
weight: 15
url: /ja/java/data-manipulation/chart-trend-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java スライドのチャートトレンドライン


## Java スライドでのチャートトレンドラインの紹介: ステップバイステップガイド

この包括的なガイドでは、Aspose.Slides for Java を使用して Java スライドでチャート トレンド ラインを作成する方法について説明します。チャート トレンド ラインはプレゼンテーションに貴重な追加要素となり、データの傾向を効果的に視覚化して分析するのに役立ちます。わかりやすい説明とコード例を使用して、プロセスを順を追って説明します。

## 前提条件

チャートのトレンド ラインの作成に進む前に、次の前提条件が満たされていることを確認してください。

- Java開発環境
- Aspose.Slides for Java ライブラリ
- お好みのコードエディタ

## ステップ1: 開始する

まず、必要な環境を設定し、新しいプレゼンテーションを作成しましょう。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//ディレクトリがまだ存在しない場合は作成します。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
//空のプレゼンテーションを作成しています
Presentation pres = new Presentation();
```

プレゼンテーションを初期化したので、集合縦棒グラフを追加する準備ができました。

```java
//集合縦棒グラフの作成
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## ステップ2: 指数トレンドラインの追加

まず、チャート シリーズに指数トレンド ラインを追加してみましょう。

```java
//チャートシリーズ 1 に指数トレンド ラインを追加する
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## ステップ3: 線形トレンドラインの追加

次に、チャート シリーズに線形トレンド ラインを追加します。

```java
//チャートシリーズ 1 に線形トレンド ラインを追加する
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## ステップ4: 対数トレンドラインの追加

ここで、別のチャート シリーズに対数トレンド ラインを追加してみましょう。

```java
//チャートシリーズ 2 に対数トレンド ラインを追加する
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## ステップ5: 移動平均トレンドラインの追加

移動平均トレンドラインを追加することもできます。

```java
//チャートシリーズ2に移動平均トレンドラインを追加する
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## ステップ6: 多項式トレンドラインの追加

多項式トレンドラインの追加:

```java
//チャートシリーズ 3 に多項式トレンド ラインを追加する
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## ステップ7: パワートレンドラインの追加

最後に、パワートレンドラインを追加しましょう。

```java
//チャートシリーズ 3 にパワートレンドラインを追加する
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## ステップ8: プレゼンテーションを保存する

チャートにさまざまなトレンド ラインを追加したので、プレゼンテーションを保存しましょう。

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

おめでとうございます! Aspose.Slides for Java を使用して、Java スライドでさまざまな種類のトレンド ラインを含むプレゼンテーションを正常に作成しました。

## Java スライドのチャートトレンドラインの完全なソースコード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//ディレクトリがまだ存在しない場合は作成します。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
//空のプレゼンテーションを作成しています
Presentation pres = new Presentation();
//集合縦棒グラフの作成
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
//チャートシリーズ 1 に指数トレンド ラインを追加する
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
//チャートシリーズ 1 に線形トレンド ラインを追加する
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
//チャートシリーズ 2 に対数トレンド ラインを追加する
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
//チャートシリーズ2に移動平均トレンドラインを追加する
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
//チャートシリーズ 3 に多項式トレンド ラインを追加する
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
//チャートシリーズ 3 にパワートレンドラインを追加する
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
//プレゼンテーションを保存しています
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides for Java ライブラリを使用して、Java スライドのグラフにさまざまな種類のトレンド ラインを追加する方法を学習しました。データ分析に取り組んでいる場合でも、情報豊富なプレゼンテーションを作成している場合でも、トレンドを視覚化する機能は強力なツールになります。

## よくある質問

### Aspose.Slides for Java でトレンド ラインの色を変更するにはどうすればよいですか?

トレンドラインの色を変更するには、`getSolidFillColor().setColor(Color)`線形トレンド ラインを追加する例に示すように、この方法を使用します。

### 1 つのチャート シリーズに複数のトレンド ラインを追加できますか?

はい、1つのチャートシリーズに複数のトレンドラインを追加できます。`getTrendLines().add()`追加するトレンド ラインごとにメソッドを選択します。

### Aspose.Slides for Java のグラフからトレンド ラインを削除するにはどうすればよいですか?

チャートからトレンドラインを削除するには、`removeAt(int index)`メソッドでは、削除するトレンド ラインのインデックスを指定します。

### トレンドライン方程式の表示をカスタマイズすることは可能ですか?

はい、トレンドライン方程式の表示をカスタマイズするには、`setDisplayEquation(boolean)`例に示すように、この方法を使用します。

### Aspose.Slides for Java のその他のリソースや例にアクセスするにはどうすればよいでしょうか?

 Aspose.Slides for Javaの追加のリソース、ドキュメント、およびサンプルは、[Aspose ウェブサイト](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
