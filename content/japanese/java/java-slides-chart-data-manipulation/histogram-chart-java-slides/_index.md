---
title: Java スライドのヒストグラム チャート
linktitle: Java スライドのヒストグラム チャート
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint プレゼンテーションでヒストグラム グラフを作成する方法を学びます。データ視覚化のためのソースコードを含むステップバイステップのガイド。
type: docs
weight: 19
url: /ja/java/chart-data-manipulation/histogram-chart-java-slides/
---

## Aspose.Slides を使用した Java Slides のヒストグラム チャートの概要

このチュートリアルでは、Aspose.Slides for Java API を使用して PowerPoint プレゼンテーションでヒストグラム グラフを作成するプロセスを説明します。ヒストグラム チャートは、連続間隔にわたるデータの分布を表すために使用されます。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがインストールされていることを確認してください。からダウンロードできます。[Aspose ウェブサイト](https://releases.aspose.com/slides/java/).

## ステップ 1: プロジェクトを初期化する

Java プロジェクトを作成し、Aspose.Slides ライブラリをプロジェクトの依存関係に含めます。

## ステップ 2: 必要なライブラリをインポートする

```java
import com.aspose.slides.*;
```

## ステップ 3: 既存のプレゼンテーションをロードする

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

必ず交換してください`"Your Document Directory"`PowerPoint ドキュメントへの実際のパスを含めます。

## ステップ 4: ヒストグラム チャートを作成する

次に、プレゼンテーションのスライドにヒストグラム チャートを作成しましょう。

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    //データ ポイントをシリーズに追加する
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    //横軸の集計タイプを自動に設定します
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    //プレゼンテーションを保存する
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

このコードでは、最初に既存のカテゴリとシリーズをグラフから削除します。次に、次を使用してデータ ポイントを系列に追加します。`getDataPoints().addDataPointForHistogramSeries`方法。最後に、横軸の集計タイプを自動に設定し、プレゼンテーションを保存します。

## Java スライドのヒストグラム チャートの完全なソース コード

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java API を使用して PowerPoint プレゼンテーションでヒストグラム グラフを作成する方法を説明しました。ヒストグラム チャートは、連続間隔にわたるデータの分布を視覚化するための貴重なツールであり、特に統計コンテンツや分析コンテンツを扱う場合、プレゼンテーションに強力に追加できます。

## よくある質問

### Aspose.Slides for Java をインストールするにはどうすればよいですか?

 Aspose.Slides for Java ライブラリは、次からダウンロードできます。[ここ](https://releases.aspose.com/slides/java/)。 Web サイトに記載されているインストール手順に従ってください。

### ヒストグラム チャートは何に使用されますか?

ヒストグラム チャートは、連続間隔にわたるデータの分布を視覚化するために使用されます。頻度分布を表すために統計でよく使用されます。

### ヒストグラム チャートの外観をカスタマイズできますか?

はい、Aspose.Slides API を使用して、色、ラベル、軸などのグラフの外観をカスタマイズできます。