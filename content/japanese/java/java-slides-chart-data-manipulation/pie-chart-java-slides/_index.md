---
title: Java スライドの円グラフ
linktitle: Java スライドの円グラフ
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションで魅力的な円グラフを作成する方法を学びます。Java 開発者向けのソース コード付きのステップバイステップ ガイドです。
type: docs
weight: 23
url: /ja/java/chart-data-manipulation/pie-chart-java-slides/
---

## Aspose.Slides を使用して Java スライドで円グラフを作成する方法の紹介

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションで円グラフを作成する方法を説明します。作業を開始できるように、ステップバイステップの手順と Java ソース コードを提供します。このガイドでは、Aspose.Slides for Java を使用して開発環境を既にセットアップしていることを前提としています。

## 前提条件

始める前に、Aspose.Slides for Javaライブラリがプロジェクトにインストールされ、設定されていることを確認してください。ダウンロードはここから行えます。[ここ](https://releases.aspose.com/slides/java/).

## ステップ1: 必要なライブラリをインポートする

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Aspose.Slides ライブラリから必要なクラスを必ずインポートしてください。

## ステップ2: プレゼンテーションを初期化する

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";

// PPTXファイルを表すプレゼンテーションクラスをインスタンス化する
Presentation presentation = new Presentation();
```

 PowerPointファイルを表す新しいプレゼンテーションオブジェクトを作成します。`"Your Document Directory"`プレゼンテーションを保存する実際のパスを入力します。

## ステップ3: スライドを追加する

```java
//最初のスライドにアクセス
ISlide slide = presentation.getSlides().get_Item(0);
```

円グラフを追加するプレゼンテーションの最初のスライドを取得します。

## ステップ4: 円グラフを追加する

```java
//デフォルトデータで円グラフを追加する
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

指定した位置とサイズでスライドに円グラフを追加します。

## ステップ5: グラフのタイトルを設定する

```java
//グラフのタイトルを設定する
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

円グラフのタイトルを設定します。必要に応じてタイトルをカスタマイズできます。

## ステップ6: グラフデータをカスタマイズする

```java
//最初のシリーズに値を表示するように設定する
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

//チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;

//チャートデータワークシートの取得
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

//デフォルトで生成されたシリーズとカテゴリを削除する
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

//新しいカテゴリーの追加
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

カテゴリとシリーズを追加し、その値を設定して、グラフ データをカスタマイズします。この例では、3 つのカテゴリと、対応するデータ ポイントを持つ 1 つのシリーズがあります。

## ステップ7: 円グラフのセクターをカスタマイズする

```java
//セクターの色を設定する
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

//各セクターの外観をカスタマイズする
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
//セクター境界をカスタマイズする
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

//他のセクターも同様にカスタマイズする
```

円グラフの各セクターの外観をカスタマイズします。色、境界線のスタイル、その他の視覚的なプロパティを変更できます。

## ステップ8: データラベルをカスタマイズする

```java
//データラベルをカスタマイズする
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

//同様の方法で他のデータポイントのデータラベルをカスタマイズします
```

円グラフの各データ ポイントのデータ ラベルをカスタマイズします。グラフに表示される値を制御できます。

## ステップ9: 引き出し線を表示する

```java
//グラフの引き出し線を表示する
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

リーダー ラインを有効にして、データ ラベルを対応するセクターに接続します。

## ステップ10: 円グラフの回転角度を設定する

```java
//円グラフセクターの回転角度を設定する
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

円グラフセクターの回転角度を設定します。この例では、180 度に設定しています。

## ステップ11: プレゼンテーションを保存する

```java
//円グラフ付きのプレゼンテーションを保存する
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

円グラフを含むプレゼンテーションを指定されたディレクトリに保存します。

## Java スライドの円グラフの完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// PPTXファイルを表すプレゼンテーションクラスをインスタンス化する
Presentation presentation = new Presentation();
//最初のスライドにアクセス
ISlide slides = presentation.getSlides().get_Item(0);
//デフォルトデータでグラフを追加
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
//設定チャートタイトル
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
//最初のシリーズを値を表示に設定
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
//チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;
//チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//デフォルトで生成されたシリーズとカテゴリを削除する
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
//新しいカテゴリーの追加
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
//新しいシリーズの追加
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
//シリーズデータを入力中
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
//新しいシリーズの各カテゴリにカスタムラベルを作成する
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
//チャートの引き出し線を表示する
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
//円グラフセクターの回転角度の設定
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
//グラフ付きのプレゼンテーションを保存する
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## 結論

Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションに円グラフを作成しました。グラフの外観とデータ ラベルは、特定の要件に応じてカスタマイズできます。このチュートリアルでは基本的な例を示しますが、必要に応じてグラフをさらに強化およびカスタマイズできます。

## よくある質問

### 円グラフ内の個々のセクターの色を変更するにはどうすればよいですか?

円グラフの各セクターの色を変更するには、各データポイントの塗りつぶし色をカスタマイズします。提供されているコード例では、`getSolidFillColor().setColor()`方法。色の値を変更して、希望する外観を実現できます。

### 円グラフにさらにカテゴリやデータ系列を追加できますか?

はい、円グラフにカテゴリやデータ系列を追加することができます。これを行うには、`getChartData().getCategories().add()`そして`getChartData().getSeries().add()`例に示すように、新しいカテゴリとシリーズに適切なデータとラベルを指定するだけで、グラフを拡張できます。

### データ ラベルの外観をカスタマイズするにはどうすればよいですか?

データラベルの外観をカスタマイズするには、`getDataLabelFormat()`各データポイントのラベルにメソッドを適用します。例では、データラベルに値を表示する方法を示しました。`getDataLabelFormat().setShowValue(true)`表示される値を制御したり、凡例キーを表示したり、その他の書式設定オプションを調整したりすることで、データ ラベルをさらにカスタマイズできます。

### 円グラフのタイトルを変更できますか?

はい、円グラフのタイトルは変更できます。提供されているコードでは、グラフのタイトルを次のように設定しています。`chart.getChartTitle().addTextFrameForOverriding("Sample Title")`置き換えることができます`"Sample Title"`希望するタイトルテキストを入力します。

### 円グラフを含む生成されたプレゼンテーションを保存するにはどうすればよいですか?

円グラフ付きのプレゼンテーションを保存するには、`presentation.save()`方法。プレゼンテーションを保存する形式とともに、希望のファイル パスと名前を指定します。例:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

正しいファイル パスと形式を指定してください。

### Aspose.Slides for Java を使用して他の種類のグラフを作成できますか?

はい、Aspose.Slides for Javaは、棒グラフ、折れ線グラフなど、さまざまなグラフタイプをサポートしています。`ChartType`グラフを追加するとき。さまざまな種類のグラフを作成する方法の詳細については、Aspose.Slides のドキュメントを参照してください。

### Aspose.Slides for Java の操作に関する詳細情報や例はどこで見つけることができますか?

詳細情報、詳細なドキュメント、追加の例については、[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/)ライブラリを効果的に使用するための包括的なリソースを提供します。