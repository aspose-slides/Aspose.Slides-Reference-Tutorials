---
title: Java スライドのグラフの傾向線
linktitle: Java スライドのグラフの傾向線
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java スライドにさまざまな傾向線を追加する方法を学びます。効果的なデータ視覚化のためのコード例を含むステップバイステップのガイド。
type: docs
weight: 15
url: /ja/java/data-manipulation/chart-trend-lines-java-slides/
---

## Java スライドでのグラフの傾向線の紹介: ステップバイステップ ガイド

この包括的なガイドでは、Aspose.Slides for Java を使用して Java Slides でチャートの傾向線を作成する方法を説明します。グラフの傾向線はプレゼンテーションに貴重な追加機能を提供し、データの傾向を効果的に視覚化して分析するのに役立ちます。わかりやすい説明とコード例を使用してプロセスを説明します。

## 前提条件

チャートの傾向線の作成に入る前に、次の前提条件が満たされていることを確認してください。

- Java開発環境
- Java ライブラリの Aspose.Slides
- 好みのコードエディター

## ステップ 1: はじめに

まずは必要な環境をセットアップし、新しいプレゼンテーションを作成しましょう。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//ディレクトリが存在しない場合は作成します。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
//空のプレゼンテーションの作成
Presentation pres = new Presentation();
```

プレゼンテーションを初期化したので、集合縦棒グラフを追加する準備が整いました。

```java
//集合縦棒グラフの作成
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## ステップ 2: 指数近似曲線を追加する

まず、指数関数的なトレンド ラインをグラフ シリーズに追加しましょう。

```java
//チャート シリーズ 1 に指数関数的なトレンド ラインを追加する
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## ステップ 3: 線形傾向線の追加

次に、一連のグラフに線形傾向線を追加します。

```java
//チャート シリーズ 1 に線形トレンド ラインを追加
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## ステップ 4: 対数傾向線の追加

次に、対数トレンド ラインを別のグラフ シリーズに追加してみましょう。

```java
//チャート シリーズ 2 に対数トレンド ラインを追加
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## ステップ 5: 移動平均傾向線の追加

移動平均トレンド ラインを追加することもできます。

```java
//チャート シリーズ 2 に移動平均トレンド ラインを追加
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## ステップ 6: 多項式傾向線の追加

多項式近似曲線を追加します。

```java
//チャート シリーズ 3 に多項式トレンド ラインを追加
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## ステップ 7: 電力トレンド ラインの追加

最後に、パワー トレンド ラインを追加しましょう。

```java
//チャート シリーズ 3 にパワー トレンド ラインを追加
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## ステップ 8: プレゼンテーションを保存する

グラフにさまざまな傾向線を追加したので、プレゼンテーションを保存しましょう。

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

おめでとう！ Aspose.Slides for Java を使用して、Java Slides でさまざまなタイプの傾向線を含むプレゼンテーションを作成することができました。

## Java スライドのチャート傾向線の完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//ディレクトリが存在しない場合は作成します。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
//空のプレゼンテーションの作成
Presentation pres = new Presentation();
//集合縦棒グラフの作成
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
//チャート シリーズ 1 にポテンシャル トレンド ラインを追加
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
//チャート シリーズ 1 に線形トレンド ラインを追加
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
//チャート シリーズ 2 に対数トレンド ラインを追加
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
//チャート シリーズ 2 に移動平均トレンド ラインを追加
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
//チャート シリーズ 3 に多項式トレンド ラインを追加
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
//チャート シリーズ 3 にパワー トレンド ラインを追加
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
//プレゼンテーションの保存
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides for Java ライブラリを使用して、Java Slides のグラフにさまざまなタイプの傾向線を追加する方法を学習しました。データ分析に取り組んでいる場合でも、有益なプレゼンテーションを作成している場合でも、傾向を視覚化する機能は強力なツールとなります。

## よくある質問

### Aspose.Slides for Java で傾向線の色を変更するにはどうすればよいですか?

傾向線の色を変更するには、`getSolidFillColor().setColor(Color)`直線トレンド ラインを追加する例に示すように、メソッドを使用します。

### 単一のグラフ シリーズに複数の傾向線を追加できますか?

はい、複数の傾向線を 1 つのグラフ シリーズに追加できます。電話するだけです`getTrendLines().add()`追加するトレンドラインごとにメソッドを追加します。

### Aspose.Slides for Java のグラフから傾向線を削除するにはどうすればよいですか?

チャートから傾向線を削除するには、`removeAt(int index)`メソッドを使用して、削除する傾向線のインデックスを指定します。

### 傾向線の方程式の表示をカスタマイズすることはできますか?

はい、傾向線の方程式の表示をカスタマイズできます。`setDisplayEquation(boolean)`例で示したように、メソッドを使用します。

### Aspose.Slides for Java のその他のリソースや例にアクセスするにはどうすればよいですか?

 Aspose.Slides for Java の追加リソース、ドキュメント、例には、[Aspose ウェブサイト](https://reference.aspose.com/slides/java/).