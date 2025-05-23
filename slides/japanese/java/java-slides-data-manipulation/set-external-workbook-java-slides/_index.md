---
"description": "Aspose.Slides for Javaを使用して、Javaスライドに外部ワークブックを設定する方法を学びます。Excelデータ統合により、ダイナミックなプレゼンテーションを作成します。"
"linktitle": "Javaスライドで外部ワークブックを設定する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドで外部ワークブックを設定する"
"url": "/ja/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドで外部ワークブックを設定する


## Javaスライドで外部ワークブックを設定する方法の紹介

このチュートリアルでは、Aspose.Slides を使用して Java Slides に外部ワークブックを設定する方法を説明します。外部 Excel ワークブックのデータを参照するグラフを含む PowerPoint プレゼンテーションを作成する方法を学びます。このガイドを最後まで読み進めれば、Java Slides プレゼンテーションに外部データを統合する方法を明確に理解できるようになります。

## 前提条件

実装に進む前に、次の前提条件が満たされていることを確認してください。

- Java Development Kit (JDK) がシステムにインストールされています。
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

次に、プレゼンテーションに円グラフを挿入します。グラフの種類と位置は必要に応じてカスタマイズできます。

## ステップ3: 外部ワークブックにアクセスする

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

外部ワークブックにアクセスするには、 `setExternalWorkbook` メソッドを使用して、データを含む Excel ブックへのパスを指定します。

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

## Javaスライドで外部ワークブックを設定するための完全なソースコード

```java
// ドキュメント ディレクトリへのパス。
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

このチュートリアルでは、Aspose.Slides を使用して Java Slides に外部ワークブックを設定する方法を学習しました。Excel ワークブックのデータを動的に参照するプレゼンテーションを作成できるようになり、スライドの柔軟性とインタラクティブ性が向上します。

## よくある質問

### Aspose.Slides for Java をインストールするにはどうすればよいですか?

Aspose.Slides for Javaは、Javaプロジェクトにライブラリを追加することでインストールできます。ライブラリはAsposeのWebサイトからダウンロードし、ドキュメントに記載されているインストール手順に従ってください。

### 外部のブックで異なる種類のグラフを使用できますか?

はい、Aspose.Slides でサポートされている様々な種類のグラフを使用し、外部ワークブックのデータとバインドできます。選択したグラフの種類によって、手順が若干異なる場合があります。

### 外部ワークブックのデータ構造が変更された場合はどうなりますか?

外部ワークブックのデータの構造が変更された場合は、グラフ データの正確性を維持するために、Java コード内のセル参照を更新する必要がある場合があります。

### Aspose.Slides は最新の Java バージョンと互換性がありますか?

Aspose.Slides for Javaは、最新のJavaバージョンとの互換性を確保するために定期的に更新されています。最適なパフォーマンスと互換性を確保するため、必ず更新を確認し、最新バージョンのライブラリをご利用ください。

### 同じ外部ブックを参照する複数のグラフを追加できますか?

はい、プレゼンテーションに複数のグラフを追加し、すべて同じ外部ブックを参照することができます。作成したいグラフごとに、このチュートリアルで説明されている手順を繰り返すだけです。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}