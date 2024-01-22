---
title: Java スライドのグラフ データ ラベルの実際の位置を取得する
linktitle: Java スライドのグラフ データ ラベルの実際の位置を取得する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java Slides のグラフ データ ラベルの実際の位置を取得する方法を学びます。ソースコード付きのステップバイステップガイド。
type: docs
weight: 18
url: /ja/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

## Java スライドのグラフ データ ラベルの実際の位置を取得する方法の概要

このチュートリアルでは、Aspose.Slides for Java を使用してグラフ データ ラベルの実際の位置を取得する方法を学習します。グラフを含む PowerPoint プレゼンテーションを生成し、データ ラベルをカスタマイズして、これらのデータ ラベルの位置を表す図形を追加する Java プログラムを作成します。

## 前提条件

始める前に、Java プロジェクトに Aspose.Slides for Java ライブラリが設定されていることを確認してください。

## ステップ 1: PowerPoint プレゼンテーションを作成する

まず、新しい PowerPoint プレゼンテーションを作成し、そこにグラフを追加しましょう。チュートリアルの後半でグラフのデータ ラベルをカスタマイズします。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## ステップ 2: データラベルをカスタマイズする
次に、グラフ シリーズのデータ ラベルをカスタマイズしましょう。位置を設定し、値を表示します。

```java
try {
    // ... (前のコード)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (残りのコード)
} finally {
    if (pres != null) pres.dispose();
}
```

## ステップ 3: データラベルの実際の位置を取得する
このステップでは、グラフ シリーズのデータ ポイントを反復処理し、4 より大きい値を持つデータ ラベルの実際の位置を取得します。次に、これらの位置を表すために楕円を追加します。

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
    // ... (残りのコード)
} finally {
    if (pres != null) pres.dispose();
}
```

## ステップ 4: プレゼンテーションを保存する
最後に、生成されたプレゼンテーションをファイルに保存します。

```java
try {
    // ... (前のコード)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Java スライドのチャート データ ラベルの実際の位置を取得するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//TODO
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

このチュートリアルでは、Aspose.Slides for Java を使用して Java Slides 内のグラフ データ ラベルの実際の位置を取得する方法を学習しました。この知識を利用して、カスタマイズされたデータ ラベルとその位置の視覚的表現によって PowerPoint プレゼンテーションを強化できるようになりました。

## よくある質問

### グラフ内のデータラベルをカスタマイズするにはどうすればよいですか?

グラフ内のデータ ラベルをカスタマイズするには、`setDefaultDataLabelFormat`チャート シリーズのメソッドを使用し、位置や表示設定などのプロパティを設定します。例えば：
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### データラベルの位置を表す図形を追加するにはどうすればよいですか?

グラフ シリーズのデータ ポイントを反復処理し、`getActualX`, `getActualY`, `getActualWidth` 、 そして`getActualHeight`データラベルのメソッドを使用してその位置を取得します。次に、`addAutoShape`方法。以下に例を示します。
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### 生成されたプレゼンテーションを保存するにはどうすればよいですか?

生成されたプレゼンテーションは、`save`方法。目的のファイル パスと`SaveFormat`パラメータとして。例えば：
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```