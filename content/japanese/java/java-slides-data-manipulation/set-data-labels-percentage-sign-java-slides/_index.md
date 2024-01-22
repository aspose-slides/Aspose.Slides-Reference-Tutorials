---
title: Java スライドでのデータ ラベルのパーセント記号の設定
linktitle: Java スライドでのデータ ラベルのパーセント記号の設定
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションでパーセント記号を使用してデータ ラベルを設定する方法を学びます。ステップバイステップのガイダンスとソース コードを使用して、魅力的なグラフを作成します。
type: docs
weight: 17
url: /ja/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## Aspose.Slides for Java でのデータ ラベルのパーセント記号の設定の概要

このガイドでは、Aspose.Slides for Java を使用してパーセント記号を使用してデータ ラベルを設定するプロセスについて説明します。積み上げ縦棒グラフを含む PowerPoint プレゼンテーションを作成し、パーセンテージを表示するようにデータ ラベルを構成します。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがプロジェクトに追加されていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/slides/java/).

## ステップ 1: 新しいプレゼンテーションを作成する

まず、Aspose.Slides を使用して新しい PowerPoint プレゼンテーションを作成します。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
// Presentationクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

## ステップ 2: スライドとグラフを追加する

次に、スライドと積み上げ縦棒グラフをプレゼンテーションに追加します。

```java
//スライドのリファレンスを取得する
ISlide slide = presentation.getSlides().get_Item(0);

//スライドに PercentsStackedColumn グラフを追加する
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## ステップ 3: 軸番号フォーマットの構成

パーセンテージを表示するには、グラフの縦軸の数値形式を構成する必要があります。

```java
//NumberFormatLinkedToSource を false に設定します
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## ステップ 4: グラフ データを追加する

シリーズとデータ ポイントを作成して、データをグラフに追加します。この例では、それぞれのデータ ポイントを持つ 2 つのシリーズを追加します。

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

## ステップ 5: データラベルをカスタマイズする

次に、データ ラベルの外観をカスタマイズしましょう。

```java
// LabelFormat プロパティの設定
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

## ステップ 6: プレゼンテーションを保存する

最後に、プレゼンテーションを PowerPoint ファイルに保存します。

```java
//プレゼンテーションをディスクに書き込む
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

それでおしまい！これで、積み上げ縦棒グラフを含む PowerPoint プレゼンテーションが作成され、Aspose.Slides for Java を使用してパーセンテージを表示するようにデータ ラベルが構成されました。

## Java スライドのセット データ ラベルのパーセント記号の完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
// Presentationクラスのインスタンスを作成する
Presentation presentation = new Presentation();
//スライドのリファレンスを取得する
ISlide slide = presentation.getSlides().get_Item(0);
//スライドに PercentsStackedColumn グラフを追加する
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
//NumberFormatLinkedToSource を false に設定します
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
// LabelFormat プロパティの設定
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

このガイドに従うことで、パーセンテージベースのデータラベルを使用して魅力的なプレゼンテーションを作成する方法を学びました。これは、ビジネスレポートや教育資料などで情報を効果的に伝えるのに特に役立ちます。

## よくある質問

### グラフシリーズの色を変更するにはどうすればよいですか?

グラフシリーズの塗りつぶしの色を変更するには、`setFill`例で示したような方法です。

### データラベルのフォントサイズをカスタマイズできますか?

はい、データ ラベルのフォント サイズは、`setFontHeight`コードで示されているプロパティ。

### グラフに系列をさらに追加するにはどうすればよいですか?

を使用して、グラフに系列を追加できます。`add`のメソッド`IChartSeriesCollection`物体。
