---
"description": "Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションでシリーズの色を自動的に調整する動的なグラフを作成する方法を学びましょう。データの視覚化を簡単に強化できます。"
"linktitle": "Javaスライドのチャートシリーズの自動色付け"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドのチャートシリーズの自動色付け"
"url": "/ja/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドのチャートシリーズの自動色付け


## Aspose.Slides for Java の自動チャートシリーズカラーの紹介

このチュートリアルでは、Aspose.Slides for Java を使用してグラフ付きのPowerPointプレゼンテーションを作成し、グラフ系列に自動で色を設定する方法を説明します。自動で色を設定すると、グラフの見栄えが良くなり、ライブラリが自動的に色を選択するため、作業時間を節約できます。

## 前提条件

始める前に、Aspose.Slides for Javaライブラリがプロジェクトにインストールされていることを確認してください。ダウンロードはこちらから可能です。 [ここ](https://releases。aspose.com/slides/java/).

## ステップ1: 新しいプレゼンテーションを作成する

まず、新しい PowerPoint プレゼンテーションを作成し、それにスライドを追加します。

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

## ステップ2: スライドにグラフを追加する

次に、スライドに集合縦棒グラフを追加します。また、最初の系列に値を表示するように設定します。

```java
// 最初のスライドにアクセス
ISlide slide = presentation.getSlides().get_Item(0);
// デフォルトデータでグラフを追加する
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// 最初の系列を値を表示に設定する
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## ステップ3: チャートデータを入力する

それでは、チャートにデータを入力していきましょう。まず、デフォルトで生成された系列とカテゴリを削除し、新しい系列とカテゴリを追加します。

```java
// チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;
// チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// デフォルトで生成されたシリーズとカテゴリを削除する
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// 新しいシリーズの追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// 新しいカテゴリの追加
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## ステップ4: シリーズデータを入力する

シリーズ 1 とシリーズ 2 の両方のシリーズ データを入力します。

```java
// 最初のチャートシリーズ
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// シリーズデータを入力中
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// 第2チャートシリーズ
series = chart.getChartData().getSeries().get_Item(1);
// シリーズデータを入力中
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## ステップ5: シリーズの自動塗りつぶし色を設定する

それでは、チャート系列の自動塗りつぶし色を設定しましょう。これにより、ライブラリが自動的に色を選択するようになります。

```java
// シリーズの自動塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## ステップ6: プレゼンテーションを保存する

最後に、グラフを含むプレゼンテーションを PowerPoint ファイルに保存します。

```java
// グラフ付きのプレゼンテーションを保存する
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Javaスライドでチャートシリーズの色を自動調整するための完全なソースコード

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
try
{
	// 最初のスライドにアクセス
	ISlide slide = presentation.getSlides().get_Item(0);
	// デフォルトデータでグラフを追加する
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// 最初の系列を値を表示に設定する
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// チャートデータシートのインデックスの設定
	int defaultWorksheetIndex = 0;
	// チャートデータワークシートの取得
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// デフォルトで生成されたシリーズとカテゴリを削除する
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// 新しいシリーズの追加
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// 新しいカテゴリの追加
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// 最初のチャートシリーズ
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// シリーズデータを入力中
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// シリーズの自動塗りつぶし色の設定
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// 第2チャートシリーズ
	series = chart.getChartData().getSeries().get_Item(1);
	// シリーズデータを入力中
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// シリーズの塗りつぶし色の設定
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// グラフ付きのプレゼンテーションを保存する
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用してグラフ付きのPowerPointプレゼンテーションを作成し、グラフ系列に自動で色を塗りつぶす方法を学びました。自動色設定により、グラフの視覚的な魅力が向上し、プレゼンテーションがより魅力的になります。必要に応じて、グラフをさらにカスタマイズすることもできます。

## よくある質問

### Aspose.Slides for Java でチャート シリーズの自動塗りつぶし色を設定するにはどうすればよいですか?

Aspose.Slides for Java でグラフ シリーズの自動塗りつぶし色を設定するには、次のコードを使用します。

```java
// シリーズの自動塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

このコードにより、ライブラリはチャートのシリーズの色を自動的に選択できるようになります。

### 必要に応じてグラフの色をカスタマイズできますか?

はい、必要に応じてグラフの色をカスタマイズできます。例では自動塗りつぶしの色を使用していますが、 `FillType` そして `SolidFillColor` シリーズの形式のプロパティ。

### グラフにさらにシリーズやカテゴリを追加するにはどうすればよいですか?

チャートに系列やカテゴリを追加するには、 `getSeries()` そして `getCategories()` チャートの手法 `ChartData` オブジェクト。データとラベルを指定して、新しいシリーズとカテゴリを追加できます。

### グラフとラベルをさらにフォーマットすることは可能ですか?

はい、必要に応じてグラフ、系列、ラベルの書式をさらに細かく設定できます。Aspose.Slides for Java は、フォント、色、スタイルなど、グラフの書式設定オプションを幅広く提供しています。書式設定オプションの詳細については、ドキュメントをご覧ください。

### Aspose.Slides for Java の使用方法に関する詳細情報はどこで入手できますか?

Aspose.Slides for Java の詳細情報と詳細なドキュメントについては、リファレンスドキュメントをご覧ください。 [ここ](https://reference。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}