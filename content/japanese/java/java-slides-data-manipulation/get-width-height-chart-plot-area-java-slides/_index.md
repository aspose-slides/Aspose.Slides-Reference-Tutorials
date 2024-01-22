---
title: Java スライドのグラフ プロット領域から幅と高さを取得する
linktitle: Java スライドのグラフ プロット領域から幅と高さを取得する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java Slides でグラフのプロット領域の寸法を取得する方法を学びます。 PowerPoint の自動化スキルを強化します。
type: docs
weight: 21
url: /ja/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

## 導入

グラフは、PowerPoint プレゼンテーションでデータを視覚化する強力な方法です。場合によっては、グラフ内の要素のサイズ変更や位置変更など、さまざまな理由でグラフのプロット領域の寸法を知る必要があることがあります。このガイドでは、Java および Aspose.Slides for Java を使用してプロット領域の幅と高さを取得する方法を説明します。

## 前提条件

コードに入る前に、Aspose.Slides for Java ライブラリがインストールされ、Java プロジェクトに設定されていることを確認してください。 Aspose Web サイトからライブラリをダウンロードできます。[ここ](https://releases.aspose.com/slides/java/).

## ステップ 1: 環境のセットアップ

Aspose.Slides for Java ライブラリが Java プロジェクトに追加されていることを確認してください。これを行うには、プロジェクトの依存関係にライブラリを含めるか、JAR ファイルを手動で追加します。

## ステップ 2: PowerPoint プレゼンテーションを作成する

まずは PowerPoint プレゼンテーションを作成し、それにスライドを追加しましょう。これはチャートのコンテナとして機能します。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

交換する`"Your Document Directory"`ドキュメント ディレクトリへのパスを置き換えます。

## ステップ 3: グラフの追加

次に、集合縦棒グラフをスライドに追加しましょう。グラフのレイアウトも検証します。

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

このコードは、位置 (100, 100) に次元 (500, 350) の集合縦棒グラフを作成します。

## ステップ 4: プロット領域の寸法を取得する

グラフのプロット領域の幅と高さを取得するには、次のコードを使用できます。

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

さて、変数`x`, `y`, `w` 、 そして`h`プロット領域の X 座標、Y 座標、幅、高さのそれぞれの値が含まれます。

## ステップ 5: プレゼンテーションを保存する

最後に、プレゼンテーションをグラフとともに保存します。

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

必ず交換してください`"Chart_out.pptx"`希望の出力ファイル名を付けます。

## Java スライドのグラフ プロット領域から幅と高さを取得するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	//プレゼンテーションをグラフとともに保存する
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

この記事では、Aspose.Slides for Java API を使用して Java Slides のグラフのプロット領域の幅と高さを取得する方法について説明しました。この情報は、PowerPoint プレゼンテーション内でグラフのレイアウトを動的に調整する必要がある場合に役立ちます。

## よくある質問

### グラフの種類を集合列以外に変更するにはどうすればよいですか?

を置き換えることでグラフの種類を変更できます。`ChartType.ClusteredColumn`必要なチャート タイプの列挙を使用して、次のように指定します。`ChartType.Line`または`ChartType.Pie`.

### グラフの他のプロパティを変更できますか?

はい、Aspose.Slides for Java API を使用して、データ、ラベル、書式設定などのグラフのさまざまなプロパティを変更できます。詳細については、ドキュメントを参照してください。

### Aspose.Slides for Java は、プロフェッショナルな PowerPoint オートメーションに適していますか?

はい、Aspose.Slides for Java は、Java アプリケーションでの PowerPoint タスクを自動化するための強力なライブラリです。プレゼンテーション、スライド、図形、グラフなどを操作するための包括的な機能を提供します。

### Aspose.Slides for Java について詳しく知るにはどうすればよいですか?

 Aspose.Slides for Java ドキュメント ページで広範なドキュメントと例を見つけることができます。[ここ](https://reference.aspose.com/slides/java/).
