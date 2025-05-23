---
"description": "Aspose.Slides for Java を使って、Java スライドのグラフ要素を非表示にする方法を学びましょう。ステップバイステップのガイドとソースコードを使って、プレゼンテーションをカスタマイズし、明瞭性と美しさを高めましょう。"
"linktitle": "Javaスライドのチャートから情報を非表示にする"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドのチャートから情報を非表示にする"
"url": "/ja/java/customization-and-formatting/hide-information-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドのチャートから情報を非表示にする


## Javaスライドでチャートから情報を非表示にする方法の紹介

このチュートリアルでは、Aspose.Slides for Java API を使用して、Java スライドのグラフからさまざまな要素を非表示にする方法を説明します。このコードを使用して、プレゼンテーションに合わせてグラフをカスタマイズできます。

## ステップ1: 環境の設定

始める前に、Aspose.Slides for Javaライブラリがプロジェクトに追加されていることを確認してください。ダウンロードはこちらから可能です。 [ここ](https://releases。aspose.com/slides/java/).

## ステップ2: 新しいプレゼンテーションを作成する

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ3: スライドにグラフを追加する

スライドにマーカー付きの折れ線グラフを追加し、グラフのさまざまな要素を非表示にします。

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## ステップ4: グラフのタイトルを非表示にする

次のようにしてグラフのタイトルを非表示にすることができます。

```java
chart.setTitle(false);
```

## ステップ5: 値軸を非表示にする

値軸 (垂直軸) を非表示にするには、次のコードを使用します。

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## ステップ6: カテゴリ軸を非表示にする

カテゴリ軸 (水平軸) を非表示にするには、次のコードを使用します。

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## ステップ7: 凡例を非表示にする

次のようにしてグラフの凡例を非表示にすることができます。

```java
chart.setLegend(false);
```

## ステップ8: 主要なグリッド線を非表示にする

水平軸の主要なグリッド線を非表示にするには、次のコードを使用できます。

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## ステップ9: シリーズを削除する

チャートからすべてのシリーズを削除する場合は、次のようなループを使用できます。

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## ステップ10: グラフシリーズをカスタマイズする

必要に応じてグラフ系列をカスタマイズできます。この例では、マーカーのスタイル、データラベルの位置、マーカーのサイズ、線の色、破線スタイルを変更します。

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

## ステップ11: プレゼンテーションを保存する

最後に、プレゼンテーションをファイルに保存します。

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

これで完了です！Aspose.Slides for Java を使用して、Java スライドのグラフからさまざまな要素を非表示にできました。必要に応じて、グラフやプレゼンテーションをさらにカスタマイズできます。

## Javaスライドのチャートから情報を非表示にする完全なソースコード

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//チャートのタイトルを非表示にする
	chart.setTitle(false);
	///値軸を非表示にする
	chart.getAxes().getVerticalAxis().setVisible(false);
	//カテゴリ軸の表示
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//伝説を隠す
	chart.setLegend(false);
	//主要グリッド線を非表示にする
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
	//系列線の色の設定
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

このステップバイステップガイドでは、Aspose.Slides for Java API を使用して、Java スライドのグラフからさまざまな要素を非表示にする方法を説明しました。これは、プレゼンテーション用のグラフをカスタマイズし、より視覚的に魅力的なものにしたり、特定のニーズに合わせてカスタマイズしたりする必要がある場合に非常に役立ちます。

## よくある質問

### グラフ要素の外観をさらにカスタマイズするにはどうすればよいですか?

グラフの系列、マーカー、ラベル、書式の対応するプロパティにアクセスすることで、線の色、塗りつぶしの色、マーカーのスタイルなど、グラフ要素のさまざまなプロパティをカスタマイズできます。

### グラフ内の特定のデータ ポイントを非表示にすることはできますか?

はい、チャート系列のデータを操作することで、特定のデータポイントを非表示にすることができます。データポイントを削除するか、値をnullに設定することで非表示にすることができます。

### チャートにさらにシリーズを追加するにはどうすればよいですか?

チャートにさらにシリーズを追加するには、 `IChartData.getSeries().add` メソッドを使用して、新しいシリーズのデータ ポイントを指定します。

### チャートの種類を動的に変更することは可能ですか?

はい、希望するタイプの新しいグラフを作成し、古いグラフから新しいグラフにデータをコピーすることで、グラフの種類を動的に変更できます。

### グラフのタイトルと軸ラベルをプログラムで変更するにはどうすればよいですか?

それぞれのプロパティにアクセスし、必要なテキストと書式を設定することで、グラフと軸のタイトルとラベルを設定できます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}