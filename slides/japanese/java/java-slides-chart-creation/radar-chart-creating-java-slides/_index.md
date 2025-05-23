---
"description": "Aspose.Slides for Java API を使用して、Java PowerPoint プレゼンテーションでレーダー チャートを作成する方法を学習します。"
"linktitle": "Javaスライドでレーダーチャートを作成する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドでレーダーチャートを作成する"
"url": "/ja/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドでレーダーチャートを作成する


## Javaスライドでレーダーチャートを作成する方法の紹介

このチュートリアルでは、Aspose.Slides for Java API を使用してレーダーチャートを作成する手順を説明します。レーダーチャートは、データを円形に視覚化するのに役立ち、複数のデータ系列を比較しやすくなります。Java ソースコードとともに、ステップバイステップの手順を説明します。

## 前提条件

始める前に、Aspose.Slides for Javaライブラリがプロジェクトに統合されていることを確認してください。ライブラリは以下からダウンロードできます。 [ここ](https://releases。aspose.com/slides/java/).

## ステップ1: プレゼンテーションの設定

まず、新しい PowerPoint プレゼンテーションを設定し、それにスライドを追加してみましょう。

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## ステップ2: レーダーチャートを追加する

次に、スライドにレーダーチャートを追加します。チャートの位置とサイズを指定します。

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## ステップ3: チャートデータの設定

次に、グラフデータを設定します。データワークブックの作成、カテゴリの追加、系列の追加を行います。

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// グラフのタイトルを設定する
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// デフォルトで生成されたシリーズとカテゴリを削除する
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// 新しいカテゴリの追加
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// 新しいシリーズの追加
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## ステップ4: シリーズデータを入力する

ここで、レーダー チャートの系列データを入力します。

```java
// シリーズ1のシリーズデータを入力する
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// シリーズの色を設定する
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// シリーズ2のシリーズデータを入力する
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// シリーズの色を設定する
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## ステップ5: 軸と凡例のカスタマイズ

レーダー チャートの軸と凡例をカスタマイズしましょう。

```java
// 凡例の位置を設定する
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// カテゴリ軸のテキストプロパティの設定
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// 凡例のテキストプロパティの設定
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// 値軸テキストプロパティの設定
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// 値軸の数値形式の設定
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// 設定表主要単位値
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## ステップ6: プレゼンテーションを保存する

最後に、レーダーチャートを含む生成されたプレゼンテーションを保存します。

。

```java
pres.save(outPath, SaveFormat.Pptx);
```

これで完了です！Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションにレーダーチャートを作成できました。このサンプルをさらにカスタマイズして、ご自身のニーズに合わせてください。

## Javaスライドでレーダーチャートを作成するための完全なソースコード

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// 最初のスライドにアクセス
	ISlide sld = pres.getSlides().get_Item(0);
	// レーダーチャートを追加
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// チャートデータシートのインデックスの設定
	int defaultWorksheetIndex = 0;
	// チャートデータの取得ワークシート
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// グラフのタイトルを設定する
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// デフォルトで生成されたシリーズとカテゴリを削除する
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// 新しいカテゴリの追加
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// 新しいシリーズの追加
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// シリーズデータを入力中
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// シリーズの色を設定する
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// 別のシリーズデータを入力中
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// シリーズの色を設定する
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// 凡例の位置を設定する
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// カテゴリ軸のテキストプロパティの設定
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// 凡例のテキストプロパティの設定
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// 値軸テキストプロパティの設定
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// 値軸の数値形式の設定
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// 設定表主要単位値
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// 生成されたプレゼンテーションを保存する
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションでレーダーチャートを作成する方法を学習しました。これらの概念を応用すれば、Java アプリケーションでデータを効果的に視覚化し、提示することができます。

## よくある質問

### グラフのタイトルを変更するにはどうすればいいですか?

グラフのタイトルを変更するには、次の行を変更します。
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### レーダーチャートにさらにデータ系列を追加できますか?

はい、追加するシリーズごとに「手順 3」と「手順 4」の手順に従って、さらにデータ シリーズを追加できます。

### グラフの色をカスタマイズするにはどうすればいいですか?

設定する線を変更することで、シリーズの色をカスタマイズできます。 `SolidFillColor` 各シリーズのプロパティ。例:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### 軸ラベルと書式を変更するにはどうすればよいですか?

軸ラベルとフォント サイズや色などの書式をカスタマイズするには、「手順 5」を参照してください。

### チャートを別のファイル形式で保存するにはどうすればよいですか?

出力形式を変更するには、ファイル拡張子を変更します。 `outPath` 変数と適切な `SaveFormat`たとえば、PDFとして保存するには、 `SaveFormat。Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}