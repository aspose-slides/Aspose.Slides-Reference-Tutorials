---
title: Java スライドのグラフ シリーズの自動色付け
linktitle: Java スライドのグラフ シリーズの自動色付け
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションで自動シリーズ カラーを使用した動的なグラフを作成する方法を学びます。データの視覚化を簡単に強化します。
type: docs
weight: 14
url: /ja/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## Aspose.Slides for Java の自動グラフ シリーズ カラーの紹介

このチュートリアルでは、Aspose.Slides for Java を使用してグラフを含む PowerPoint プレゼンテーションを作成し、グラフ シリーズの自動塗りつぶし色を設定する方法を説明します。自動塗りつぶし色を使用すると、ライブラリに色を選択させることでグラフの視覚的魅力を高め、時間を節約できます。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがプロジェクトにインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/slides/java/).

## ステップ 1: 新しいプレゼンテーションを作成する

まず、新しい PowerPoint プレゼンテーションを作成し、それにスライドを追加します。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
// Presentationクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

## ステップ 2: スライドにグラフを追加する

次に、集合縦棒グラフをスライドに追加します。また、最初のシリーズが値を表示するように設定します。

```java
//最初のスライドにアクセスする
ISlide slide = presentation.getSlides().get_Item(0);
//デフォルトのデータを含むグラフを追加する
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
//最初のシリーズを「値を表示」に設定します
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## ステップ 3: グラフ データを入力する

次に、グラフにデータを入力します。まず、デフォルトで生成されたシリーズとカテゴリを削除してから、新しいシリーズとカテゴリを追加します。

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

//新しいカテゴリの追加
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## ステップ 4: シリーズ データを入力する

シリーズ 1 とシリーズ 2 の両方にシリーズ データを入力します。

```java
//最初のチャート シリーズを取得する
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//シリーズデータを入力中です
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// 番目のチャート シリーズを取得する
series = chart.getChartData().getSeries().get_Item(1);
//シリーズデータを入力中です
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## ステップ 5: シリーズの自動塗りつぶし色を設定する

次に、グラフシリーズの自動塗りつぶし色を設定しましょう。これにより、ライブラリが色を選択するようになります。

```java
//シリーズの自動塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## ステップ 6: プレゼンテーションを保存する

最後に、グラフを含むプレゼンテーションを PowerPoint ファイルに保存します。

```java
//プレゼンテーションをグラフとともに保存する
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Java スライドのグラフ シリーズの自動カラーの完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
// Presentationクラスのインスタンスを作成する
Presentation presentation = new Presentation();
try
{
	//最初のスライドにアクセスする
	ISlide slide = presentation.getSlides().get_Item(0);
	//デフォルトのデータを含むグラフを追加する
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	//最初のシリーズを「値を表示」に設定します
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
	//新しいカテゴリの追加
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	//最初のチャート シリーズを取得する
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	//シリーズデータを入力中です
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	//シリーズの自動塗りつぶし色の設定
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// 番目のチャート シリーズを取得する
	series = chart.getChartData().getSeries().get_Item(1);
	//シリーズデータを入力中です
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	//シリーズの塗りつぶし色の設定
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	//プレゼンテーションをグラフとともに保存する
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用してグラフを含む PowerPoint プレゼンテーションを作成し、グラフ シリーズの自動塗りつぶし色を設定する方法を学びました。自動カラーを使用すると、グラフの視覚的な魅力が向上し、プレゼンテーションがより魅力的なものになります。特定の要件に応じて、グラフをさらにカスタマイズできます。

## よくある質問

### Aspose.Slides for Java でグラフ シリーズの自動塗りつぶし色を設定するにはどうすればよいですか?

Aspose.Slides for Java でグラフ シリーズの自動塗りつぶし色を設定するには、次のコードを使用します。

```java
//シリーズの自動塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

このコードにより、ライブラリはグラフ シリーズの色を自動的に選択できるようになります。

### 必要に応じてグラフの色をカスタマイズできますか?

はい、必要に応じてグラフの色をカスタマイズできます。この例では自動塗りつぶし色を使用しましたが、変更することで特定の色を設定できます。`FillType`そして`SolidFillColor`シリーズの形式のプロパティ。

### グラフに系列やカテゴリを追加するにはどうすればよいですか?

追加の系列またはカテゴリをグラフに追加するには、`getSeries()`そして`getCategories()`チャートのメソッド`ChartData`物体。データとラベルを指定することで、新しいシリーズとカテゴリを追加できます。

### グラフとラベルをさらにフォーマットすることは可能ですか?

はい、必要に応じて、グラフ、系列、ラベルをさらに書式設定できます。 Aspose.Slides for Java は、フォント、色、スタイルなどを含む、グラフの広範な書式設定オプションを提供します。書式設定オプションの詳細については、ドキュメントを参照してください。

### Aspose.Slides for Java の使用に関する詳細情報はどこで入手できますか?

 Aspose.Slides for Java の詳細と詳細なドキュメントについては、リファレンス ドキュメントを参照してください。[ここ](https://reference.aspose.com/slides/java/).