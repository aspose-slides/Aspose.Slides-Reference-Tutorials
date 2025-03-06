---
title: Java スライドにドーナツ コールアウトを追加する
linktitle: Java スライドにドーナツ コールアウトを追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java スライドにドーナツ コールアウトを追加する方法を学びます。強化されたプレゼンテーションのためのソース コード付きのステップ バイ ステップ ガイド。
weight: 12
url: /ja/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides for Java を使用して Java スライドにドーナツ コールアウトを追加する方法の紹介

このチュートリアルでは、Aspose.Slides for Java を使用して、Java でスライドにドーナツ コールアウトを追加する手順を説明します。ドーナツ コールアウトは、ドーナツ グラフ内の特定のデータ ポイントを強調表示するために使用できるグラフ要素です。便宜上、ステップ バイ ステップの手順と完全なソース コードを提供します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Java開発環境
2. Aspose.Slides for Java ライブラリ
3. EclipseやIntelliJ IDEAなどの統合開発環境（IDE）
4. ドーナツ吹き出しを追加したいPowerPointプレゼンテーション

## ステップ1: Javaプロジェクトを設定する

1. 選択した IDE で新しい Java プロジェクトを作成します。
2. Aspose.Slides for Java ライブラリを依存関係としてプロジェクトに追加します。

## ステップ2: プレゼンテーションを初期化する

まず、PowerPoint プレゼンテーションを初期化し、ドーナツ コールアウトを追加するスライドを作成する必要があります。これを実現するためのコードは次のとおりです。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

必ず交換してください`"Your Document Directory"` PowerPoint プレゼンテーション ファイルへの実際のパスを入力します。

## ステップ3: ドーナツグラフを作成する

次に、スライドにドーナツ グラフを作成します。グラフの位置とサイズは、必要に応じてカスタマイズできます。ドーナツ グラフを追加するコードは次のとおりです。

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## ステップ4: ドーナツグラフをカスタマイズする

さて、ドーナツ チャートをカスタマイズします。凡例の削除、穴のサイズの設定、最初のスライスの角度の調整など、さまざまなプロパティを設定します。コードは次のとおりです。

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

このコード スニペットはドーナツ グラフのプロパティを設定します。特定のニーズに合わせて値を調整できます。

## ステップ5: ドーナツグラフにデータを追加する

それでは、ドーナツ グラフにデータを追加しましょう。また、データ ポイントの外観をカスタマイズします。これを実現するためのコードは次のとおりです。

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        //ここでデータポイントの外観をカスタマイズします
        i++;
    }
    categoryIndex++;
}
```

このコードでは、ドーナツ グラフにカテゴリとデータ ポイントを追加しています。必要に応じて、データ ポイントの外観をさらにカスタマイズできます。

## ステップ6: プレゼンテーションを保存する

最後に、ドーナツ コールアウトを追加した後は、プレゼンテーションを保存することを忘れないでください。プレゼンテーションを保存するコードは次のとおりです。

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

必ず交換してください`"chart.pptx"`希望するファイル名を入力します。

おめでとうございます! Aspose.Slides for Java を使用して、Java スライドにドーナツ コールアウトを正常に追加しました。これで、Java アプリケーションを実行して、ドーナツ グラフとコールアウトを含む PowerPoint プレゼンテーションを生成できます。

## Java スライドにドーナツ コールアウトを追加するための完全なソース コード

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
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して Java スライドにドーナツ コールアウトを追加する手順について説明しました。ドーナツ グラフの作成方法、外観のカスタマイズ方法、データ ポイントの追加方法を学習しました。この強力なライブラリを使用してプレゼンテーションをさらに強化し、さらに多くのグラフ作成オプションを自由に探索してください。

## よくある質問

### ドーナツ吹き出しの外観を変更するにはどうすればよいですか?

チャート内のデータ ポイントのプロパティを変更することで、ドーナツ コールアウトの外観をカスタマイズできます。提供されているコードでは、データ ポイントの塗りつぶしの色、線の色、フォント スタイル、その他の属性を設定する方法を確認できます。

### ドーナツ グラフにさらにデータ ポイントを追加できますか?

はい、ドーナツ グラフには必要な数だけデータ ポイントを追加できます。カテゴリとデータ ポイントを追加するコード内のループを拡張し、適切なデータと書式設定を指定するだけです。

### スライド上のドーナツ グラフの位置とサイズを調整するにはどうすればよいですか?

ドーナツグラフの位置とサイズは、`addChart`メソッド。このメソッドの 4 つの数字は、それぞれグラフの左上隅の X 座標と Y 座標、および幅と高さに対応します。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
