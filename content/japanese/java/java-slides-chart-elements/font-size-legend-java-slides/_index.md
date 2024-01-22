---
title: Java スライドのフォント サイズの凡例
linktitle: Java スライドのフォント サイズの凡例
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint プレゼンテーションを強化します。凡例のフォント サイズなどをカスタマイズする方法については、ステップバイステップ ガイドをご覧ください。
type: docs
weight: 13
url: /ja/java/chart-elements/font-size-legend-java-slides/
---

## Java スライドのフォント サイズ凡例の概要

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint スライドの凡例のフォント サイズをカスタマイズする方法を学習します。このタスクを達成するための段階的な手順とソース コードを提供します。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがインストールされ、Java プロジェクトに設定されていることを確認してください。ライブラリはからダウンロードできます[ここ](https://releases.aspose.com/slides/java/).

## ステップ 1: プレゼンテーションを初期化する

まず、必要なクラスをインポートし、PowerPoint プレゼンテーションを初期化します。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

交換する`"Your Document Directory"`PowerPoint ファイルへの実際のパスを含めます。

## ステップ 2: グラフを追加する

次に、スライドにグラフを追加し、凡例のフォント サイズを設定します。

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

このコードでは、最初のスライドに集合縦棒グラフを作成し、凡例テキストのフォント サイズを 20 ポイントに設定します。調整できます`setFontHeight`必要に応じて値を変更してフォント サイズを変更します。

## ステップ 3: 軸の値をカスタマイズする

次に、グラフの縦軸の値をカスタマイズしましょう。

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

ここでは縦軸の最小値と最大値を設定します。データ要件に応じて値を変更できます。

## ステップ 4: プレゼンテーションを保存する

最後に、変更したプレゼンテーションを新しいファイルに保存します。

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

このコードは、変更されたプレゼンテーションを指定されたディレクトリに「output.pptx」として保存します。

## Java スライドのフォント サイズ凡例の完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

Aspose.Slides for Java を使用して、Java PowerPoint スライドの凡例のフォント サイズを正常にカスタマイズできました。 Aspose.Slides の機能をさらに探索して、インタラクティブで視覚的に魅力的なプレゼンテーションを作成できます。

## よくある質問

### グラフ内の凡例テキストのフォント サイズを変更するにはどうすればよいですか?

グラフ内の凡例テキストのフォント サイズを変更するには、次のコードを使用できます。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

このコードでは、グラフを作成し、凡例テキストのフォント サイズを 20 ポイントに設定します。調整できます`setFontHeight`値を指定してフォントサイズを変更します。

### グラフ内の凡例の他のプロパティをカスタマイズできますか?

はい、Aspose.Slides を使用して、グラフ内の凡例のさまざまなプロパティをカスタマイズできます。カスタマイズできる共通プロパティには、テキストの書式設定、位置、表示設定などが含まれます。たとえば、凡例の位置を変更するには、次を使用できます。

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

このコードは、グラフの下部に凡例が表示されるように設定します。その他のカスタマイズ オプションについては、Aspose.Slides ドキュメントを参照してください。

### グラフの縦軸の最小値と最大値を設定するにはどうすればよいですか?

グラフの縦軸の最小値と最大値を設定するには、次のコードを使用できます。

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

ここでは、軸の自動スケーリングを無効にし、縦軸の最小値と最大値を指定します。グラフ データの必要に応じて値を調整します。

### Aspose.Slides の詳細情報とドキュメントはどこで入手できますか?

Aspose ドキュメント Web サイトでは、Aspose.Slides for Java の包括的なドキュメントと API リファレンスを見つけることができます。訪問[ここ](https://reference.aspose.com/slides/java/)図書館の利用方法について詳しくは、こちらをご覧ください。