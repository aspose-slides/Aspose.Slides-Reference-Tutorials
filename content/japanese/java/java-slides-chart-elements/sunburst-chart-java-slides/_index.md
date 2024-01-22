---
title: Java スライドのサンバースト チャート
linktitle: Java スライドのサンバースト チャート
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して、Java スライドで見事なサンバースト チャートを作成します。段階的なチャートの作成とデータ操作を学びます。
type: docs
weight: 16
url: /ja/java/chart-elements/sunburst-chart-java-slides/
---

## Aspose.Slides を使用した Java スライドのサンバースト チャートの概要

このチュートリアルでは、Aspose.Slides for Java API を使用して PowerPoint プレゼンテーションでサンバースト グラフを作成する方法を学習します。サンバースト チャートは、階層データを表すために使用される放射状チャートです。ソースコードとともに段階的な手順を説明します。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリが Java プロジェクトにインストールされ、構成されていることを確認してください。ライブラリはからダウンロードできます[ここ](https://releases.aspose.com/slides/java/).

## ステップ 1: 必要なライブラリをインポートする

まず、Aspose.Slides を操作するために必要なライブラリをインポートし、Java アプリケーションでサンバースト チャートを作成します。

```java
import com.aspose.slides.*;
```

## ステップ 2: プレゼンテーションを初期化する

PowerPoint プレゼンテーションを初期化し、プレゼンテーション ファイルを保存するディレクトリを指定します。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## ステップ 3: サンバースト チャートを作成する

スライド上にサンバースト チャートを作成します。チャートの位置 (X、Y) と寸法 (幅、高さ) を指定します。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## ステップ 4: チャート データを準備する

既存のカテゴリと系列データをグラフから削除し、グラフのデータ ワークブックを作成します。

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## ステップ 5: グラフの階層を定義する

サンバースト チャートの階層構造を定義します。枝、幹、葉をカテゴリとして追加できます。

```java
//ブランチ1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

//支店2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## ステップ 6: グラフにデータを追加する

データ ポイントをサンバースト チャート シリーズに追加します。

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## ステップ 7: プレゼンテーションを保存する

最後に、サンバースト チャートを含むプレゼンテーションを保存します。

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Java スライドのサンバースト チャートの完全なソース コード

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//ブランチ1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//ブランチ2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java API を使用して PowerPoint プレゼンテーションでサンバースト グラフを作成する方法を学習しました。プレゼンテーションの初期化、グラフの作成、グラフ階層の定義、データ ポイントの追加、プレゼンテーションの保存の方法を説明しました。この知識を使用して、Java アプリケーションでインタラクティブで有益なサンバースト チャートを作成できるようになりました。

## よくある質問

### サンバースト チャートの外観をカスタマイズするにはどうすればよいですか?

色、ラベル、スタイルなどのプロパティを変更することで、サンバースト チャートの外観をカスタマイズできます。カスタマイズ オプションの詳細については、Aspose.Slides のドキュメントを参照してください。

### グラフにさらにデータ ポイントを追加できますか?

はい、次のコマンドを使用して、グラフにさらにデータ ポイントを追加できます。`series.getDataPoints().addDataPointForSunburstSeries()`含める各データ ポイントのメソッド。

### サンバースト チャートにツールチップを追加するにはどうすればよいですか?

サンバースト チャートにツールヒントを追加するには、チャート セグメントにマウスを移動したときに値や説明などの追加情報を表示するようにデータ ラベルの形式を設定します。

### ハイパーリンクを使用してインタラクティブなサンバースト チャートを作成することはできますか?

はい、特定のグラフ要素またはセグメントにハイパーリンクを追加することで、ハイパーリンクを含むインタラクティブなサンバースト グラフを作成できます。ハイパーリンクの追加の詳細については、Aspose.Slides のドキュメントを参照してください。