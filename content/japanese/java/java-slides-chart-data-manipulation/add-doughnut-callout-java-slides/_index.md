---
title: Java スライドにドーナツ吹き出しを追加する
linktitle: Java スライドにドーナツ吹き出しを追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java スライドにドーナツ コールアウトを追加する方法を学びます。強化されたプレゼンテーションのためのソース コードを含むステップバイステップ ガイド。
type: docs
weight: 12
url: /ja/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

## Aspose.Slides for Java を使用して Java スライドにドーナツ コールアウトを追加する方法の概要

このチュートリアルでは、Aspose.Slides for Java を使用して Java のスライドにドーナツ コールアウトを追加するプロセスを説明します。ドーナツ コールアウトは、ドーナツ チャート内の特定のデータ ポイントを強調表示するために使用できるチャート要素です。あなたの便宜のために、段階的な手順と完全なソースコードを提供します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Java開発環境
2. Java ライブラリ用の Aspose.Slides
3. Eclipse や IntelliJ IDEA などの統合開発環境 (IDE)
4. ドーナツ吹き出しを追加する PowerPoint プレゼンテーション

## ステップ 1: Java プロジェクトをセットアップする

1. 選択した IDE で新しい Java プロジェクトを作成します。
2. Aspose.Slides for Java ライブラリを依存関係としてプロジェクトに追加します。

## ステップ 2: プレゼンテーションを初期化する

まず、PowerPoint プレゼンテーションを初期化し、ドーナツ吹き出しを追加するスライドを作成する必要があります。これを実現するコードは次のとおりです。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

必ず交換してください`"Your Document Directory"` PowerPoint プレゼンテーション ファイルへの実際のパスを含めます。

## ステップ 3: ドーナツ グラフを作成する

次に、スライド上にドーナツ グラフを作成します。要件に応じてチャートの位置とサイズをカスタマイズできます。ドーナツ チャートを追加するコードは次のとおりです。

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## ステップ 4: ドーナツ チャートをカスタマイズする

次に、ドーナツ チャートをカスタマイズします。凡例の削除、穴のサイズの構成、最初のスライス角度の調整など、さまざまなプロパティを設定します。コードは次のとおりです。

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

このコード スニペットは、ドーナツ チャートのプロパティを設定します。特定のニーズに合わせて値を調整できます。

## ステップ 5: ドーナツ チャートにデータを追加する

次に、ドーナツ チャートにデータを追加しましょう。データポイントの外観もカスタマイズします。これを実現するコードは次のとおりです。

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

このコードでは、ドーナツ チャートにカテゴリとデータ ポイントを追加しています。必要に応じて、データ ポイントの外観をさらにカスタマイズできます。

## ステップ 6: プレゼンテーションを保存する

最後に、ドーナツ吹き出しを追加した後、忘れずにプレゼンテーションを保存してください。プレゼンテーションを保存するコードは次のとおりです。

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

必ず交換してください`"chart.pptx"`任意のファイル名を付けてください。

おめでとう！ Aspose.Slides for Java を使用して Java スライドにドーナツ コールアウトを正常に追加しました。これで、Java アプリケーションを実行して、ドーナツ グラフと吹き出しを含む PowerPoint プレゼンテーションを生成できるようになりました。

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

このチュートリアルでは、Aspose.Slides for Java を使用して Java スライドにドーナツ コールアウトを追加するプロセスについて説明しました。ドーナツ グラフを作成し、外観をカスタマイズし、データ ポイントを追加する方法を学習しました。この強力なライブラリを使用してプレゼンテーションをさらに強化し、より多くのグラフ オプションを試してみてください。

## よくある質問

### ドーナツ吹き出しの外観を変更するにはどうすればよいですか?

グラフ内のデータ ポイントのプロパティを変更することで、ドーナツ コールアウトの外観をカスタマイズできます。提供されたコードでは、データ ポイントの塗りつぶしの色、線の色、フォント スタイル、その他の属性を設定する方法を確認できます。

### ドーナツ チャートにさらにデータ ポイントを追加できますか?

はい、必要な数のデータ ポイントをドーナツ チャートに追加できます。カテゴリとデータ ポイントが追加されるコード内のループを拡張し、適切なデータと書式設定を提供するだけです。

### スライド上のドーナツ チャートの位置とサイズを調整するにはどうすればよいですか?

ドーナツ チャートの位置とサイズを変更するには、`addChart`方法。このメソッドの 4 つの数値は、それぞれグラフの左上隅の X 座標と Y 座標、幅と高さに対応します。