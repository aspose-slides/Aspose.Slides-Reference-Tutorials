---
title: Java スライドでワークブックからグラフ データを設定する
linktitle: Java スライドでワークブックからグラフ データを設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して、Java スライドで Excel ブックからグラフ データを設定する方法を学びます。動的なプレゼンテーションのコード例を含むステップ バイ ステップ ガイド。
weight: 15
url: /ja/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java スライドでワークブックからグラフ データを設定する方法の紹介

Aspose.Slides for Java は、開発者が PowerPoint プレゼンテーションをプログラムで操作できるようにする強力なライブラリです。PowerPoint スライドの作成、操作、管理のための広範な機能を提供します。プレゼンテーションを操作する際の一般的な要件の 1 つは、Excel ブックなどの外部データ ソースからグラフ データを動的に設定することです。このチュートリアルでは、Java を使用してこれを実現する方法を説明します。

## 前提条件

実装に進む前に、次の前提条件が満たされていることを確認してください。

- Java 開発キット (JDK) がシステムにインストールされています。
- Aspose.Slides for Java ライブラリがプロジェクトに追加されました。
- グラフに使用するデータを含む Excel ブック。

## ステップ1: プレゼンテーションを作成する

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

まず、Aspose.Slides for Java を使用して新しい PowerPoint プレゼンテーションを作成します。

## ステップ2: グラフを追加する

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

次に、プレゼンテーションのスライドの 1 つにグラフを追加します。この例では円グラフを追加していますが、ニーズに合ったグラフの種類を選択できます。

## ステップ3: チャートデータをクリアする

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Excel ブックからの新しいデータに対応するために、グラフから既存のデータをすべてクリアします。

## ステップ4: Excelワークブックを読み込む

```java
Workbook workbook = new Workbook("Your Document Directory";
```

グラフに使用するデータを含むExcelブックを読み込みます。`"book1.xlsx"` Excel ファイルへのパスを入力します。

## ステップ 5: ワークブック ストリームをチャート データに書き込む

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Excel ワークブックのデータをストリームに変換し、チャート データに書き込みます。

## ステップ6: グラフデータの範囲を設定する

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

グラフのデータとして使用する Excel ブックのセル範囲を指定します。データに応じて範囲を調整します。

## ステップ7: チャートシリーズをカスタマイズする

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

要件に合わせて、チャート シリーズのさまざまなプロパティをカスタマイズできます。この例では、チャート シリーズにさまざまな色を有効にします。

## ステップ8: プレゼンテーションを保存する

```java
pres.save(outPath, SaveFormat.Pptx);
```

最後に、更新されたグラフ データを含むプレゼンテーションを指定された出力パスに保存します。

## Java スライドでワークブックからグラフ データを設定する完全なソース コード

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
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

このチュートリアルでは、Aspose.Slides for Java ライブラリを使用して、Excel ブックから Java スライドにグラフ データを設定する方法を学習しました。ステップ バイ ステップ ガイドに従い、提供されているソース コード例を使用すると、動的なグラフ データを PowerPoint プレゼンテーションに簡単に統合できます。

## よくある質問

### プレゼンテーション内のグラフの外観をカスタマイズするにはどうすればよいですか?

色、フォント、ラベルなどのプロパティを変更して、グラフの外観をカスタマイズできます。グラフのカスタマイズ オプションの詳細については、Aspose.Slides for Java のドキュメントを参照してください。

### 別の Excel ファイルのデータを使用してグラフを作成できますか?

はい、コードでワークブックを読み込むときに正しいファイル パスを指定することで、任意の Excel ファイルのデータを使用できます。

### Aspose.Slides for Java では他にどのような種類のグラフを作成できますか?

Aspose.Slides for Java は、棒グラフ、折れ線グラフ、散布図など、さまざまなグラフの種類をサポートしています。データ表現のニーズに最適なグラフの種類を選択できます。

### 実行中のプレゼンテーションでグラフデータを動的に更新することは可能ですか?

はい、基になるブックを変更してグラフデータを更新することで、プレゼンテーション内のグラフデータを動的に更新できます。

### Aspose.Slides for Java の操作に関するその他の例やリソースはどこで見つかりますか?

追加の例やリソースについては、[Aspose ウェブサイト](https://www.aspose.com/)さらに、Aspose.Slides for Java のドキュメントには、ライブラリの操作に関する包括的なガイダンスが記載されています。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
