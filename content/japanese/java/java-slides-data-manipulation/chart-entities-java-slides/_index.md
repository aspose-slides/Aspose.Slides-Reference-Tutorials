---
title: Java スライドのグラフ エンティティ
linktitle: Java スライドのグラフ エンティティ
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して Java Slides グラフを作成およびカスタマイズする方法を学びます。強力なグラフ エンティティを使用してプレゼンテーションを強化します。
type: docs
weight: 13
url: /ja/java/data-manipulation/chart-entities-java-slides/
---

## Java スライドのグラフ エンティティの概要

グラフは、プレゼンテーションでデータを視覚化するための強力なツールです。ビジネス レポート、学術プレゼンテーション、その他の形式のコンテンツを作成する場合、グラフは情報を効果的に伝えるのに役立ちます。 Aspose.Slides for Java は、グラフを操作するための強力な機能を提供しており、Java 開発者にとって頼りになる選択肢となっています。

## 前提条件

チャート エンティティの世界に入る前に、次の前提条件が満たされていることを確認してください。

- Java 開発キット (JDK) がインストールされている
- Aspose.Slides for Java ライブラリがダウンロードされ、プロジェクトに追加されました
- Java プログラミングの基本的な知識

それでは、Aspose.Slides for Java を使用してグラフの作成とカスタマイズを始めましょう。

## ステップ 1: プレゼンテーションを作成する

最初のステップは、グラフを追加する新しいプレゼンテーションを作成することです。プレゼンテーションを作成するコードのスニペットを次に示します。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ 2: グラフの追加

プレゼンテーションの準備ができたら、グラフを追加します。この例では、マーカー付きの単純な折れ線グラフを追加します。その方法は次のとおりです。

```java
//最初のスライドにアクセスする
ISlide slide = pres.getSlides().get_Item(0);

//サンプルチャートの追加
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## ステップ 3: グラフのタイトルをカスタマイズする

明確に定義されたグラフにはタイトルが必要です。グラフのタイトルを設定しましょう。

```java
//チャートタイトルの設定
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## ステップ 4: グリッド線の書式設定

グラフの主グリッド線と副グリッド線の書式を設定できます。垂直軸のグリッド線の書式を設定しましょう。

```java
//値軸の主グリッド線の形式を設定する
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

//値軸の補助グリッド線の形式を設定する
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## ステップ 5: 値軸のカスタマイズ

数値軸の数値形式、最大値、最小値を制御できます。カスタマイズする方法は次のとおりです。

```java
//設定値の軸番号形式
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

//チャートの最大値、最小値の設定
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## ステップ 6: 値軸のタイトルを追加する

グラフの情報をさらに増やすために、値の軸にタイトルを追加できます。

```java
//設定値軸タイトル
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## ステップ 7: カテゴリ軸の書式設定

通常、データ カテゴリを表すカテゴリ軸もカスタマイズできます。

```java
//カテゴリ軸の主グリッド線の形式を設定する
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

//カテゴリ軸の補助グリッド線の形式を設定する
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## ステップ 8: 凡例の追加

凡例は、グラフ内のデータ系列を説明するのに役立ちます。凡例をカスタマイズしてみましょう。

```java
//凡例テキストのプロパティの設定
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

//グラフを重複させずにグラフの凡例を表示するように設定します
chart.getLegend().setOverlay(true);
```

## ステップ 9: プレゼンテーションを保存する

最後に、プレゼンテーションをグラフとともに保存します。

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Java スライドのグラフ エンティティの完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//ディレクトリが存在しない場合は作成します。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
//プレゼンテーションのインスタンス化// プレゼンテーションのインスタンス化
Presentation pres = new Presentation();
try
{
	//最初のスライドにアクセスする
	ISlide slide = pres.getSlides().get_Item(0);
	//サンプルチャートの追加
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	//チャートタイトルの設定
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
	//値軸の補助グリッド線の形式を設定する
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	//設定値の軸番号形式
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	//チャートの最大値、最小値の設定
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	//値軸のテキストプロパティの設定
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	//設定値軸タイトル
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	//設定値軸線形式 : 現在廃止
	//chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	//カテゴリ軸の主グリッド線の形式を設定する
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	//カテゴリ軸の補助グリッド線の形式を設定する
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	//カテゴリ軸のテキストプロパティの設定
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
	//カテゴリ軸ラベル位置の設定
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	//カテゴリ軸テーブル回転角度の設定
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	//凡例テキストのプロパティの設定
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	//グラフを重複させずにグラフの凡例を表示するように設定します
	chart.getLegend().setOverlay(true);
	//最初の系列を 2 次値軸にプロットする
	//Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	//設定チャートの後壁の色
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	//プロットエリアの色の設定
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	//プレゼンテーションの保存
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

この記事では、Aspose.Slides for Java を使用して Java Slides のグラフ エンティティの世界を探索しました。グラフを作成、カスタマイズ、操作してプレゼンテーションを強化する方法を学習しました。グラフはデータを視覚的に魅力的なものにするだけでなく、視聴者が複雑な情報をより簡単に理解するのにも役立ちます。

## よくある質問

### グラフの種類を変更するにはどうすればよいですか?

グラフの種類を変更するには、`chart.setType()`メソッドを選択し、目的のグラフの種類を指定します。

### 複数のデータ系列をグラフに追加できますか?

はい、次のコマンドを使用して複数のデータ系列をグラフに追加できます。`chart.getChartData().getSeries().addSeries()`方法。

### グラフの色をカスタマイズするにはどうすればよいですか?

グリッド線、タイトル、凡例などのさまざまなグラフ要素の塗りつぶし形式を設定することで、グラフの色をカスタマイズできます。

### 3D グラフを作成できますか?

はい、Aspose.Slides for Java は 3D グラフの作成をサポートしています。設定できるのは、`ChartType` 3D グラフ タイプに変更して作成します。

### Aspose.Slides for Java は最新の Java バージョンと互換性がありますか?

はい。Aspose.Slides for Java は、最新の Java バージョンをサポートするために定期的に更新され、幅広い Java 環境にわたる互換性を提供します。