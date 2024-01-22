---
title: Java スライドの通常のグラフ
linktitle: Java スライドの通常のグラフ
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java Slides で通常のグラフを作成します。 PowerPoint プレゼンテーションでグラフを作成、カスタマイズ、保存するためのステップバイステップのガイドとソース コード。
type: docs
weight: 21
url: /ja/java/chart-data-manipulation/normal-charts-java-slides/
---

## Java スライドでの標準チャートの紹介

このチュートリアルでは、Aspose.Slides for Java API を使用して Java Slides で通常のグラフを作成するプロセスを説明します。ソース コードとともに段階的な手順を使用して、PowerPoint プレゼンテーションで集合縦棒グラフを作成する方法を示します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Aspose.Slides for Java API がインストールされています。
2. Java 開発環境がセットアップされています。
3. Java プログラミングの基本的な知識。

## ステップ 1: プロジェクトのセットアップ

プロジェクト用のディレクトリがあることを確認してください。コードに記載されているように、これを「Your Document Directory」と呼びます。これをプロジェクト ディレクトリへの実際のパスに置き換えることができます。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//ディレクトリが存在しない場合は作成します。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## ステップ 2: プレゼンテーションを作成する

次に、PowerPoint プレゼンテーションを作成し、その最初のスライドにアクセスしてみましょう。

```java
// PPTX ファイルを表すプレゼンテーション クラスをインスタンス化します。
Presentation pres = new Presentation();
//最初のスライドにアクセスする
ISlide sld = pres.getSlides().get_Item(0);
```

## ステップ 3: グラフの追加

集合縦棒グラフをスライドに追加し、そのタイトルを設定します。

```java
//デフォルトのデータを含むグラフを追加する
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
//設定表タイトル
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## ステップ4: チャートデータの設定

次に、系列とカテゴリを定義してグラフデータを設定します。

```java
//最初のシリーズを「値を表示」に設定します
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

//チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;

//チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

//デフォルトで生成されたシリーズとカテゴリを削除する
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

//新しいシリーズの追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

//新しいカテゴリの追加
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## ステップ 5: シリーズ データの入力

次に、グラフに系列データ ポイントを入力しましょう。

```java
//最初のチャート シリーズを取得する
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

//シリーズデータの入力
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

//シリーズの塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// 番目のチャート シリーズを取得する
series = chart.getChartData().getSeries().get_Item(1);

//シリーズデータの入力
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

//シリーズの塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## ステップ 6: ラベルのカスタマイズ

グラフシリーズのデータラベルをカスタマイズしましょう。

```java
//最初のラベルにはカテゴリ名が表示されます
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

//シリーズ名と区切り記号を使用して 3 番目のラベルの値を表示します
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## ステップ 7: プレゼンテーションを保存する

最後に、グラフを含むプレゼンテーションをプロジェクト ディレクトリに保存します。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

それでおしまい！ Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションで集合縦棒グラフを作成することに成功しました。要件に応じてこのグラフをさらにカスタマイズできます。

## Java スライドの標準グラフの完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//ディレクトリが存在しない場合は作成します。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// PPTX ファイルを表すプレゼンテーション クラスをインスタンス化します。
Presentation pres = new Presentation();
//最初のスライドにアクセスする
ISlide sld = pres.getSlides().get_Item(0);
//デフォルトのデータを含むグラフを追加する
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
//設定表タイトル
//Chart.getChartTitle().getTextFrameForOverriding().setText("サンプル タイトル");
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
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
//新しいシリーズの追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
//新しいカテゴリの追加
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
//最初のチャート シリーズを取得する
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//シリーズデータを入力中です
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
//シリーズの塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// 番目のチャート シリーズを取得する
series = chart.getChartData().getSeries().get_Item(1);
//シリーズデータを入力中です
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
//シリーズの塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
//最初のラベルにはカテゴリ名が表示されます
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// 番目のラベルの値を表示
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
//プレゼンテーションをグラフとともに保存する
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# 結論

このチュートリアルでは、Aspose.Slides for Java API を使用して Java Slides で通常のグラフを作成する方法を学習しました。 PowerPoint プレゼンテーションで集合縦棒グラフを作成するためのソース コードを含むステップバイステップ ガイドを説明しました。

## よくある質問

### グラフの種類を変更するにはどうすればよいですか?

グラフの種類を変更するには、`ChartType`を使用してチャートを追加するときのパラメータ`sld.getShapes().addChart()`。 Aspose.Slides で使用できるさまざまなグラフの種類から選択できます。

### グラフシリーズの色を変更できますか?

はい、次を使用して各系列の塗りつぶしの色を設定することで、グラフ系列の色を変更できます。`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### グラフにカテゴリやシリーズを追加するにはどうすればよいですか?

グラフにカテゴリや系列を追加するには、`chart.getChartData().getCategories().add()`そして`chart.getChartData().getSeries().add()`方法。

### グラフのタイトルをさらにカスタマイズするにはどうすればよいですか?

のプロパティを変更することで、グラフのタイトルをさらにカスタマイズできます。`chart.getChartTitle()`テキストの配置、フォント サイズ、色など。

### チャートを別のファイル形式で保存するにはどうすればよいですか?

チャートを別のファイル形式で保存するには、`SaveFormat`のパラメータ`pres.save()`メソッドを希望の形式 (PDF、PNG、JPEG など) に変換します。