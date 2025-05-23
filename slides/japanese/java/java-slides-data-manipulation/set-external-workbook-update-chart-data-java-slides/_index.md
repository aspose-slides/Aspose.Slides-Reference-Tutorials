---
"description": "Aspose.Slides for Javaを使用して、外部ワークブックを設定し、Javaスライドでグラフデータを更新する方法を学びます。PowerPointの自動化スキルを向上させましょう。"
"linktitle": "Javaスライドでグラフデータの更新を使用して外部ワークブックを設定する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドでグラフデータの更新を使用して外部ワークブックを設定する"
"url": "/ja/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドでグラフデータの更新を使用して外部ワークブックを設定する


## Javaスライドでグラフデータを更新する外部ワークブックを設定する方法の紹介

この包括的なガイドでは、Aspose.Slides for Java APIを使用して、Java Slidesで更新されたグラフデータを含む外部ワークブックを設定する手順を詳しく説明します。この強力なライブラリを使用すると、PowerPointプレゼンテーションをプログラムで操作できるため、外部ソースからのグラフデータの更新などのタスクを簡単に自動化できます。このチュートリアルを最後までお読みいただければ、ステップバイステップの手順と付属のJavaコードを通して、このタスクを実現する方法を明確に理解できるようになります。

## 前提条件

実装に進む前に、次の前提条件が満たされていることを確認してください。

1. Aspose.Slides for Java: Aspose.Slides for Javaライブラリがインストールされている必要があります。ダウンロードはこちらから。 [ここ](https://releases。aspose.com/slides/java/).

2. Java 開発環境: システムに Java 開発環境が設定されていることを確認します。

## ステップ1: 新しいプレゼンテーションを作成する

まず、Aspose.Slides for Javaを使って新しいPowerPointプレゼンテーションを作成しましょう。作成するためのJavaコードは次のとおりです。

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ2: グラフを追加する

それでは、プレゼンテーションにグラフを追加してみましょう。この例では円グラフを作成します。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## ステップ3: 外部ワークブックを設定する

ここで、グラフのデータソースとして外部ワークブックを設定します。外部ワークブックのURLを指定する必要があります（現時点では存在しない場合でも）。

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://パスが存在しない", false);
```

## ステップ4: プレゼンテーションを保存する

最後に、更新されたグラフ データを含むプレゼンテーションを保存します。

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Javaスライドでグラフデータを更新する外部ワークブックを設定するための完全なソースコード

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://パスが存在しない", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

おめでとうございます！Aspose.Slides for Javaを使用して、Java Slidesで更新されたグラフデータを含む外部ワークブックを設定する方法を学習しました。これは、外部データソースからPowerPointプレゼンテーションのグラフを動的に更新するのに非常に便利です。

## よくある質問

### グラフの外部ブックデータを更新するにはどうすればよいですか?

グラフの外部ワークブックデータを更新するには、指定したURLにある外部ワークブックのデータを変更するだけです。次回プレゼンテーションを開くと、Aspose.Slides for Javaは外部ワークブックから更新されたデータを取得し、それに応じてグラフを更新します。

### ローカル ファイルを外部ワークブックとして使用できますか?

はい、URLではなくファイルパスを指定することで、ローカルファイルを外部ワークブックとして使用できます。ただし、ファイルパスが正しく、Javaアプリケーションからアクセスできることを確認してください。

### Aspose.Slides for Java で外部ワークブックを使用する場合、制限はありますか?

外部ワークブックの使用は強力な機能ですが、外部ワークブックのデータが利用できるかどうかは、指定されたURLまたはファイルパスでアクセスできるかどうかに依存することに注意してください。データ取得の問題を回避するために、プレゼンテーションを開くときに外部データソースが利用可能であることを確認してください。

### 外部ブックを設定した後、グラフの外観をカスタマイズできますか?

はい、外部ワークブックを設定した後でも、タイトル、ラベル、色など、グラフの外観をカスタマイズできます。Aspose.Slides for Java は、ニーズに合わせて幅広いグラフ書式設定オプションを提供します。

### Aspose.Slides for Java に関する詳細なドキュメントやリソースはどこで入手できますか?

詳細なドキュメントと追加のリソースについては、Aspose.Slides for Javaのドキュメントを参照してください。 [ここ](https://reference。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}