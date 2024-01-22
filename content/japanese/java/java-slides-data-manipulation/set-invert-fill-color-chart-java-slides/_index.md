---
title: Java スライドで塗りつぶしカラー チャートの反転を設定する
linktitle: Java スライドで塗りつぶしカラー チャートの反転を設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して Java Slides グラフの塗りつぶしの色を反転するように設定する方法を学習します。このステップバイステップのガイドとソース コードを使用して、グラフの視覚化を強化します。
type: docs
weight: 22
url: /ja/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

## Java スライドで塗りつぶしカラー チャートを反転設定する方法の概要

このチュートリアルでは、Aspose.Slides for Java を使用して Java Slides のグラフの反転塗りつぶし色を設定する方法を説明します。塗りつぶしの色の反転は、グラフ内の負の値を特定の色で強調表示する場合に便利な機能です。これを実現するための段階的な手順とソース コードを提供します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Aspose.Slides for Java ライブラリがインストールされています。
2. Java開発環境のセットアップ。

## ステップ 1: プレゼンテーションを作成する

まず、グラフを追加するプレゼンテーションを作成する必要があります。次のコードを使用してプレゼンテーションを作成できます。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ 2: グラフを追加する

次に、集合縦棒グラフをプレゼンテーションに追加します。その方法は次のとおりです。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## ステップ 3: チャート データを設定する

次に、系列とカテゴリを含むグラフ データを設定しましょう。

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

//新しいシリーズとカテゴリの追加
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## ステップ 4: シリーズ データを入力する

次に、グラフに系列データを入力しましょう。

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## ステップ 5: 塗りつぶしの色の反転を設定する

グラフシリーズの塗りつぶしの反転色を設定するには、次のコードを使用できます。

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

上記のコードでは、負の値の塗りつぶしの色を反転するようにシリーズを設定し、反転した塗りつぶしの色を指定します。

## ステップ 6: プレゼンテーションを保存する

最後に、グラフを含むプレゼンテーションを保存します。

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Java スライドの塗りつぶしカラー チャートを反転設定するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
//新しいシリーズとカテゴリの追加
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
//最初のグラフ シリーズを取得し、シリーズ データを入力します。
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

このチュートリアルでは、Aspose.Slides for Java を使用して Java Slides のグラフの反転塗りつぶし色を設定する方法を説明しました。この機能を使用すると、グラフ内の負の値を特定の色で強調表示でき、データを視覚的にわかりやすくすることができます。

## よくある質問

このセクションでは、Aspose.Slides for Java を使用した Java Slides のグラフの反転塗りつぶし色の設定に関連するいくつかのよくある質問に対処します。

### Aspose.Slides for Java をインストールするにはどうすればよいですか?

 Aspose.Slides JAR ファイルを Java プロジェクトに含めることで、Aspose.Slides for Java をインストールできます。ライブラリはからダウンロードできます。[Aspose.Slides for Java のダウンロード ページ](https://releases.aspose.com/slides/java/)。特定の開発環境のドキュメントに記載されているインストール手順に従ってください。

### グラフシリーズの反転塗りつぶしの色をカスタマイズできますか?

はい、グラフ シリーズの反転塗りつぶしの色をカスタマイズできます。提供されたコード例では、`series.getInvertedSolidFillColor().setColor(Color.RED)`線は、反転塗りつぶしの色を赤に設定します。交換できます`Color.RED`他の色でもお選びいただけます。

### Aspose.Slides for Java でグラフの種類を変更するにはどうすればよいですか?

グラフの種類を変更するには、`ChartType`プレゼンテーションにグラフを追加するときのパラメータ。コード例では、`ChartType.ClusteredColumn` 。適切なオプションを指定することで、折れ線グラフ、棒グラフ、円グラフなどの他のグラフの種類を調べることができます。`ChartType`列挙値。

### 複数のデータ系列をグラフに追加するにはどうすればよいですか?

複数のデータ系列をグラフに追加するには、`chart.getChartData().getSeries().add(...)`追加するシリーズごとにメソッドを選択します。グラフに複数の系列を入力するには、各系列に適切なデータ ポイントとラベルを必ず指定してください。

### グラフの外観の他の側面をカスタマイズする方法はありますか?

はい、Aspose.Slides for Java を使用して、軸ラベル、タイトル、凡例など、グラフの外観のさまざまな側面をカスタマイズできます。グラフ要素と外観のカスタマイズに関する詳細なガイダンスについては、ドキュメントを参照してください。

### グラフを別の形式で保存できますか?

はい、Aspose.Slides for Java を使用して、グラフをさまざまな形式で保存できます。提供されたコード例では、プレゼンテーションを PPTX ファイルとして保存しました。さまざまな使い方ができます`SaveFormat`要件に応じて、PDF、PNG、SVG などの他の形式で保存するオプションがあります。