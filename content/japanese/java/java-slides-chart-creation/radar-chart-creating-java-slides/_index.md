---
title: Java スライドでレーダー チャートを作成する
linktitle: Java スライドでレーダー チャートを作成する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java API を使用して、Java PowerPoint プレゼンテーションでレーダー チャートを作成する方法を学びます。
type: docs
weight: 10
url: /ja/java/chart-creation/radar-chart-creating-java-slides/
---

## Java スライドでのレーダー チャートの作成の概要

このチュートリアルでは、Aspose.Slides for Java API を使用してレーダー チャートを作成するプロセスを説明します。レーダー チャートは、データを円形パターンで視覚化するのに役立ち、複数のデータ系列を比較しやすくなります。 Java ソース コードとともに段階的な手順を説明します。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがプロジェクトに統合されていることを確認してください。ライブラリはからダウンロードできます[ここ](https://releases.aspose.com/slides/java/).

## ステップ 1: プレゼンテーションのセットアップ

まず、新しい PowerPoint プレゼンテーションを設定し、それにスライドを追加します。

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## ステップ 2: レーダー チャートの追加

次に、レーダー チャートをスライドに追加します。チャートの位置と寸法を指定します。

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## ステップ3：チャートデータの設定

チャートデータを設定していきます。これには、データ ワークブックの作成、カテゴリの追加、シリーズの追加が含まれます。

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

//グラフのタイトルを設定する
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

//デフォルトで生成されたシリーズとカテゴリを削除する
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

//新しいカテゴリの追加
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

//新しいシリーズの追加
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## ステップ 4: シリーズ データの入力

次に、レーダー チャートの系列データを入力します。

```java
//シリーズ 1 のシリーズ データを入力する
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

//セットシリーズカラー
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

//シリーズ 2 のシリーズ データを入力する
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

//セットシリーズカラー
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## ステップ 5: 軸と凡例のカスタマイズ

レーダー チャートの軸と凡例をカスタマイズしましょう。

```java
//凡例の位置を設定する
ichart.getLegend().setPosition(LegendPositionType.Bottom);

//カテゴリ軸のテキストプロパティの設定
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

//凡例テキストのプロパティの設定
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

//値軸のテキストプロパティの設定
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

//設定値の軸番号形式
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

//チャートのメジャーユニット値の設定
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## ステップ 6: プレゼンテーションを保存する

最後に、生成されたプレゼンテーションをレーダー チャートとともに保存します。

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

それでおしまい！ Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションでレーダー チャートを正常に作成できました。特定のニーズに合わせてこの例をさらにカスタマイズできるようになりました。

## Java スライドで作成するレーダー チャートの完全なソース コード

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	//最初のスライドにアクセスする
	ISlide sld = pres.getSlides().get_Item(0);
	//レーダーチャートを追加
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	//チャートデータシートのインデックスの設定
	int defaultWorksheetIndex = 0;
	//チャートデータの取得ワークシート
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	//グラフのタイトルを設定する
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	//デフォルトで生成されたシリーズとカテゴリを削除する
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	//新しいカテゴリの追加
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	//新しいシリーズの追加
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	//シリーズデータを入力中です
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	//セットシリーズカラー
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	//別のシリーズ データを入力中です
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	//セットシリーズカラー
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	//凡例の位置を設定する
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	//カテゴリ軸のテキストプロパティの設定
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	//凡例テキストのプロパティの設定
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	//値軸のテキストプロパティの設定
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	//設定値の軸番号形式
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	//チャートのメジャーユニット値の設定
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	//生成されたプレゼンテーションを保存する
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションでレーダー チャートを作成する方法を学習しました。これらの概念を適用して、Java アプリケーションでデータを効果的に視覚化して表示できます。

## よくある質問

### グラフのタイトルを変更するにはどうすればよいですか?

グラフのタイトルを変更するには、次の行を変更します。
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### レーダー チャートにさらにデータ シリーズを追加できますか?

はい、含める追加の系列ごとに「ステップ 3」と「ステップ 4」の手順に従って、さらにデータ系列を追加できます。

### グラフの色をカスタマイズするにはどうすればよいですか?

シリーズの色をカスタマイズするには、`SolidFillColor`各シリーズのプロパティ。例えば：
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### 軸のラベルと書式を変更するにはどうすればよいですか?

フォント サイズや色などの軸ラベルと書式設定をカスタマイズするには、「ステップ 5」を参照してください。

### チャートを別のファイル形式で保存するにはどうすればよいですか?

ファイル拡張子を変更することで出力形式を変更できます。`outPath`変数と適切な使用`SaveFormat`。たとえば、PDF として保存するには、次を使用します。`SaveFormat.Pdf`.