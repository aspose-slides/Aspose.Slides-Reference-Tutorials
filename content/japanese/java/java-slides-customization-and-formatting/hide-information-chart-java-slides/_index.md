---
title: Java スライドのグラフから情報を非表示にする
linktitle: Java スライドのグラフから情報を非表示にする
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java Slides でグラフ要素を非表示にする方法を学びます。ステップバイステップのガイダンスとソース コードを使用して、プレゼンテーションをカスタマイズして、明瞭さと美しさを実現します。
type: docs
weight: 13
url: /ja/java/customization-and-formatting/hide-information-chart-java-slides/
---

## Java スライドのグラフから情報を非表示にする方法の概要

このチュートリアルでは、Aspose.Slides for Java API を使用して Java Slides のグラフからさまざまな要素を非表示にする方法を検討します。このコードを使用して、プレゼンテーションの必要に応じてグラフをカスタマイズできます。

## ステップ 1: 環境のセットアップ

始める前に、Aspose.Slides for Java ライブラリがプロジェクトに追加されていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/slides/java/).

## ステップ 2: 新しいプレゼンテーションを作成する

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ 3: スライドにグラフを追加する

マーカー付きの折れ線グラフをスライドに追加してから、グラフのさまざまな要素を非表示にします。

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## ステップ 4: グラフのタイトルを非表示にする

次のようにしてグラフのタイトルを非表示にすることができます。

```java
chart.setTitle(false);
```

## ステップ 5: 値軸を非表示にする

値の軸 (垂直軸) を非表示にするには、次のコードを使用します。

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## ステップ 6: カテゴリ軸を非表示にする

カテゴリ軸 (水平軸) を非表示にするには、次のコードを使用します。

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## ステップ 7: 凡例を非表示にする

次のようにしてグラフの凡例を非表示にすることができます。

```java
chart.setLegend(false);
```

## ステップ 8: 主なグリッド線を非表示にする

横軸の主グリッド線を非表示にするには、次のコードを使用できます。

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## ステップ 9: シリーズを削除する

チャートからすべての系列を削除したい場合は、次のようなループを使用できます。

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## ステップ 10: チャート シリーズをカスタマイズする

必要に応じてグラフシリーズをカスタマイズできます。この例では、マーカー スタイル、データ ラベルの位置、マーカー サイズ、線の色、破線のスタイルを変更します。

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## ステップ 11: プレゼンテーションを保存する

最後に、プレゼンテーションをファイルに保存します。

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

それでおしまい！ Aspose.Slides for Java を使用して、Java Slides のグラフからさまざまな要素を非表示にすることができました。特定の要件に合わせて、必要に応じてグラフとプレゼンテーションをさらにカスタマイズできます。

## Java スライドのチャートから情報を非表示にするための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//グラフのタイトルを非表示にする
	chart.setTitle(false);
	///値軸を非表示にする
	chart.getAxes().getVerticalAxis().setVisible(false);
	//カテゴリ軸の可視性
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//伝説を隠す
	chart.setLegend(false);
	//MajorGridLine の非表示
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//系列の線色の設定
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## 結論

このステップバイステップ ガイドでは、Aspose.Slides for Java API を使用して Java Slides のグラフからさまざまな要素を非表示にする方法を説明しました。これは、プレゼンテーション用にチャートをカスタマイズし、より視覚的に魅力的なものにしたり、特定のニーズに合わせたりする必要がある場合に非常に役立ちます。

## よくある質問

### グラフ要素の外観をさらにカスタマイズするにはどうすればよいですか?

グラフシリーズ、マーカー、ラベル、形式の対応するプロパティにアクセスすることで、線の色、塗りつぶしの色、マーカーのスタイルなどのグラフ要素のさまざまなプロパティをカスタマイズできます。

### グラフ内の特定のデータ ポイントを非表示にすることはできますか?

はい、グラフ シリーズのデータを操作することで、特定のデータ ポイントを非表示にすることができます。データ ポイントを削除するか、その値を null に設定して非表示にすることができます。

### グラフに系列を追加するにはどうすればよいですか?

を使用して、グラフに系列をさらに追加できます。`IChartData.getSeries().add`メソッドを作成し、新しいシリーズのデータ ポイントを指定します。

### グラフの種類を動的に変更することはできますか?

はい、目的のタイプの新しいグラフを作成し、古いグラフから新しいグラフにデータをコピーすることで、グラフの種類を動的に変更できます。

### グラフのタイトルと軸のラベルをプログラムで変更するにはどうすればよいですか?

それぞれのプロパティにアクセスし、必要なテキストと書式を設定することで、グラフと軸のタイトルとラベルを設定できます。