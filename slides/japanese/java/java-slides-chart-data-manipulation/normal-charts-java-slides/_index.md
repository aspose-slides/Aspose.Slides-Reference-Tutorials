---
"description": "Aspose.Slides for Javaを使用して、Javaスライドで標準グラフを作成します。PowerPointプレゼンテーションでグラフを作成、カスタマイズ、保存するためのステップバイステップガイドとソースコードです。"
"linktitle": "Javaスライドの通常のチャート"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドの通常のチャート"
"url": "/ja/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドの通常のチャート


## Javaスライドでの正規グラフの紹介

このチュートリアルでは、Aspose.Slides for Java API を使用して、Java Slides で通常のグラフを作成する手順を詳しく説明します。PowerPoint プレゼンテーションで集合縦棒グラフを作成する方法を、ステップバイステップの手順とソースコードを使って説明します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Aspose.Slides for Java API がインストールされています。
2. Java 開発環境をセットアップしました。
3. Java プログラミングの基礎知識。

## ステップ1: プロジェクトの設定

プロジェクト用のディレクトリがあることを確認してください。コードに記載されているように、「Your Document Directory」と名付けましょう。これは実際のプロジェクトディレクトリへのパスに置き換えても構いません。

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// ディレクトリがまだ存在しない場合は作成します。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## ステップ2: プレゼンテーションの作成

それでは、PowerPoint プレゼンテーションを作成し、最初のスライドにアクセスしてみましょう。

```java
// PPTXファイルを表すプレゼンテーションクラスをインスタンス化する
Presentation pres = new Presentation();
// 最初のスライドにアクセス
ISlide sld = pres.getSlides().get_Item(0);
```

## ステップ3: グラフの追加

スライドに集合縦棒グラフを追加し、タイトルを設定します。

```java
// デフォルトデータでグラフを追加する
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// 設定チャートタイトル
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## ステップ4: チャートデータの設定

次に、シリーズとカテゴリを定義してグラフデータを設定します。

```java
// 最初の系列を値を表示に設定する
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;

// チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// デフォルトで生成されたシリーズとカテゴリを削除する
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// 新しいシリーズの追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// 新しいカテゴリの追加
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## ステップ5: シリーズデータを入力する

それでは、グラフの系列データ ポイントを入力しましょう。

```java
// 最初のチャートシリーズ
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// シリーズデータの入力
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// シリーズの塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// 第2チャートシリーズ
series = chart.getChartData().getSeries().get_Item(1);

// シリーズデータの入力
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// シリーズの塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## ステップ6: ラベルのカスタマイズ

グラフシリーズのデータラベルをカスタマイズしましょう。

```java
// 最初のラベルにはカテゴリ名が表示されます
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// シリーズ名と区切り文字を含む3番目のラベルの値を表示する
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## ステップ7: プレゼンテーションを保存する

最後に、チャートを含むプレゼンテーションをプロジェクト ディレクトリに保存します。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

これで完了です！Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションに集合縦棒グラフを作成できました。このグラフは、必要に応じてさらにカスタマイズできます。

## Javaスライドの通常チャートの完全なソースコード

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// ディレクトリがまだ存在しない場合は作成します。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// PPTXファイルを表すプレゼンテーションクラスをインスタンス化する
Presentation pres = new Presentation();
// 最初のスライドにアクセス
ISlide sld = pres.getSlides().get_Item(0);
// デフォルトデータでグラフを追加する
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// 設定チャートタイトル
// Chart.getChartTitle().getTextFrameForOverriding().setText("サンプルタイトル");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// 最初の系列を値を表示に設定する
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;
// チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// デフォルトで生成されたシリーズとカテゴリを削除する
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// 新しいシリーズの追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// 新しいカテゴリの追加
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// 最初のチャートシリーズ
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// シリーズデータを入力中
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// シリーズの塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// 第2チャートシリーズ
series = chart.getChartData().getSeries().get_Item(1);
// シリーズデータを入力中
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// シリーズの塗りつぶし色の設定
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// 最初のラベルにはカテゴリ名が表示されます
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// 3番目のラベルの値を表示
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// グラフ付きのプレゼンテーションを保存する
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# 結論

このチュートリアルでは、Aspose.Slides for Java API を使用して、Java Slides で通常のグラフを作成する方法を学習しました。PowerPoint プレゼンテーションで集合縦棒グラフを作成する手順を、ソースコード付きでステップバイステップで解説しました。

## よくある質問

### グラフの種類を変更するにはどうすればよいですか?

チャートの種類を変更するには、 `ChartType` チャートを追加する際のパラメータ `sld.getShapes().addChart()`Aspose.Slides で利用可能なさまざまなグラフ タイプから選択できます。

### チャートシリーズの色を変更できますか?

はい、各系列の塗りつぶし色を設定することで、チャート系列の色を変更できます。 `series。getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### グラフにカテゴリやシリーズを追加するにはどうすればよいですか?

新しいデータポイントとラベルを追加することで、チャートにカテゴリやシリーズを追加できます。 `chart.getChartData().getCategories().add()` そして `chart.getChartData().getSeries().add()` 方法。

### グラフのタイトルをさらにカスタマイズするにはどうすればいいでしょうか?

グラフのタイトルをさらにカスタマイズするには、以下のプロパティを変更します。 `chart.getChartTitle()` テキストの配置、フォント サイズ、色など。

### チャートを別のファイル形式で保存するにはどうすればよいですか?

チャートを別のファイル形式で保存するには、 `SaveFormat` パラメータの `pres.save()` 方法を希望の形式 (例: PDF、PNG、JPEG) に変更します。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}