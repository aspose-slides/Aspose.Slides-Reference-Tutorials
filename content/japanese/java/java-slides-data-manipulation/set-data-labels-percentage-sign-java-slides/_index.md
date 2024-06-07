---
title: Java スライドでデータ ラベルのパーセンテージ記号を設定する
linktitle: Java スライドでデータ ラベルのパーセンテージ記号を設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションでパーセント記号付きのデータ ラベルを設定する方法を学びます。ステップ バイ ステップのガイダンスとソース コードを使用して、魅力的なグラフを作成します。
type: docs
weight: 17
url: /ja/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## Aspose.Slides for Java でデータ ラベルのパーセンテージ記号を設定する方法の紹介

このガイドでは、Aspose.Slides for Java を使用して、パーセント記号付きのデータ ラベルを設定する手順について説明します。積み上げ縦棒グラフを含む PowerPoint プレゼンテーションを作成し、データ ラベルを構成してパーセントを表示します。

## 前提条件

始める前に、Aspose.Slides for Javaライブラリがプロジェクトに追加されていることを確認してください。ダウンロードはこちらからできます。[ここ](https://releases.aspose.com/slides/java/).

## ステップ1: 新しいプレゼンテーションを作成する

まず、Aspose.Slides を使用して新しい PowerPoint プレゼンテーションを作成します。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

## ステップ2: スライドとグラフを追加する

次に、プレゼンテーションにスライドと積み上げ縦棒グラフを追加します。

```java
//スライドの参照を取得する
ISlide slide = presentation.getSlides().get_Item(0);

//スライドにパーセント積み上げ縦棒グラフを追加する
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## ステップ3: 軸の数値形式を設定する

パーセンテージを表示するには、グラフの垂直軸の数値形式を設定する必要があります。

```java
//NumberFormatLinkedToSource を false に設定する
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## ステップ4: チャートデータを追加する

シリーズとデータ ポイントを作成して、チャートにデータを追加します。この例では、それぞれのデータ ポイントを持つ 2 つのシリーズを追加します。

```java
//チャートデータワークシートの取得
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

//新しいシリーズを追加
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

//新しいシリーズを追加
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## ステップ5: データラベルをカスタマイズする

次に、データ ラベルの外観をカスタマイズしましょう。

```java
// LabelFormatプロパティの設定
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## ステップ6: プレゼンテーションを保存する

最後に、プレゼンテーションを PowerPoint ファイルに保存します。

```java
//プレゼンテーションをディスクに書き込む
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

これで完了です。Aspose.Slides for Java を使用して、積み上げ縦棒グラフを含む PowerPoint プレゼンテーションを作成し、パーセンテージを表示するようにデータ ラベルを構成しました。

## Java スライドでデータ ラベルのパーセンテージ記号を設定するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
//スライドの参照を取得する
ISlide slide = presentation.getSlides().get_Item(0);
//スライドにパーセント積み上げ縦棒グラフを追加する
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
//NumberFormatLinkedToSource を false に設定する
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
//チャートデータワークシートの取得
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
//新しいシリーズを追加
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
//シリーズの塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// LabelFormatプロパティの設定
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
//新しいシリーズを追加
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
//塗りつぶしの種類と色の設定
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
//プレゼンテーションをディスクに書き込む
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## 結論

このガイドに従うことで、パーセンテージベースのデータ ラベルを使用して魅力的なプレゼンテーションを作成する方法を学習しました。これは、ビジネス レポートや教育資料などで情報を効果的に伝えるのに特に役立ちます。

## よくある質問

### チャートシリーズの色を変更するにはどうすればよいですか?

チャートシリーズの塗りつぶし色を変更するには、`setFill`例に示す方法を使用します。

### データ ラベルのフォント サイズをカスタマイズできますか?

はい、データラベルのフォントサイズをカスタマイズするには、`setFontHeight`コードに示されているプロパティ。

### チャートにさらにシリーズを追加するにはどうすればよいですか?

チャートにシリーズを追加するには、`add`方法`IChartSeriesCollection`物体。
