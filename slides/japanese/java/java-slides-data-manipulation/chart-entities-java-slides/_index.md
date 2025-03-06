---
title: Java スライドのチャートエンティティ
linktitle: Java スライドのチャートエンティティ
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して Java スライド チャートを作成し、カスタマイズする方法を学びます。強力なチャート エンティティを使用してプレゼンテーションを強化します。
weight: 13
url: /ja/java/data-manipulation/chart-entities-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java スライドのチャートエンティティ


## Java スライドのチャートエンティティの紹介

チャートは、プレゼンテーションでデータを視覚化するための強力なツールです。ビジネス レポート、学術プレゼンテーション、またはその他の形式のコンテンツを作成する場合でも、チャートは情報を効果的に伝えるのに役立ちます。Aspose.Slides for Java はチャートを操作するための強力な機能を備えているため、Java 開発者にとって頼りになる選択肢となっています。

## 前提条件

チャート エンティティの世界に飛び込む前に、次の前提条件が満たされていることを確認してください。

- Java開発キット（JDK）がインストールされている
- Aspose.Slides for Java ライブラリがダウンロードされ、プロジェクトに追加されました
- Javaプログラミングの基礎知識

それでは、Aspose.Slides for Java を使用してグラフの作成とカスタマイズを始めましょう。

## ステップ1: プレゼンテーションの作成

最初のステップは、チャートを追加する新しいプレゼンテーションを作成することです。プレゼンテーションを作成するためのコード スニペットを次に示します。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ2: チャートの追加

プレゼンテーションの準備ができたら、グラフを追加します。この例では、マーカー付きのシンプルな折れ線グラフを追加します。手順は次のとおりです。

```java
//最初のスライドにアクセスする
ISlide slide = pres.getSlides().get_Item(0);

//サンプルチャートの追加
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## ステップ3: グラフタイトルのカスタマイズ

適切に定義されたチャートにはタイトルが必要です。チャートのタイトルを設定してみましょう。

```java
//設定チャートタイトル
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## ステップ4: グリッド線の書式設定

グラフの主グリッド線と副グリッド線の書式を設定できます。垂直軸のグリッド線の書式を設定してみましょう。

```java
//値軸の主グリッド線の形式を設定する
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

//値軸の補助グリッド線の書式を設定する
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## ステップ5: 値軸のカスタマイズ

数値軸の数値形式、最大値、最小値を制御できます。カスタマイズ方法は次のとおりです。

```java
//値軸の数値形式の設定
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

//設定チャートの最大値、最小値
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## ステップ 6: 値軸タイトルの追加

グラフにさらに情報を追加するには、値軸にタイトルを追加します。

```java
//値軸のタイトルの設定
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## ステップ 7: カテゴリ軸の書式設定

通常はデータ カテゴリを表すカテゴリ軸もカスタマイズできます。

```java
//カテゴリ軸の主グリッド線の形式を設定する
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

//カテゴリ軸の補助グリッド線の書式設定
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## ステップ8: 凡例の追加

凡例はグラフ内のデータ系列を説明するのに役立ちます。凡例をカスタマイズしてみましょう。

```java
//凡例テキストプロパティの設定
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

//重複するチャートなしでチャートの凡例を表示するよう設定する
chart.getLegend().setOverlay(true);
```

## ステップ9: プレゼンテーションを保存する

最後に、グラフを含むプレゼンテーションを保存します。

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Java スライドのチャート エンティティの完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//ディレクトリがまだ存在しない場合は作成します。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
//プレゼンテーションをインスタンス化しています// プレゼンテーションをインスタンス化しています
Presentation pres = new Presentation();
try
{
	//最初のスライドにアクセスする
	ISlide slide = pres.getSlides().get_Item(0);
	//サンプルチャートの追加
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	//設定チャートタイトル
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	//値軸の主グリッド線の形式を設定する
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	//値軸の補助グリッド線の書式を設定する
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	//値軸の数値形式の設定
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	//設定チャートの最大値、最小値
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	//値軸テキストプロパティの設定
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	//値軸のタイトルの設定
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	//設定値軸線の形式: 現在は廃止
	//chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	//カテゴリ軸の主グリッド線の形式を設定する
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	//カテゴリ軸の補助グリッド線の書式設定
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	//カテゴリ軸テキストプロパティの設定
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	//カテゴリタイトルの設定
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	//カテゴリ軸ラベルの位置を設定する
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	//カテゴリ軸ラベルの回転角度の設定
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	//凡例テキストプロパティの設定
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	//重複するチャートなしでチャートの凡例を表示するよう設定する
	chart.getLegend().setOverlay(true);
	//最初の系列を二次値軸にプロットする
	//Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	//設定表 背面壁色
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	//プロットエリアの色の設定
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	//プレゼンテーションを保存
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

この記事では、Aspose.Slides for Java を使用して、Java スライドのグラフ エンティティの世界について説明しました。グラフを作成、カスタマイズ、操作してプレゼンテーションを強化する方法を学習しました。グラフは、データを視覚的に魅力的にするだけでなく、視聴者が複雑な情報をより簡単に理解するのにも役立ちます。

## よくある質問

### グラフの種類を変更するにはどうすればよいですか?

チャートの種類を変更するには、`chart.setType()`メソッドを選択し、目的のグラフの種類を指定します。

### グラフに複数のデータ系列を追加できますか?

はい、複数のデータ系列をグラフに追加することができます。`chart.getChartData().getSeries().addSeries()`方法。

### グラフの色をカスタマイズするにはどうすればよいですか?

グリッド線、タイトル、凡例などのさまざまなグラフ要素の塗りつぶし形式を設定することで、グラフの色をカスタマイズできます。

### 3D チャートを作成できますか?

はい、Aspose.Slides for Javaは3Dチャートの作成をサポートしています。`ChartType` 3D チャート タイプを選択して作成します。

### Aspose.Slides for Java は最新の Java バージョンと互換性がありますか?

はい、Aspose.Slides for Java は定期的に更新され、最新の Java バージョンをサポートし、幅広い Java 環境との互換性を提供します。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
