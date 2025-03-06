---
title: Java スライドでのチャートシリーズの自動色付け
linktitle: Java スライドでのチャートシリーズの自動色付け
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションでシリーズの色を自動的に変更する動的なグラフを作成する方法を学びます。データの視覚化を簡単に強化できます。
weight: 14
url: /ja/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides for Java での自動チャート シリーズ カラーの概要

このチュートリアルでは、Aspose.Slides for Java を使用してグラフ付きの PowerPoint プレゼンテーションを作成し、グラフ シリーズの自動塗りつぶし色を設定する方法について説明します。自動塗りつぶし色を使用すると、グラフの視覚的な魅力が増し、ライブラリで色を選択できるため、時間の節約にもなります。

## 前提条件

始める前に、プロジェクトにAspose.Slides for Javaライブラリがインストールされていることを確認してください。ダウンロードはこちらからできます。[ここ](https://releases.aspose.com/slides/java/).

## ステップ1: 新しいプレゼンテーションを作成する

まず、新しい PowerPoint プレゼンテーションを作成し、それにスライドを追加します。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

## ステップ2: スライドにグラフを追加する

次に、スライドに集合縦棒グラフを追加します。また、最初の系列に値を表示するように設定します。

```java
//最初のスライドにアクセス
ISlide slide = presentation.getSlides().get_Item(0);
//デフォルトデータでグラフを追加
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
//最初のシリーズを値を表示に設定
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## ステップ3: チャートデータを入力する

次に、グラフにデータを入力します。まず、デフォルトで生成されたシリーズとカテゴリを削除し、次に新しいシリーズとカテゴリを追加します。

```java
//チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;
//チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//デフォルトで生成されたシリーズとカテゴリを削除する
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

//新しいシリーズの追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

//新しいカテゴリーの追加
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## ステップ4: シリーズデータを入力する

シリーズ 1 とシリーズ 2 の両方のシリーズ データを入力します。

```java
//最初のチャートシリーズ
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//シリーズデータを入力中
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

//第2チャートシリーズ
series = chart.getChartData().getSeries().get_Item(1);
//シリーズデータを入力中
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## ステップ5: シリーズの自動塗りつぶし色を設定する

次に、チャート シリーズの自動塗りつぶし色を設定しましょう。これにより、ライブラリが自動的に色を選択するようになります。

```java
//シリーズの自動塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## ステップ6: プレゼンテーションを保存する

最後に、グラフを含むプレゼンテーションを PowerPoint ファイルに保存します。

```java
//グラフ付きのプレゼンテーションを保存する
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Java スライドの自動チャート シリーズ カラーの完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
try
{
	//最初のスライドにアクセス
	ISlide slide = presentation.getSlides().get_Item(0);
	//デフォルトデータでグラフを追加
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	//最初のシリーズを値を表示に設定
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	//チャートデータシートのインデックスの設定
	int defaultWorksheetIndex = 0;
	//チャートデータワークシートの取得
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	//デフォルトで生成されたシリーズとカテゴリを削除する
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	//新しいシリーズの追加
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	//新しいカテゴリーの追加
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	//最初のチャートシリーズ
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	//シリーズデータを入力中
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	//シリーズの自動塗りつぶし色の設定
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	//第2チャートシリーズ
	series = chart.getChartData().getSeries().get_Item(1);
	//シリーズデータを入力中
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	//シリーズの塗りつぶし色の設定
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	//グラフ付きのプレゼンテーションを保存する
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用してチャート付きの PowerPoint プレゼンテーションを作成し、チャート シリーズの自動塗りつぶし色を設定する方法を学習しました。自動色設定により、チャートの視覚的な魅力が高まり、プレゼンテーションがより魅力的になります。必要に応じて、特定の要件に合わせてチャートをさらにカスタマイズできます。

## よくある質問

### Aspose.Slides for Java でチャート シリーズの自動塗りつぶし色を設定するにはどうすればよいですか?

Aspose.Slides for Java でグラフ シリーズの自動塗りつぶし色を設定するには、次のコードを使用します。

```java
//シリーズの自動塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

このコードにより、ライブラリはチャートシリーズの色を自動的に選択できるようになります。

### 必要に応じてグラフの色をカスタマイズできますか?

はい、必要に応じてグラフの色をカスタマイズできます。提供された例では自動塗りつぶし色を使用しましたが、`FillType`そして`SolidFillColor`シリーズの形式のプロパティ。

### グラフにシリーズやカテゴリを追加するにはどうすればよいですか?

チャートにシリーズやカテゴリを追加するには、`getSeries()`そして`getCategories()`チャートの手法`ChartData`オブジェクト。データとラベルを指定して、新しいシリーズとカテゴリを追加できます。

### グラフとラベルをさらにフォーマットすることは可能ですか?

はい、必要に応じてグラフ、シリーズ、ラベルをさらに書式設定できます。Aspose.Slides for Java には、フォント、色、スタイルなど、グラフの広範な書式設定オプションが用意されています。書式設定オプションの詳細については、ドキュメントを参照してください。

### Aspose.Slides for Java の使用に関する詳細情報はどこで入手できますか?

 Aspose.Slides for Javaの詳細情報と詳細なドキュメントについては、リファレンスドキュメントをご覧ください。[ここ](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
