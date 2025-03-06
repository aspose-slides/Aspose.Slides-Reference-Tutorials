---
title: Java スライドでグラフ データを更新して外部ワークブックを設定する
linktitle: Java スライドでグラフ データを更新して外部ワークブックを設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、外部ワークブックを設定し、Java スライドでグラフ データを更新する方法を学習します。PowerPoint の自動化スキルを強化します。
weight: 20
url: /ja/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java スライドでグラフ データを更新して外部ワークブックを設定する方法の概要

この包括的なガイドでは、Aspose.Slides for Java API を使用して、Java スライドで更新されたグラフ データを含む外部ワークブックを設定する手順を説明します。この強力なライブラリを使用すると、PowerPoint プレゼンテーションをプログラムで操作できるため、外部ソースからのグラフ データの更新などのタスクを簡単に自動化できます。このチュートリアルの最後には、ステップバイステップの手順と付属の Java コードを使用して、このタスクを実行する方法を明確に理解できるようになります。

## 前提条件

実装に進む前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Slides for Java: Aspose.Slides for Javaライブラリがインストールされている必要があります。ここからダウンロードできます。[ここ](https://releases.aspose.com/slides/java/).

2. Java 開発環境: システムに Java 開発環境が設定されていることを確認します。

## ステップ1: 新しいプレゼンテーションを作成する

まず、Aspose.Slides for Java を使用して新しい PowerPoint プレゼンテーションを作成しましょう。これを行うための Java コードは次のとおりです。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ2: グラフを追加する

それでは、プレゼンテーションにグラフを追加してみましょう。この例では円グラフを作成します。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## ステップ3: 外部ワークブックを設定する

ここで、外部ワークブックをグラフのデータ ソースとして設定します。現時点では存在しない場合でも、外部ワークブックの URL を指定する必要があります。

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://パス/存在しない", false);
```

## ステップ4: プレゼンテーションを保存する

最後に、更新されたグラフ データを含むプレゼンテーションを保存します。

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Java スライドでグラフ データを更新して外部ワークブックを設定するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://パス/存在しない", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

おめでとうございます! Aspose.Slides for Java を使用して、Java スライドで更新されたグラフ データを含む外部ブックを設定する方法を学習しました。これは、外部データ ソースから PowerPoint プレゼンテーションのグラフを動的に更新するのに非常に便利です。

## よくある質問

### グラフの外部ワークブックデータを更新するにはどうすればよいですか?

グラフの外部ブック データを更新するには、指定された URL の外部ブックのデータを変更するだけです。次にプレゼンテーションを開くと、Aspose.Slides for Java は外部ブックから更新されたデータを取得し、それに応じてグラフを更新します。

### ローカル ファイルを外部ワークブックとして使用できますか?

はい、URL の代わりにファイル パスを指定することにより、ローカル ファイルを外部ワークブックとして使用できます。ファイル パスが正しく、Java アプリケーションからアクセスできることを確認してください。

### Aspose.Slides for Java で外部ワークブックを使用する場合、制限はありますか?

外部ブックの使用は強力な機能ですが、外部ブックのデータが利用できるかどうかは、指定された URL またはファイル パスでのアクセス可能性によって決まることに注意してください。データ取得の問題を回避するには、プレゼンテーションを開くときに外部データ ソースが利用可能であることを確認してください。

### 外部ブックを設定した後、グラフの外観をカスタマイズできますか?

はい、外部ブックを設定した後でも、タイトル、ラベル、色など、グラフの外観をカスタマイズできます。Aspose.Slides for Java には、ニーズを満たすための広範なグラフ書式設定オプションが用意されています。

### Aspose.Slides for Java の詳細なドキュメントやリソースはどこで入手できますか?

詳細なドキュメントと追加リソースについては、Aspose.Slides for Javaのドキュメントをご覧ください。[ここ](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
