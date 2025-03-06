---
title: Java スライドのフォント サイズの凡例
linktitle: Java スライドのフォント サイズの凡例
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint プレゼンテーションを強化します。ステップバイステップ ガイドで、凡例のフォント サイズなどをカスタマイズする方法を学びます。
type: docs
weight: 13
url: /ja/java/chart-elements/font-size-legend-java-slides/
---

## Java スライドのフォント サイズ凡例の紹介

このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint スライドの凡例のフォント サイズをカスタマイズする方法を学習します。このタスクを実行するための手順とソース コードを提供します。

## 前提条件

始める前に、Aspose.Slides for JavaライブラリがJavaプロジェクトにインストールされ、設定されていることを確認してください。ライブラリは以下からダウンロードできます。[ここ](https://releases.aspose.com/slides/java/).

## ステップ1: プレゼンテーションを初期化する

まず、必要なクラスをインポートし、PowerPoint プレゼンテーションを初期化します。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

交換する`"Your Document Directory"` PowerPoint ファイルへの実際のパスを入力します。

## ステップ2: グラフを追加する

次に、スライドにグラフを追加し、凡例のフォント サイズを設定します。

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

このコードでは、最初のスライドに集合縦棒グラフを作成し、凡例テキストのフォントサイズを20ポイントに設定しています。`setFontHeight`必要に応じてフォント サイズを変更するには値を入力します。

## ステップ3: 軸の値をカスタマイズする

ここで、グラフの縦軸の値をカスタマイズしてみましょう。

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

ここでは、垂直軸の最小値と最大値を設定します。データの要件に応じて値を変更できます。

## ステップ4: プレゼンテーションを保存する

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
//ドキュメント ディレクトリへのパス。
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

Aspose.Slides for Java を使用して、Java PowerPoint スライドの凡例のフォント サイズをカスタマイズできました。Aspose.Slides の機能をさらに詳しく調べて、インタラクティブで視覚的に魅力的なプレゼンテーションを作成できます。

## よくある質問

### グラフ内の凡例テキストのフォント サイズを変更するにはどうすればよいですか?

グラフ内の凡例テキストのフォント サイズを変更するには、次のコードを使用します。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

このコードでは、グラフを作成し、凡例テキストのフォントサイズを20ポイントに設定しています。`setFontHeight`フォントサイズを変更する値。

### グラフ内の凡例の他のプロパティをカスタマイズできますか?

はい、Aspose.Slides を使用してグラフの凡例のさまざまなプロパティをカスタマイズできます。カスタマイズできる一般的なプロパティには、テキストの書式設定、位置、表示などが含まれます。たとえば、凡例の位置を変更するには、次のものを使用します。

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

このコードは、凡例がグラフの下部に表示されるように設定します。その他のカスタマイズ オプションについては、Aspose.Slides のドキュメントを参照してください。

### グラフの縦軸の最小値と最大値を設定するにはどうすればよいですか?

グラフの垂直軸の最小値と最大値を設定するには、次のコードを使用します。

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

ここでは、自動軸スケーリングを無効にし、垂直軸の最小値と最大値を指定します。グラフのデータに応じて値を調整します。

### Aspose.Slides の詳細情報とドキュメントはどこで入手できますか?

 Aspose.Slides for Javaの包括的なドキュメントとAPIリファレンスは、AsposeドキュメントWebサイトでご覧いただけます。[ここ](https://reference.aspose.com/slides/java/)ライブラリの使用に関する詳細情報。