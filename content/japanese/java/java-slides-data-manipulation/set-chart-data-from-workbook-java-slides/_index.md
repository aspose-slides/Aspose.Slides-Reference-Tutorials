---
title: Java スライドのワークブックからグラフ データを設定する
linktitle: Java スライドのワークブックからグラフ データを設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して Java Slides で Excel ワークブックからグラフ データを設定する方法を学びます。動的プレゼンテーションのコード例を含むステップバイステップのガイド。
type: docs
weight: 15
url: /ja/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Java スライドでワークブックからグラフ データを設定する方法の概要

Aspose.Slides for Java は、開発者がプログラムで PowerPoint プレゼンテーションを操作できるようにする強力なライブラリです。 PowerPoint スライドを作成、操作、管理するための広範な機能を提供します。プレゼンテーションを操作するときの一般的な要件の 1 つは、Excel ワークブックなどの外部データ ソースからグラフ データを動的に設定することです。このチュートリアルでは、Java を使用してこれを実現する方法を説明します。

## 前提条件

実装に入る前に、次の前提条件を満たしていることを確認してください。

- Java Development Kit (JDK) がシステムにインストールされています。
- Aspose.Slides for Java ライブラリがプロジェクトに追加されました。
- グラフに使用するデータが含まれる Excel ワークブック。

## ステップ 1: プレゼンテーションを作成する

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
```

まず、Aspose.Slides for Java を使用して新しい PowerPoint プレゼンテーションを作成します。

## ステップ 2: グラフを追加する

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

次に、プレゼンテーション内のスライドの 1 つにグラフを追加します。この例では円グラフを追加していますが、ニーズに合ったグラフの種類を選択できます。

## ステップ 3: チャート データをクリアする

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Excel ワークブックからの新しいデータを準備するために、グラフから既存のデータを消去します。

## ステップ 4: Excel ワークブックをロードする

```java
Workbook workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
```

グラフに使用するデータを含む Excel ワークブックを読み込みます。交換する`"book1.xlsx"`Excel ファイルへのパスを含めます。

## ステップ 5: ワークブック ストリームをグラフ データに書き込む

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Excel ワークブック データをストリームに変換し、グラフ データに書き込みます。

## ステップ 6: チャートのデータ範囲を設定する

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

グラフのデータとして使用する Excel ワークブックのセル範囲を指定します。データの必要に応じて範囲を調整します。

## ステップ 7: チャート シリーズをカスタマイズする

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

要件に合わせてグラフ シリーズのさまざまなプロパティをカスタマイズできます。この例では、グラフ シリーズに対してさまざまな色を有効にします。

## ステップ 8: プレゼンテーションを保存する

```java
pres.save(outPath, SaveFormat.Pptx);
```

最後に、更新されたグラフ データを含むプレゼンテーションを指定した出力パスに保存します。

## Java スライドのワークブックからグラフ データを設定するための完全なソース コード

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java ライブラリを使用して Java Slides で Excel ワークブックからグラフ データを設定する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コード例を使用すると、動的なグラフ データを PowerPoint プレゼンテーションに簡単に統合できます。

## よくある質問

### プレゼンテーション内のグラフの外観をカスタマイズするにはどうすればよいですか?

色、フォント、ラベルなどのプロパティを変更することで、グラフの外観をカスタマイズできます。グラフのカスタマイズ オプションの詳細については、Aspose.Slides for Java のドキュメントを参照してください。

### 別の Excel ファイルのデータをグラフに使用できますか?

はい、コードでワークブックを読み込むときに正しいファイル パスを指定することで、任意の Excel ファイルのデータを使用できます。

### Aspose.Slides for Java では他にどのようなタイプのグラフを作成できますか?

Aspose.Slides for Java は、棒グラフ、折れ線グラフ、散布図など、さまざまな種類のグラフをサポートしています。データ表現のニーズに最も適したグラフの種類を選択できます。

### 実行中のプレゼンテーションでグラフ データを動的に更新することはできますか?

はい、基礎となるワークブックを変更してグラフ データを更新することで、プレゼンテーション内のグラフ データを動的に更新できます。

### Aspose.Slides for Java を使用するためのその他の例やリソースはどこで見つけられますか?

追加の例やリソースについては、[Aspose ウェブサイト](https://www.aspose.com/)。さらに、Aspose.Slides for Java ドキュメントには、ライブラリの操作に関する包括的なガイダンスが提供されています。