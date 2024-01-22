---
title: Java スライドでの円グラフのスライス色の自動設定
linktitle: Java スライドでの円グラフのスライス色の自動設定
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java PowerPoint プレゼンテーションで自動スライス カラーを使用した動的な円グラフを作成する方法を学びます。ソースコード付きのステップバイステップガイド。
type: docs
weight: 24
url: /ja/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

## Java スライドでの円グラフのスライス色の自動設定の概要

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションで円グラフを作成し、グラフの自動スライス カラーを設定する方法を説明します。ソースコードとともに段階的なガイダンスを提供します。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがインストールされ、Java プロジェクトに設定されていることを確認してください。このライブラリは、Aspose Web サイトからダウンロードできます。[Java 用 Aspose.Slides をダウンロード](https://releases.aspose.com/slides/java/).

## ステップ 1: 必要なパッケージをインポートする

まず、Aspose.Slides for Java から必要なパッケージをインポートする必要があります。

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## ステップ 2: PowerPoint プレゼンテーションを作成する

インスタンス化します`Presentation`新しい PowerPoint プレゼンテーションを作成するクラス:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## ステップ 3: スライドを追加する

プレゼンテーションの最初のスライドにアクセスし、デフォルト データを含むグラフをそれに追加します。

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## ステップ 4: グラフのタイトルを設定する

グラフのタイトルを設定します。

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## ステップ 5: グラフ データを構成する

最初の系列の値を表示するようにグラフを設定し、グラフ データを構成します。

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## ステップ 6: カテゴリとシリーズを追加する

新しいカテゴリとシリーズをグラフに追加します。

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## ステップ 7: シリーズ データを入力する

円グラフの系列データを入力します。

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## ステップ 8: さまざまなスライスの色を有効にする

円グラフのさまざまなスライスの色を有効にします。

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## ステップ 9: プレゼンテーションを保存する

最後に、プレゼンテーションを PowerPoint ファイルに保存します。

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Java スライドで円グラフのスライスの自動カラーを設定するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
// PPTX ファイルを表すプレゼンテーション クラスをインスタンス化します。
Presentation presentation = new Presentation();
try
{
	//最初のスライドにアクセスする
	ISlide slides = presentation.getSlides().get_Item(0);
	//デフォルトのデータを含むグラフを追加する
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	//設定表タイトル
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	//最初のシリーズを「値を表示」に設定します
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	//チャートデータシートのインデックスの設定
	int defaultWorksheetIndex = 0;
	//チャートデータワークシートの取得
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	//デフォルトで生成されたシリーズとカテゴリを削除する
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	//新しいカテゴリの追加
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	//新しいシリーズの追加
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	//シリーズデータを入力中です
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

Aspose.Slides for Java を使用して PowerPoint プレゼンテーションで円グラフを作成し、自動スライス カラーを設定することができました。このステップバイステップのガイドでは、これを実現するために必要なソース コードを提供します。必要に応じて、グラフとプレゼンテーションをさらにカスタマイズできます。

## よくある質問

### 円グラフの個々のスライスの色をカスタマイズするにはどうすればよいですか?

円グラフの個々のスライスの色をカスタマイズするには、`getAutomaticSeriesColors`メソッドを使用してデフォルトの配色を取得し、必要に応じて色を変更します。以下に例を示します。

```java
//デフォルトの配色を取得する
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

//必要に応じて色を変更します
colors.get_Item(0).setColor(Color.RED); //最初のスライスの色を赤に設定します
colors.get_Item(1).setColor(Color.BLUE); // 番目のスライスの色を青に設定します
//必要に応じてさらに色の変更を追加します
```

### 円グラフに凡例を追加するにはどうすればよいですか?

円グラフに凡例を追加するには、`getLegend`メソッドを作成し、次のように設定します。

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); //凡例の位置を設定する
legend.setOverlay(true); //チャート上に凡例を表示する
```

### タイトルのフォントやスタイルを変更できますか?

はい、タイトルのフォントとスタイルを変更できます。次のコードを使用して、タイトルのフォントとスタイルを設定します。

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); //フォントサイズを設定する
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); //タイトルを太字にする
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); //タイトルを斜体にする
```

必要に応じて、フォント サイズ、太さ、斜体スタイルを調整できます。