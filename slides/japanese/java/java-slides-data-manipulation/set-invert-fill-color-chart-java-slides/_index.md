---
title: Java スライドで塗りつぶしカラーチャートの反転を設定する
linktitle: Java スライドで塗りつぶしカラーチャートの反転を設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して Java スライド チャートの塗りつぶし色を反転する方法を学びます。このステップ バイ ステップ ガイドとソース コードを使用して、チャートの視覚化を強化します。
weight: 22
url: /ja/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java スライドで塗りつぶしカラーチャートの反転を設定する


## Java スライドで反転塗りつぶしカラーチャートを設定する方法の紹介

このチュートリアルでは、Aspose.Slides for Java を使用して、Java スライドのグラフの塗りつぶし色の反転を設定する方法を説明します。塗りつぶし色の反転は、グラフ内の負の値を特定の色で強調表示したい場合に便利な機能です。これを実現するための手順とソース コードを提供します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Aspose.Slides for Java ライブラリがインストールされました。
2. Java開発環境をセットアップしました。

## ステップ1: プレゼンテーションを作成する

まず、チャートを追加するプレゼンテーションを作成する必要があります。プレゼンテーションを作成するには、次のコードを使用できます。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ2: グラフを追加する

次に、プレゼンテーションに集合縦棒グラフを追加します。手順は次のとおりです。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## ステップ3: チャートデータを設定する

次に、シリーズとカテゴリを含むグラフ データを設定しましょう。

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

//新しいシリーズとカテゴリーの追加
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## ステップ4: シリーズデータを入力する

次に、グラフの系列データを入力します。

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## ステップ5: 塗りつぶし色の反転を設定する

グラフシリーズの塗りつぶし色の反転を設定するには、次のコードを使用します。

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

上記のコードでは、負の値の塗りつぶし色を反転するようにシリーズを設定し、反転した塗りつぶしの色を指定します。

## ステップ6: プレゼンテーションを保存する

最後に、グラフを含むプレゼンテーションを保存します。

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Java スライドで反転塗りつぶしカラーチャートを設定するための完全なソースコード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
//新しいシリーズとカテゴリーの追加
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
//最初のチャート シリーズを取得し、シリーズ データを入力します。
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して、Java スライドのグラフの塗りつぶし色を反転させる方法を説明しました。この機能を使用すると、グラフ内の負の値を特定の色で強調表示できるため、データの視覚的な情報量が増します。

## よくある質問

このセクションでは、Aspose.Slides for Java を使用して Java スライドのグラフの塗りつぶし色の反転を設定することに関するよくある質問について説明します。

### Aspose.Slides for Java をインストールするにはどうすればよいですか?

 Aspose.Slides for Javaをインストールするには、JavaプロジェクトにAspose.Slides JARファイルを含めます。ライブラリは以下からダウンロードできます。[Aspose.Slides for Java のダウンロード ページ](https://releases.aspose.com/slides/java/)特定の開発環境のドキュメントに記載されているインストール手順に従ってください。

### グラフシリーズの反転塗りつぶしの色をカスタマイズできますか?

はい、チャートシリーズの反転塗りつぶしの色をカスタマイズできます。提供されているコード例では、`series.getInvertedSolidFillColor().setColor(Color.RED)`線は反転した塗りつぶしの色を赤に設定します。`Color.RED`お好みの色で。

### Aspose.Slides for Java でグラフの種類を変更するにはどうすればよいですか?

チャートの種類を変更するには、`ChartType`プレゼンテーションにグラフを追加するときにパラメータを使用します。コード例では、`ChartType.ClusteredColumn`適切なオプションを指定することで、折れ線グラフ、棒グラフ、円グラフなどの他の種類のグラフも表示できます。`ChartType`列挙値。

### グラフに複数のデータ系列を追加するにはどうすればよいですか?

複数のデータ系列をグラフに追加するには、`chart.getChartData().getSeries().add(...)`追加するシリーズごとにメソッドを使用します。複数のシリーズをチャートに取り込むには、各シリーズに適切なデータ ポイントとラベルを指定してください。

### チャートの外観の他の側面をカスタマイズする方法はありますか?

はい、Aspose.Slides for Java を使用すると、軸ラベル、タイトル、凡例など、グラフの外観のさまざまな側面をカスタマイズできます。グラフ要素と外観のカスタマイズに関する詳細なガイダンスについては、ドキュメントを参照してください。

### チャートを異なる形式で保存できますか?

はい、Aspose.Slides for Javaを使用して、チャートをさまざまな形式で保存できます。提供されたコード例では、プレゼンテーションをPPTXファイルとして保存しました。`SaveFormat`要件に応じて、PDF、PNG、SVG などの他の形式で保存するオプションがあります。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
