---
title: Java スライドのチャート プロット領域から幅と高さを取得する
linktitle: Java スライドのチャート プロット領域から幅と高さを取得する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java スライドでチャートのプロット領域の寸法を取得する方法を学びます。PowerPoint の自動化スキルを強化します。
weight: 21
url: /ja/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## 導入

グラフは、PowerPoint プレゼンテーションでデータを視覚化する強力な方法です。グラフ内の要素のサイズ変更や再配置など、さまざまな理由でグラフのプロット領域のサイズを知る必要がある場合があります。このガイドでは、Java と Aspose.Slides for Java を使用してプロット領域の幅と高さを取得する方法を説明します。

## 前提条件

コードに入る前に、JavaプロジェクトにAspose.Slides for Javaライブラリがインストールされ、設定されていることを確認してください。ライブラリはAsposeのWebサイトからダウンロードできます。[ここ](https://releases.aspose.com/slides/java/).

## ステップ1: 環境の設定

Aspose.Slides for Java ライブラリが Java プロジェクトに追加されていることを確認します。これを行うには、ライブラリをプロジェクトの依存関係に含めるか、JAR ファイルを手動で追加します。

## ステップ2: PowerPointプレゼンテーションの作成

まず、PowerPoint プレゼンテーションを作成し、それにスライドを追加します。これがチャートのコンテナーとして機能します。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

交換する`"Your Document Directory"`ドキュメント ディレクトリへのパスを入力します。

## ステップ3: グラフを追加する

次に、スライドに集合縦棒グラフを追加してみましょう。グラフのレイアウトも検証します。

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

このコードは、位置 (100, 100)、次元 (500, 350) の集合縦棒グラフを作成します。

## ステップ4: プロットエリアの寸法を取得する

グラフのプロット領域の幅と高さを取得するには、次のコードを使用します。

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

さて、変数`x`, `y`, `w` 、 そして`h`プロット領域の X 座標、Y 座標、幅、高さのそれぞれの値が含まれます。

## ステップ5: プレゼンテーションを保存する

最後に、グラフを含むプレゼンテーションを保存します。

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

必ず交換してください`"Chart_out.pptx"`希望する出力ファイル名を入力します。

## Java スライドのチャート プロット領域から幅と高さを取得するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
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
	//グラフ付きのプレゼンテーションを保存する
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

この記事では、Aspose.Slides for Java API を使用して、Java スライドのグラフのプロット領域の幅と高さを取得する方法について説明しました。この情報は、PowerPoint プレゼンテーション内でグラフのレイアウトを動的に調整する必要がある場合に役立ちます。

## よくある質問

### グラフの種類を集合縦棒以外のものに変更するにはどうすればいいですか?

チャートの種類を変更するには、`ChartType.ClusteredColumn`希望するチャートタイプの列挙体、例えば`ChartType.Line`または`ChartType.Pie`.

### グラフの他のプロパティを変更できますか?

はい、Aspose.Slides for Java API を使用して、データ、ラベル、書式設定など、グラフのさまざまなプロパティを変更できます。詳細については、ドキュメントを参照してください。

### Aspose.Slides for Java はプロフェッショナルな PowerPoint 自動化に適していますか?

はい、Aspose.Slides for Java は、Java アプリケーションで PowerPoint タスクを自動化するための強力なライブラリです。プレゼンテーション、スライド、図形、グラフなどを操作する包括的な機能を提供します。

### Aspose.Slides for Java について詳しく知るにはどうすればよいですか?

 Aspose.Slides for Javaのドキュメントページでは、詳細なドキュメントと例をご覧いただけます。[ここ](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
