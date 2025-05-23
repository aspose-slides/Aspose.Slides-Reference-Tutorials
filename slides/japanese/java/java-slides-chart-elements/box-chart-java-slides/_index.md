---
"description": "Aspose.Slidesを使ってJavaプレゼンテーションでボックスチャートを作成する方法を学びましょう。効果的なデータ視覚化のためのステップバイステップガイドとソースコードが付属しています。"
"linktitle": "Javaスライドのボックスチャート"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドのボックスチャート"
"url": "/ja/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドのボックスチャート


## Aspose.Slides for Java のボックス チャートの概要

このチュートリアルでは、Aspose.Slides for Java を使用してボックス チャートを作成する手順を詳しく説明します。ボックス チャートは、さまざまな四分位数や外れ値を含む統計データを視覚化するのに役立ちます。ステップ バイ ステップの手順とソース コードを用意し、すぐに使い始められるようお手伝いします。

## 前提条件

始める前に、次のものがあることを確認してください。

- Aspose.Slides for Java ライブラリがインストールおよび構成されています。
- Java 開発環境をセットアップしました。

## ステップ1: プレゼンテーションを初期化する

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

この手順では、既存の PowerPoint ファイル (この例では「test.pptx」) へのパスを使用してプレゼンテーション オブジェクトを初期化します。

## ステップ2: ボックスチャートを作成する

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

この手順では、プレゼンテーションの最初のスライドにボックスグラフの図形を作成します。また、グラフから既存のカテゴリと系列をすべてクリアします。

## ステップ3: カテゴリを定義する

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

このステップでは、ボックスチャートのカテゴリーを定義します。 `IChartDataWorkbook` カテゴリを追加し、それに応じてラベルを付けます。

## ステップ4：シリーズを作成する

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

ここでは、チャートの BoxAndWhisker シリーズを作成し、四分位法、平均線、平均マーカー、内部ポイント、外れ値ポイントなどのさまざまなオプションを構成します。

## ステップ5: データポイントを追加する

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

このステップでは、BoxAndWhisker系列にデータポイントを追加します。これらのデータポイントは、グラフの統計データを表します。

## ステップ6: プレゼンテーションを保存する

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

最後に、ボックス チャートを含むプレゼンテーションを「BoxAndWhisker.pptx」という名前の新しい PowerPoint ファイルに保存します。

おめでとうございます！Aspose.Slides for Java を使用してボックスチャートを作成できました。必要に応じて、各種プロパティを調整したり、データポイントを追加したりすることで、チャートをさらにカスタマイズできます。

## Javaスライドのボックスチャートの完全なソースコード

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用してボックス チャートを作成する方法を学習しました。ボックス チャートは、四分位数や外れ値などの統計データを視覚化するための便利なツールです。Java アプリケーションでボックス チャートを作成し始める際に役立つ、ステップバイステップのガイドとソース コードを用意しました。

## よくある質問

### ボックス チャートの外観を変更するにはどうすればよいですか?

ボックスチャートの外観は、線のスタイル、色、フォントなどのプロパティを変更することでカスタマイズできます。チャートのカスタマイズの詳細については、Aspose.Slides for Javaのドキュメントをご覧ください。

### ボックス チャートに追加のデータ シリーズを追加できますか?

はい、追加のデータ系列を作成することで、ボックスチャートに複数のデータ系列を追加できます。 `IChartSeries` オブジェクトを作成し、そこにデータ ポイントを追加します。

### QuartileMethodType.Exclusive はどういう意味ですか?

その `QuartileMethodType.Exclusive` この設定では、四分位数の計算を排他的手法で行うことを指定します。データと要件に応じて、異なる四分位数の計算方法を選択できます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}