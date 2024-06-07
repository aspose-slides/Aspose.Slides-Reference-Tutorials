---
title: Java スライドで外部ワークブックを設定する
linktitle: Java スライドで外部ワークブックを設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java スライドに外部ワークブックを設定する方法を学習します。Excel データ統合により動的なプレゼンテーションを作成します。
type: docs
weight: 19
url: /ja/java/data-manipulation/set-external-workbook-java-slides/
---

## Java スライドで外部ワークブックを設定する方法の紹介

このチュートリアルでは、Aspose.Slides を使用して Java Slides に外部ブックを設定する方法について説明します。外部 Excel ブックのデータを参照するグラフを含む PowerPoint プレゼンテーションを作成する方法を学習します。このガイドを読み終えると、外部データを Java Slides プレゼンテーションに統合する方法を明確に理解できるようになります。

## 前提条件

実装に進む前に、次の前提条件が満たされていることを確認してください。

- Java 開発キット (JDK) がシステムにインストールされています。
- Aspose.Slides for Java ライブラリがプロジェクトに追加されました。
- プレゼンテーションで参照するデータを含む Excel ブック。

## ステップ1: 新しいプレゼンテーションを作成する

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

まず、Aspose.Slides を使用して新しい PowerPoint プレゼンテーションを作成します。

## ステップ2: グラフを追加する

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

次に、プレゼンテーションに円グラフを挿入します。必要に応じてグラフの種類と位置をカスタマイズできます。

## ステップ3: 外部ワークブックにアクセスする

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

外部ワークブックにアクセスするには、`setExternalWorkbook`メソッドを使用して、データを含む Excel ブックへのパスを指定します。

## ステップ4: チャートデータをバインドする

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

系列とカテゴリのセル参照を指定して、グラフを外部ブックのデータにバインドします。

## ステップ5: プレゼンテーションを保存する

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

最後に、外部ブック参照を含むプレゼンテーションを PowerPoint ファイルとして保存します。

## Java スライドで外部ワークブックを設定するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
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

このチュートリアルでは、Aspose.Slides を使用して Java Slides に外部ブックを設定する方法を学習しました。Excel ブックからデータを動的に参照するプレゼンテーションを作成できるようになり、スライドの柔軟性とインタラクティブ性が強化されます。

## よくある質問

### Aspose.Slides for Java をインストールするにはどうすればよいですか?

Aspose.Slides for Java は、ライブラリを Java プロジェクトに追加することでインストールできます。ライブラリは Aspose Web サイトからダウンロードし、ドキュメントに記載されているインストール手順に従ってください。

### 外部のワークブックで異なる種類のグラフを使用できますか?

はい、Aspose.Slides でサポートされているさまざまなグラフの種類を使用して、外部のワークブックのデータにバインドできます。選択したグラフの種類によって、プロセスが若干異なる場合があります。

### 外部ワークブックのデータ構造が変更された場合はどうなりますか?

外部ワークブックのデータの構造が変更された場合は、グラフ データの正確性を維持するために、Java コード内のセル参照を更新する必要がある場合があります。

### Aspose.Slides は最新の Java バージョンと互換性がありますか?

Aspose.Slides for Java は、最新の Java バージョンとの互換性を確保するために定期的に更新されます。最適なパフォーマンスと互換性を確保するため、必ず更新を確認し、最新バージョンのライブラリを使用してください。

### 同じ外部ブックを参照する複数のグラフを追加できますか?

はい、同じ外部ブックを参照する複数のグラフをプレゼンテーションに追加できます。作成するグラフごとに、このチュートリアルで説明されている手順を繰り返すだけです。