---
title: Java スライドの円グラフ
linktitle: Java スライドの円グラフ
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションで美しい円グラフを作成する方法を学びます。 Java 開発者向けのソース コードを含むステップバイステップ ガイド。
type: docs
weight: 23
url: /ja/java/chart-data-manipulation/pie-chart-java-slides/
---

## Aspose.Slides を使用した Java Slides での円グラフの作成の概要

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションで円グラフを作成する方法を説明します。開始に役立つ段階的な手順と Java ソース コードを提供します。このガイドは、Aspose.Slides for Java を使用して開発環境がすでにセットアップされていることを前提としています。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがプロジェクトにインストールされ、構成されていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/slides/java/).

## ステップ 1: 必要なライブラリをインポートする

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

必要なクラスを Aspose.Slides ライブラリからインポートしてください。

## ステップ 2: プレゼンテーションを初期化する

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";

// PPTX ファイルを表すプレゼンテーション クラスをインスタンス化します。
Presentation presentation = new Presentation();
```

 PowerPoint ファイルを表す新しいプレゼンテーション オブジェクトを作成します。交換する`"Your Document Directory"`プレゼンテーションを保存する実際のパスに置き換えます。

## ステップ 3: スライドを追加する

```java
//最初のスライドにアクセスする
ISlide slide = presentation.getSlides().get_Item(0);
```

円グラフを追加するプレゼンテーションの最初のスライドを取得します。

## ステップ 4: 円グラフを追加する

```java
//デフォルトのデータを含む円グラフを追加する
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

指定した位置とサイズで円グラフをスライドに追加します。

## ステップ 5: グラフのタイトルを設定する

```java
//グラフのタイトルを設定する
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

円グラフのタイトルを設定します。必要に応じてタイトルをカスタマイズできます。

## ステップ 6: グラフ データをカスタマイズする

```java
//最初の系列を値を表示するように設定します
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

//チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;

//チャートデータワークシートの取得
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

//デフォルトで生成されたシリーズとカテゴリを削除する
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

//新しいカテゴリの追加
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

//新しいシリーズの追加
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

//シリーズデータの入力
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

カテゴリと系列を追加し、それらの値を設定して、グラフ データをカスタマイズします。この例には、3 つのカテゴリと、対応するデータ ポイントを持つ 1 つのシリーズがあります。

## ステップ 7: 円グラフのセクターをカスタマイズする

```java
//セクターの色の設定
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

//各セクターの外観をカスタマイズする
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
//セクターの境界線をカスタマイズする
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

//同様の方法で他のセクターをカスタマイズする
```

円グラフの各セクターの外観をカスタマイズします。色、境界線のスタイル、その他の視覚的なプロパティを変更できます。

## ステップ 8: データラベルをカスタマイズする

```java
//データラベルをカスタマイズする
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

//同様の方法で他のデータポイントのデータラベルをカスタマイズします
```

円グラフの各データ ポイントのデータ ラベルをカスタマイズします。グラフに表示する値を制御できます。

## ステップ 9: 引き出し線を表示する

```java
//チャートの引き出し線を表示する
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

引き出し線を有効にして、データ ラベルを対応するセクターに接続します。

## ステップ 10: 円グラフの回転角度を設定する

```java
//円グラフのセクターの回転角度を設定する
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

円グラフのセクターの回転角度を設定します。この例では、180 度に設定します。

## ステップ 11: プレゼンテーションを保存する

```java
//円グラフを含むプレゼンテーションを保存する
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

円グラフを含むプレゼンテーションを指定したディレクトリに保存します。

## Java スライドの円グラフの完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
// PPTX ファイルを表すプレゼンテーション クラスをインスタンス化します。
Presentation presentation = new Presentation();
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
//新しいバージョンでは動作しません
//新しいポイントの追加とセクターの色の設定
//series.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
//セクター境界の設定
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
//セクター境界の設定
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
//セクター境界の設定
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
//新しいシリーズのカテゴリごとにカスタム ラベルを作成する
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
//lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
//チャートの引き出し線の表示
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
//円グラフのセクターの回転角度の設定
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
//プレゼンテーションをグラフとともに保存する
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## 結論

Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションで円グラフを作成することに成功しました。特定の要件に応じて、グラフの外観とデータ ラベルをカスタマイズできます。このチュートリアルでは基本的な例を提供しますが、必要に応じてグラフをさらに拡張およびカスタマイズできます。

## よくある質問

### 円グラフの個々のセクターの色を変更するにはどうすればよいですか?

円グラフの個々のセクターの色を変更するには、各データ ポイントの塗りつぶしの色をカスタマイズできます。提供されたコード例では、`getSolidFillColor().setColor()`方法。希望の外観を実現するために色の値を変更できます。

### 円グラフにさらにカテゴリやデータ系列を追加できますか?

はい、円グラフにカテゴリやデータ系列を追加できます。これを行うには、`getChartData().getCategories().add()`そして`getChartData().getSeries().add()`例に示すように、メソッド。新しいカテゴリとシリーズに適切なデータとラベルを指定するだけで、グラフを拡張できます。

### データラベルの外観をカスタマイズするにはどうすればよいですか?

データラベルの外観をカスタマイズするには、`getDataLabelFormat()`各データポイントのラベルのメソッド。この例では、次を使用してデータ ラベルの値を表示する方法を示しました。`getDataLabelFormat().setShowValue(true)`。表示する値を制御したり、凡例キーを表示したり、その他の書式設定オプションを調整したりすることで、データ ラベルをさらにカスタマイズできます。

### 円グラフのタイトルを変更できますか?

はい、円グラフのタイトルを変更できます。提供されたコードでは、次を使用してグラフのタイトルを設定します。`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` 。交換できます`"Sample Title"`希望のタイトルテキストを付けます。

### 円グラフを含む生成されたプレゼンテーションを保存するにはどうすればよいですか?

円グラフを含むプレゼンテーションを保存するには、`presentation.save()`方法。プレゼンテーションを保存する形式とともに、目的のファイル パスと名前を指定します。例えば：
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

必ず正しいファイル パスと形式を指定してください。

### Aspose.Slides for Java を使用して他のタイプのグラフを作成できますか?

はい、Aspose.Slides for Java は、棒グラフ、折れ線グラフなど、さまざまな種類のグラフをサポートしています。を変更することで、さまざまなタイプのグラフを作成できます。`ChartType`グラフを追加するとき。さまざまなタイプのグラフの作成の詳細については、Aspose.Slides のドキュメントを参照してください。

### Aspose.Slides for Java を使用するための詳細情報と例を見つけるにはどうすればよいですか?

詳細、詳細なドキュメント、追加の例については、次のサイトを参照してください。[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/)。ライブラリを効果的に使用するための包括的なリソースを提供します。