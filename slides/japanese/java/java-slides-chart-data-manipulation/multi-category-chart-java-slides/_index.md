---
"description": "Aspose.Slides for Javaを使用して、Javaスライドでマルチカテゴリーチャートを作成します。プレゼンテーションで印象的なデータ視覚化を実現するための、ソースコード付きのステップバイステップガイドです。"
"linktitle": "Javaスライドのマルチカテゴリチャート"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドのマルチカテゴリチャート"
"url": "/ja/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドのマルチカテゴリチャート


## Aspose.Slides を使用した Java スライドでのマルチカテゴリ チャートの紹介

このチュートリアルでは、Aspose.Slides for Java API を使用して、Java スライドでマルチカテゴリチャートを作成する方法を学びます。このガイドでは、複数のカテゴリと系列を含む集合縦棒グラフを作成するための手順とソースコードを提供します。

## 前提条件
始める前に、Java 開発環境に Aspose.Slides for Java ライブラリがインストールされ、設定されていることを確認してください。

## ステップ1: 環境の設定
まず、必要なクラスをインポートし、スライドを操作するための新しい Presentation オブジェクトを作成します。

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ2: スライドとグラフを追加する
次に、スライドを作成し、そこに集合縦棒グラフを追加します。

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## ステップ3: 既存データの消去
グラフから既存のデータをすべてクリアします。

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## ステップ4: データカテゴリの設定
それでは、グラフのデータカテゴリを設定しましょう。複数のカテゴリを作成し、グループ化します。

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// カテゴリを追加してグループ化する
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

これで完了です！Aspose.Slides を使って、Java スライドにマルチカテゴリーチャートを作成できました。このチャートは、必要に応じてさらにカスタマイズできます。

## Javaスライドのマルチカテゴリーチャートの完全なソースコード

```java
// ドキュメント ディレクトリへのパス。
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
//            シリーズの追加
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
// グラフ付きのプレゼンテーションを保存する
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides for Java API を使用して、Java スライドでマルチカテゴリチャートを作成する方法を学習しました。ソースコード付きのステップバイステップガイドに沿って、複数のカテゴリと系列を含む集合縦棒グラフを作成しました。

## よくある質問

### チャートの外観をカスタマイズするにはどうすればよいですか?

色、フォント、スタイルなどのプロパティを変更することで、グラフの外観をカスタマイズできます。詳細なカスタマイズオプションについては、Aspose.Slides のドキュメントをご覧ください。

### チャートにさらにシリーズを追加できますか?

はい、手順 5 に示すのと同様のプロセスに従って、グラフにシリーズを追加できます。

### グラフの種類を変更するにはどうすればよいですか?

グラフの種類を変更するには、 `ChartType.ClusteredColumn` 手順 2 でグラフを追加するときに、希望するグラフの種類を選択します。

### グラフにタイトルを追加するにはどうすればよいですか?

チャートにタイトルを追加するには、 `ch.getChartTitle().getTextFrame().setText("Chart Title");` 方法。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}