---
title: Java スライドの複数カテゴリのグラフ
linktitle: Java スライドの複数カテゴリのグラフ
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java Slides で複数カテゴリのグラフを作成します。プレゼンテーションで印象的なデータを視覚化するためのソース コードを含むステップバイステップ ガイド。
type: docs
weight: 20
url: /ja/java/chart-data-manipulation/multi-category-chart-java-slides/
---

## Aspose.Slides を使用した Java Slides での複数カテゴリ チャートの概要

このチュートリアルでは、Aspose.Slides for Java API を使用して Java スライドでマルチカテゴリ グラフを作成する方法を学習します。このガイドでは、複数のカテゴリと系列を含む集合縦棒グラフを作成するのに役立つ、ソース コードとともに段階的な手順を説明します。

## 前提条件
始める前に、Aspose.Slides for Java ライブラリが Java 開発環境にインストールされ、セットアップされていることを確認してください。

## ステップ 1: 環境のセットアップ
まず、必要なクラスをインポートし、スライドを操作するための新しいプレゼンテーション オブジェクトを作成します。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ 2: スライドとグラフを追加する
次に、スライドを作成し、それに集合縦棒グラフを追加します。

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## ステップ 3: 既存のデータの消去
既存のデータをグラフから消去します。

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## ステップ 4: データ カテゴリの設定
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

## ステップ 5: シリーズの追加
次に、データ ポイントとともに系列をグラフに追加しましょう。

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

## ステップ 6: プレゼンテーションを保存する
最後に、プレゼンテーションをグラフとともに保存します。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

それでおしまい！ Aspose.Slides を使用して、Java スライドに複数カテゴリのグラフを作成することができました。このグラフは、特定の要件に合わせてさらにカスタマイズできます。

## Java スライドの複数カテゴリ チャートの完全なソース コード

```java
//ドキュメントディレクトリへのパス。
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
//プレゼンテーションをグラフとともに保存する
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides for Java API を使用して Java スライドでマルチカテゴリ グラフを作成する方法を学習しました。ソースコードを含むステップバイステップのガイドを実行して、複数のカテゴリと系列を含む集合縦棒グラフを作成しました。

## よくある質問

### グラフの外観をカスタマイズするにはどうすればよいですか?

色、フォント、スタイルなどのプロパティを変更することで、グラフの外観をカスタマイズできます。カスタマイズ オプションの詳細については、Aspose.Slides のドキュメントを参照してください。

### チャートにさらにシリーズを追加できますか?

はい、ステップ 5 と同様のプロセスに従って、グラフに系列を追加できます。

### グラフの種類を変更するにはどうすればよいですか?

グラフの種類を変更するには、`ChartType.ClusteredColumn`ステップ 2 でグラフを追加するときに、目的のグラフ タイプを指定します。

### グラフにタイトルを追加するにはどうすればよいですか?

を使用してグラフにタイトルを追加できます。`ch.getChartTitle().getTextFrame().setText("Chart Title");`方法。