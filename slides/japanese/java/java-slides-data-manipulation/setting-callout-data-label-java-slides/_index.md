---
"description": "Aspose.Slides for Javaでデータラベルの吹き出しを設定する方法を学びましょう。ソースコード付きのステップバイステップガイドです。"
"linktitle": "Javaスライドでデータラベルの吹き出しを設定する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドでデータラベルの吹き出しを設定する"
"url": "/ja/java/data-manipulation/setting-callout-data-label-java-slides/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドでデータラベルの吹き出しを設定する


## Aspose.Slides for Java でデータラベルの吹き出しを設定する方法の紹介

このチュートリアルでは、Aspose.Slides for Java を使用して、グラフ内のデータラベルに吹き出しを設定する方法を説明します。吹き出しは、グラフ内の特定のデータポイントを強調表示するのに役立ちます。コードを段階的に説明し、必要なソースコードを提供します。

## 前提条件

- Aspose.Slides for Java がインストールされている必要があります。
- Java プロジェクトを作成し、Aspose.Slides ライブラリをプロジェクトに追加します。

## ステップ1: プレゼンテーションを作成し、グラフを追加する

まず、プレゼンテーションを作成し、スライドにグラフを追加する必要があります。 `"Your Document Directory"` ドキュメント ディレクトリへの実際のパスを入力します。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## ステップ2: チャートを構成する

次に、凡例、系列、カテゴリなどのプロパティを設定してグラフを構成します。

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// シリーズとカテゴリを設定します（シリーズとカテゴリの数を調整できます）
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // ここにデータポイントを追加
        // ...
        i++;
    }
    categoryIndex++;
}
```

## ステップ3: データラベルをカスタマイズする

ここで、最後のシリーズのコールアウトの設定など、データ ラベルをカスタマイズします。

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // データ ポイントの書式設定 (塗りつぶし、線など) をカスタマイズします

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        // ラベルの書式設定（フォント、塗りつぶしなど）をカスタマイズする
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // 吹き出しを有効にする
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## ステップ4: プレゼンテーションを保存する

最後に、設定したグラフを含むプレゼンテーションを保存します。

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

これで、Aspose.Slides for Java を使用してグラフ内のデータラベルに吹き出しを設定することができました。グラフとデータの要件に合わせてコードをカスタマイズしてください。

## Javaスライドでデータラベルの吹き出しを設定するための完全なソースコード

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save("chart.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用してグラフのデータラベルに吹き出しを設定する方法を解説しました。吹き出しは、グラフやプレゼンテーションで特定のデータポイントを強調するのに役立つ便利なツールです。このカスタマイズを実現するためのステップバイステップガイドとソースコードをご用意しました。

## よくある質問

### データ ラベルの外観をカスタマイズするにはどうすればよいですか?

データラベルの外観をカスタマイズするには、フォント、塗りつぶし、線のスタイルなどのプロパティを変更します。例:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### データ ラベルのコールアウトを有効または無効にするにはどうすればよいですか?

データラベルの吹き出しを有効または無効にするには、 `setShowLabelAsDataCallout` メソッド。設定する `true` 吹き出しを有効にして `false` 無効にします。

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // 吹き出しを有効にする
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // コールアウトを無効にする
```

### データ ラベルの引き出し線をカスタマイズできますか?

はい、データラベルの引き出し線は、線のスタイル、色、幅などのプロパティを使ってカスタマイズできます。例えば：

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // 引き出し線を有効にする
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

これらは、Aspose.Slides for Java におけるデータラベルと吹き出しの一般的なカスタマイズオプションです。さらに、特定のニーズに合わせて外観をカスタマイズすることもできます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}