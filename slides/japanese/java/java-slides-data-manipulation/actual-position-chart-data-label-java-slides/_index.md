---
title: Java スライドでチャート データ ラベルの実際の位置を取得する
linktitle: Java スライドでチャート データ ラベルの実際の位置を取得する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java スライドのグラフ データ ラベルの実際の位置を取得する方法を学びます。ソース コードを使用したステップ バイ ステップ ガイド。
weight: 18
url: /ja/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java スライドでチャート データ ラベルの実際の位置を取得する方法の紹介

このチュートリアルでは、Aspose.Slides for Java を使用してグラフ データ ラベルの実際の位置を取得する方法を学習します。グラフを含む PowerPoint プレゼンテーションを生成し、データ ラベルをカスタマイズし、これらのデータ ラベルの位置を表す図形を追加する Java プログラムを作成します。

## 前提条件

始める前に、Java プロジェクトに Aspose.Slides for Java ライブラリが設定されていることを確認してください。

## ステップ1: PowerPointプレゼンテーションを作成する

まず、新しい PowerPoint プレゼンテーションを作成し、それにグラフを追加しましょう。グラフのデータ ラベルはチュートリアルの後半でカスタマイズします。

```java
//ドキュメント ディレクトリへのパス。
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
次に、グラフシリーズのデータ ラベルをカスタマイズします。ラベルの位置を設定し、値を表示します。

```java
try {
    // ... (前のコード)
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
この手順では、グラフ シリーズのデータ ポイントを反復処理し、値が 4 より大きいデータ ラベルの実際の位置を取得します。次に、これらの位置を表す省略記号を追加します。

```java
try {
    // ... (前のコード)
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
    // ... (前のコード)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Java スライドでチャート データ ラベルの実際の位置を取得するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
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

このチュートリアルでは、Aspose.Slides for Java を使用して Java スライドのグラフ データ ラベルの実際の位置を取得する方法を学習しました。この知識を使用して、カスタマイズされたデータ ラベルとその位置の視覚的表現で PowerPoint プレゼンテーションを強化できます。

## よくある質問

### グラフ内のデータ ラベルをカスタマイズするにはどうすればよいですか?

グラフのデータラベルをカスタマイズするには、`setDefaultDataLabelFormat`メソッドをチャート シリーズに適用し、位置や表示などのプロパティを設定します。例:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### データ ラベルの位置を表す図形を追加するにはどうすればよいですか?

チャートシリーズのデータポイントを反復処理し、`getActualX`, `getActualY`, `getActualWidth` 、 そして`getActualHeight`データラベルの位置を取得するには、データラベルのメソッドを使用します。次に、`addAutoShape`方法。次に例を示します。
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### 生成されたプレゼンテーションを保存するにはどうすればよいですか?

生成されたプレゼンテーションは、`save`方法。希望するファイルパスと`SaveFormat`パラメータとして。例:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
