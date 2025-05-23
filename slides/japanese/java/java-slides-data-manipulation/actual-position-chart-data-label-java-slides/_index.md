---
"description": "Aspose.Slides for Javaを使用して、Javaスライド内のグラフデータラベルの実際の位置を取得する方法を学びます。ソースコード付きのステップバイステップガイドです。"
"linktitle": "Javaスライドでチャートデータラベルの実際の位置を取得する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドでチャートデータラベルの実際の位置を取得する"
"url": "/ja/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドでチャートデータラベルの実際の位置を取得する


## Javaスライドでチャートデータラベルの実際の位置を取得する方法の紹介

このチュートリアルでは、Aspose.Slides for Java を使用してグラフのデータラベルの実際の位置を取得する方法を学習します。グラフを含むPowerPointプレゼンテーションを生成し、データラベルをカスタマイズし、それらのデータラベルの位置を表す図形を追加するJavaプログラムを作成します。

## 前提条件

始める前に、Java プロジェクトに Aspose.Slides for Java ライブラリが設定されていることを確認してください。

## ステップ1: PowerPointプレゼンテーションを作成する

まず、新しいPowerPointプレゼンテーションを作成し、グラフを追加しましょう。グラフのデータラベルは、チュートリアルの後半でカスタマイズします。

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## ステップ2: データラベルをカスタマイズする
それでは、グラフ系列のデータラベルをカスタマイズしてみましょう。ラベルの位置を設定し、値を表示します。

```java
try {
    // ...（前のコード）
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ...（残りのコード）
} finally {
    if (pres != null) pres.dispose();
}
```

## ステップ3: データラベルの実際の位置を取得する
この手順では、グラフ系列のデータ ポイントを反復処理し、値が 4 より大きいデータ ラベルの実際の位置を取得します。次に、これらの位置を表す省略記号を追加します。

```java
try {
    // ...（前のコード）
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ...（残りのコード）
} finally {
    if (pres != null) pres.dispose();
}
```

## ステップ4: プレゼンテーションを保存する
最後に、生成されたプレゼンテーションをファイルに保存します。

```java
try {
    // ...（前のコード）
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Javaスライドでチャートデータラベルの実際の位置を取得するための完全なソースコード

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//やるべきこと
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して、Java スライド内のグラフのデータラベルの実際の位置を取得する方法を学習しました。この知識を活用して、カスタマイズされたデータラベルとその位置を視覚的に表現することで、PowerPoint プレゼンテーションをより魅力的にすることができます。

## よくある質問

### グラフ内のデータ ラベルをカスタマイズするにはどうすればよいですか?

グラフのデータラベルをカスタマイズするには、 `setDefaultDataLabelFormat` チャート系列のメソッドを使用して、位置や表示/非表示などのプロパティを設定します。例:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### データ ラベルの位置を表す図形を追加するにはどうすればよいですか?

チャートシリーズのデータポイントを反復処理し、 `getActualX`、 `getActualY`、 `getActualWidth`、 そして `getActualHeight` データラベルの位置を取得するには、データラベルのメソッドを使用します。その後、 `addAutoShape` 方法。以下に例を示します。
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### 生成されたプレゼンテーションを保存するにはどうすればよいですか?

生成されたプレゼンテーションは、 `save` 方法。希望するファイルパスと `SaveFormat` パラメータとして。例えば：
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}