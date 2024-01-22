---
title: Java スライドのグラフのデフォルトのマーカー
linktitle: Java スライドのグラフのデフォルトのマーカー
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、チャートにデフォルトのマーカーを含む Java スライドを作成する方法を学びます。ソースコード付きのステップバイステップガイド。
type: docs
weight: 16
url: /ja/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

## Java スライドのグラフのデフォルト マーカーの概要

このチュートリアルでは、Aspose.Slides for Java を使用してデフォルトのマーカーを含むグラフを作成する方法を検討します。デフォルトのマーカーは、チャート内のデータ ポイントを強調表示するために追加されるシンボルまたは図形です。データを視覚化するためにマーカーを含む折れ線グラフを作成します。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがインストールされ、Java プロジェクトに設定されていることを確認してください。

## ステップ 1: プレゼンテーションを作成する

まず、プレゼンテーションを作成し、それにスライドを追加しましょう。次に、スライドにグラフを追加します。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## ステップ 2: マーカー付きの折れ線グラフを追加する

次に、マーカー付きの折れ線グラフをスライドに追加しましょう。また、グラフからデフォルトのデータも消去します。

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## ステップ 3: グラフ データを入力する

グラフにサンプル データを入力します。この例では、データ ポイントとカテゴリを含む 2 つのシリーズを作成します。

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

//シリーズ 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

//シリーズ 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

//シリーズデータの入力
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## ステップ 4: グラフをカスタマイズする

凡例の追加や外観の調整など、グラフをさらにカスタマイズできます。

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## ステップ 5: プレゼンテーションを保存する

最後に、グラフを含むプレゼンテーションを目的の場所に保存します。

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

それでおしまい！ Aspose.Slides for Java を使用して、デフォルトのマーカーを含む折れ線グラフを作成しました。

## Java スライドのグラフのデフォルト マーカーの完全なソース コード

```java
        //ドキュメントディレクトリへのパス。
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //番目のチャート シリーズを取得する
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //シリーズデータを入力中です
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## 結論

この包括的なチュートリアルでは、Aspose.Slides for Java を使用してグラフ内にデフォルトのマーカーを含む Java スライドを作成する方法を学習しました。プレゼンテーションの設定からグラフの外観のカスタマイズ、結果の保存までのプロセス全体をカバーしました。

## よくある質問

### マーカーのシンボルを変更するにはどうすればよいですか?

各データ ポイントのマーカー スタイルを設定することで、マーカー シンボルをカスタマイズできます。使用`IDataPoint.setMarkerStyle()`マーカーのシンボルを変更します。

### グラフの色を調整するにはどうすればよいですか?

グラフの色を変更するには、`IChartSeriesFormat`そして`IShapeFillFormat`塗りつぶしと線のプロパティを設定するためのインターフェイス。

### データポイントにラベルを追加できますか?

はい、次を使用してデータ ポイントにラベルを追加できます。`IDataPoint.getLabel()`メソッドを作成し、必要に応じてカスタマイズします。