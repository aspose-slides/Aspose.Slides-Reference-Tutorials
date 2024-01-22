---
title: Java スライドに外部ワークブックを設定する
linktitle: Java スライドに外部ワークブックを設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java Slides で外部ワークブックを設定する方法を学びます。 Excel データ統合を使用して動的なプレゼンテーションを作成します。
type: docs
weight: 19
url: /ja/java/data-manipulation/set-external-workbook-java-slides/
---

## Java スライドでの外部ワークブックの設定の概要

このチュートリアルでは、Aspose.Slides を使用して Java Slides で外部ワークブックを設定する方法を検討します。外部 Excel ワークブックのデータを参照するグラフを含む PowerPoint プレゼンテーションを作成する方法を学習します。このガイドを読み終えるまでに、外部データを Java Slides プレゼンテーションに統合する方法を明確に理解できるようになります。

## 前提条件

実装に入る前に、次の前提条件を満たしていることを確認してください。

- Java Development Kit (JDK) がシステムにインストールされています。
- Aspose.Slides for Java ライブラリがプロジェクトに追加されました。
- プレゼンテーションで参照するデータが含まれる Excel ワークブック。

## ステップ 1: 新しいプレゼンテーションを作成する

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

まず、Aspose.Slides を使用して新しい PowerPoint プレゼンテーションを作成します。

## ステップ 2: グラフを追加する

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

次に、円グラフをプレゼンテーションに挿入します。必要に応じて、グラフの種類と位置をカスタマイズできます。

## ステップ 3: 外部ワークブックにアクセスする

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

外部ワークブックにアクセスするには、`setExternalWorkbook`メソッドを使用して、データを含む Excel ワークブックへのパスを指定します。

## ステップ 4: チャート データをバインドする

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

シリーズとカテゴリのセル参照を指定することで、グラフを外部ワークブックのデータにバインドします。

## ステップ 5: プレゼンテーションを保存する

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

最後に、外部ワークブック参照を含むプレゼンテーションを PowerPoint ファイルとして保存します。

## Java スライドの外部ワークブックを設定するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides を使用して Java Slides で外部ワークブックを設定する方法を学習しました。 Excel ワークブックのデータを動的に参照するプレゼンテーションを作成できるようになり、スライドの柔軟性と対話性が向上します。

## よくある質問

### Aspose.Slides for Java をインストールするにはどうすればよいですか?

Aspose.Slides for Java は、Java プロジェクトにライブラリを追加することでインストールできます。 Aspose Web サイトからライブラリをダウンロードし、ドキュメントに記載されているインストール手順に従ってください。

### 外部ワークブックで異なる種類のグラフを使用できますか?

はい、Aspose.Slides でサポートされているさまざまなグラフ タイプを使用して、外部ワークブックのデータにバインドできます。選択したグラフの種類によってプロセスが若干異なる場合があります。

### 外部ワークブックのデータ構造が変更された場合はどうなりますか?

外部ワークブックのデータ構造が変更された場合は、グラフ データが正確であることを確認するために Java コード内のセル参照を更新する必要がある場合があります。

### Aspose.Slides は最新の Java バージョンと互換性がありますか?

Aspose.Slides for Java は、最新の Java バージョンとの互換性を確保するために定期的に更新されます。最適なパフォーマンスと互換性を実現するために、必ずアップデートを確認し、最新バージョンのライブラリを使用してください。

### 同じ外部ワークブックを参照する複数のグラフを追加できますか?

はい、プレゼンテーションに複数のグラフを追加し、すべて同じ外部ワークブックを参照することができます。作成するチャートごとに、このチュートリアルで概説されている手順を繰り返すだけです。