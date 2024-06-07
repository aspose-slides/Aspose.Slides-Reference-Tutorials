---
title: Java スライドのチャートのデフォルト マーカー
linktitle: Java スライドのチャートのデフォルト マーカー
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、チャートにデフォルトのマーカーが付いた Java スライドを作成する方法を学びます。ソース コード付きのステップ バイ ステップ ガイド。
type: docs
weight: 16
url: /ja/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

## Java スライドのチャートのデフォルト マーカーの紹介

このチュートリアルでは、Aspose.Slides for Java を使用して、デフォルトのマーカー付きのグラフを作成する方法について説明します。デフォルトのマーカーとは、グラフ内のデータ ポイントを強調表示するために追加されるシンボルまたは図形です。データを視覚化するために、マーカー付きの折れ線グラフを作成します。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリが Java プロジェクトにインストールされ、設定されていることを確認してください。

## ステップ1: プレゼンテーションを作成する

まず、プレゼンテーションを作成し、スライドを追加します。次に、スライドにグラフを追加します。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## ステップ2: マーカー付きの折れ線グラフを追加する

次に、マーカー付きの折れ線グラフをスライドに追加します。また、グラフからデフォルトのデータをすべてクリアします。

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## ステップ3: チャートデータを入力する

サンプル データを使用してグラフを作成します。この例では、データ ポイントとカテゴリを含む 2 つのシリーズを作成します。

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

//シリーズ2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

//シリーズデータの入力
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## ステップ4: チャートをカスタマイズする

凡例を追加したり外観を調整したりするなど、グラフをさらにカスタマイズできます。

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## ステップ5: プレゼンテーションを保存する

最後に、グラフを含むプレゼンテーションを目的の場所に保存します。

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

これで完了です。Aspose.Slides for Java を使用して、デフォルトのマーカー付きの折れ線グラフを作成しました。

## Java スライドのチャートのデフォルト マーカーの完全なソース コード

```java
        //ドキュメント ディレクトリへのパス。
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
            //第2チャートシリーズ
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //シリーズデータを入力中
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

この包括的なチュートリアルでは、Aspose.Slides for Java を使用して、チャートにデフォルトのマーカーが付いた Java スライドを作成する方法を学習しました。プレゼンテーションの設定からチャートの外観のカスタマイズ、結果の保存まで、プロセス全体を説明しました。

## よくある質問

### マーカーシンボルを変更するにはどうすればよいですか?

各データポイントのマーカースタイルを設定することで、マーカーシンボルをカスタマイズできます。`IDataPoint.setMarkerStyle()`マーカーシンボルを変更します。

### グラフの色を調整するにはどうすればよいですか?

チャートの色を変更するには、`IChartSeriesFormat`そして`IShapeFillFormat`塗りつぶしと線のプロパティを設定するためのインターフェース。

### データ ポイントにラベルを追加できますか?

はい、データポイントにラベルを追加することができます。`IDataPoint.getLabel()`方法を確認し、必要に応じてカスタマイズします。