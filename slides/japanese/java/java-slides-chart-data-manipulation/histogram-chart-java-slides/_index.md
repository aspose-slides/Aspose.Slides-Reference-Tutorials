---
title: Java スライドのヒストグラム チャート
linktitle: Java スライドのヒストグラム チャート
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint プレゼンテーションでヒストグラム チャートを作成する方法を学びます。データ視覚化のためのソース コードを含むステップ バイ ステップ ガイド。
weight: 19
url: /ja/java/chart-data-manipulation/histogram-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides を使用した Java スライドのヒストグラム チャートの紹介

このチュートリアルでは、Aspose.Slides for Java API を使用して PowerPoint プレゼンテーションでヒストグラム チャートを作成する手順を説明します。ヒストグラム チャートは、連続した間隔でのデータの分布を表すために使用されます。

## 前提条件

始める前に、Aspose.Slides for Javaライブラリがインストールされていることを確認してください。[Aspose ウェブサイト](https://releases.aspose.com/slides/java/).

## ステップ1: プロジェクトを初期化する

Java プロジェクトを作成し、プロジェクトの依存関係に Aspose.Slides ライブラリを含めます。

## ステップ2: 必要なライブラリをインポートする

```java
import com.aspose.slides.*;
```

## ステップ3: 既存のプレゼンテーションを読み込む

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

必ず交換してください`"Your Document Directory"`PowerPoint ドキュメントへの実際のパスを入力します。

## ステップ4: ヒストグラムチャートを作成する

それでは、プレゼンテーションのスライドにヒストグラム チャートを作成しましょう。

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    //シリーズにデータポイントを追加する
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    //水平軸の集計タイプを自動に設定する
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    //プレゼンテーションを保存する
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

このコードでは、まずチャートから既存のカテゴリとシリーズをクリアします。次に、`getDataPoints().addDataPointForHistogramSeries`最後に、水平軸の集計タイプを自動に設定し、プレゼンテーションを保存します。

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

このチュートリアルでは、Aspose.Slides for Java API を使用して PowerPoint プレゼンテーションでヒストグラム チャートを作成する方法について説明しました。ヒストグラム チャートは、連続した間隔でのデータの分布を視覚化するための便利なツールであり、特に統計や分析のコンテンツを扱う場合に、プレゼンテーションに強力な追加機能として使用できます。

## よくある質問

### Aspose.Slides for Java をインストールするにはどうすればよいですか?

 Aspose.Slides for Javaライブラリは以下からダウンロードできます。[ここ](https://releases.aspose.com/slides/java/)ウェブサイトに記載されているインストール手順に従ってください。

### ヒストグラムチャートは何に使用されますか?

ヒストグラム チャートは、連続した間隔でのデータの分布を視覚化するために使用されます。統計では、頻度分布を表すためによく使用されます。

### ヒストグラム チャートの外観をカスタマイズできますか?

はい、Aspose.Slides API を使用して、色、ラベル、軸などのグラフの外観をカスタマイズできます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
