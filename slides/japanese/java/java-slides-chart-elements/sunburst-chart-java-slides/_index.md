---
"description": "Aspose.Slides を使って、Java スライドで魅力的なサンバーストチャートを作成します。チャートの作成とデータ操作をステップバイステップで学びます。"
"linktitle": "Javaスライドのサンバーストチャート"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドのサンバーストチャート"
"url": "/ja/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドのサンバーストチャート


## Aspose.Slides を使用した Java スライドでのサンバースト チャートの紹介

このチュートリアルでは、Aspose.Slides for Java API を使用して、PowerPoint プレゼンテーションにサンバースト チャートを作成する方法を学びます。サンバースト チャートは、階層構造のデータを表すために使用される放射状チャートです。ソースコードとともに、ステップバイステップの手順を説明します。

## 前提条件

始める前に、JavaプロジェクトにAspose.Slides for Javaライブラリがインストールされ、設定されていることを確認してください。ライブラリは以下からダウンロードできます。 [ここ](https://releases。aspose.com/slides/java/).

## ステップ1: 必要なライブラリをインポートする

まず、Aspose.Slides を操作するために必要なライブラリをインポートし、Java アプリケーションでサンバースト チャートを作成します。

```java
import com.aspose.slides.*;
```

## ステップ2: プレゼンテーションを初期化する

PowerPoint プレゼンテーションを初期化し、プレゼンテーション ファイルを保存するディレクトリを指定します。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## ステップ3: サンバーストチャートを作成する

スライド上にサンバーストチャートを作成します。チャートの位置（X、Y）とサイズ（幅、高さ）を指定します。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## ステップ4: チャートデータの準備

グラフから既存のカテゴリと系列データをすべてクリアし、グラフのデータ ワークブックを作成します。

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## ステップ5: チャート階層を定義する

サンバーストチャートの階層構造を定義します。枝、幹、葉をカテゴリとして追加できます。

```java
// 支店1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// 支店2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## ステップ6: グラフにデータを追加する

サンバースト チャート シリーズにデータ ポイントを追加します。

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

## ステップ7: プレゼンテーションを保存する

最後に、サンバースト チャートを含むプレゼンテーションを保存します。

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Javaスライドのサンバーストチャートの完全なソースコード

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

このチュートリアルでは、Aspose.Slides for Java API を使用して、PowerPoint プレゼンテーションでサンバースト チャートを作成する方法を学習しました。プレゼンテーションの初期化、チャートの作成、チャート階層の定義、データポイントの追加、そしてプレゼンテーションの保存方法を学習しました。この知識を活用して、Java アプリケーションでインタラクティブで情報豊富なサンバースト チャートを作成できるようになります。

## よくある質問

### サンバースト チャートの外観をカスタマイズするにはどうすればよいですか?

サンバーストチャートの外観は、色、ラベル、スタイルなどのプロパティを変更することでカスタマイズできます。詳細なカスタマイズオプションについては、Aspose.Slides のドキュメントをご覧ください。

### グラフにさらにデータポイントを追加できますか?

はい、グラフにデータポイントを追加することができます。 `series.getDataPoints().addDataPointForSunburstSeries()` 含めるデータ ポイントごとにメソッドを選択します。

### サンバースト チャートにツールチップを追加するにはどうすればよいですか?

サンバースト チャートにツールヒントを追加するには、チャートのセグメントにマウスを移動したときに値や説明などの追加情報が表示されるようにデータ ラベル形式を設定できます。

### ハイパーリンク付きのインタラクティブなサンバースト チャートを作成することは可能ですか?

はい、特定のグラフ要素またはセグメントにハイパーリンクを追加することで、インタラクティブなサンバーストグラフを作成できます。ハイパーリンクの追加方法の詳細については、Aspose.Slides のドキュメントをご覧ください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}