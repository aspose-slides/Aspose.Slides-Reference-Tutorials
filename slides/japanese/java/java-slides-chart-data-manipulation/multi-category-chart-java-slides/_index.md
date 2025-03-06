---
title: Java スライドのマルチカテゴリ チャート
linktitle: Java スライドのマルチカテゴリ チャート
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java スライドでマルチカテゴリ チャートを作成します。プレゼンテーションで印象的なデータ視覚化を実現するためのソース コード付きのステップバイステップ ガイドです。
weight: 20
url: /ja/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java スライドのマルチカテゴリ チャート


## Aspose.Slides を使用した Java スライドのマルチカテゴリ チャートの紹介

このチュートリアルでは、Aspose.Slides for Java API を使用して、Java スライドでマルチカテゴリ チャートを作成する方法を学習します。このガイドでは、複数のカテゴリとシリーズを含む集合縦棒グラフを作成するための手順をソース コードとともに段階的に説明します。

## 前提条件
始める前に、Java 開発環境に Aspose.Slides for Java ライブラリがインストールされ、設定されていることを確認してください。

## ステップ1: 環境の設定
まず、必要なクラスをインポートし、スライドを操作するための新しい Presentation オブジェクトを作成します。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ2: スライドとグラフを追加する
次に、スライドを作成し、それに集合縦棒グラフを追加します。

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## ステップ3: 既存のデータを消去する
グラフから既存のデータをすべてクリアします。

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## ステップ4: データカテゴリの設定
次に、グラフのデータ カテゴリを設定しましょう。複数のカテゴリを作成し、グループ化します。

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

//カテゴリを追加してグループ化する
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## ステップ5: シリーズの追加
ここで、データ ポイントとともにシリーズをグラフに追加してみましょう。

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## ステップ6: プレゼンテーションを保存する
最後に、グラフを含むプレゼンテーションを保存します。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

これで完了です。Aspose.Slides を使用して、Java スライドにマルチカテゴリ チャートを作成しました。このチャートは、特定の要件に合わせてさらにカスタマイズできます。

## Java スライドのマルチカテゴリ チャートの完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
//シリーズの追加
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
//グラフ付きのプレゼンテーションを保存する
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides for Java API を使用して、Java スライドでマルチカテゴリ チャートを作成する方法を学習しました。ソース コードを使用したステップ バイ ステップ ガイドに従って、複数のカテゴリとシリーズを含む集合縦棒グラフを作成しました。

## よくある質問

### チャートの外観をカスタマイズするにはどうすればよいですか?

色、フォント、スタイルなどのプロパティを変更することで、グラフの外観をカスタマイズできます。詳細なカスタマイズ オプションについては、Aspose.Slides のドキュメントを参照してください。

### チャートにさらにシリーズを追加できますか?

はい、手順 5 に示すのと同様のプロセスに従って、グラフにシリーズを追加できます。

### グラフの種類を変更するにはどうすればよいですか?

チャートの種類を変更するには、`ChartType.ClusteredColumn`手順 2 でグラフを追加するときに、目的のグラフ タイプを選択します。

### チャートにタイトルを追加するにはどうすればよいですか?

チャートにタイトルを追加するには、`ch.getChartTitle().getTextFrame().setText("Chart Title");`方法。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
