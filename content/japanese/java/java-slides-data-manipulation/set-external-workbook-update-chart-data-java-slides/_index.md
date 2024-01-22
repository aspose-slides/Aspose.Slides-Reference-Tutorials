---
title: Java スライドでグラフ データを更新する外部ワークブックを設定する
linktitle: Java スライドでグラフ データを更新する外部ワークブックを設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java Slides で外部ワークブックを設定し、グラフ データを更新する方法を学びます。 PowerPoint の自動化スキルを強化します。
type: docs
weight: 20
url: /ja/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

## Java スライドでグラフ データを更新する外部ワークブックの設定の概要

この包括的なガイドでは、Aspose.Slides for Java API を使用して、更新されたグラフ データを含む外部ワークブックを Java Slides に設定するプロセスについて説明します。この強力なライブラリを使用すると、PowerPoint プレゼンテーションをプログラムで操作できるため、外部ソースからのグラフ データの更新などのタスクを簡単に自動化できます。このチュートリアルを終了するまでに、段階的な手順とそれに付随する Java コードを使用してこのタスクを実行する方法を明確に理解できるようになります。

## 前提条件

実装に入る前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Slides for Java: Aspose.Slides for Java ライブラリがインストールされている必要があります。からダウンロードできます[ここ](https://releases.aspose.com/slides/java/).

2. Java 開発環境: システムに Java 開発環境がセットアップされていることを確認します。

## ステップ 1: 新しいプレゼンテーションを作成する

まず、Aspose.Slides for Java を使用して新しい PowerPoint プレゼンテーションを作成しましょう。これを行うための Java コードは次のとおりです。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ 2: グラフを追加する

次に、プレゼンテーションにグラフを追加しましょう。この例では円グラフを作成します。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## ステップ 3: 外部ワークブックを設定する

ここで、外部ワークブックをグラフのデータ ソースとして設定します。現時点では外部ワークブックが存在しない場合でも、外部ワークブックへの URL を指定する必要があります。

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://パス/存在しない/存在します"、false);
```

## ステップ 4: プレゼンテーションを保存する

最後に、更新されたグラフ データを含むプレゼンテーションを保存します。

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Java スライドのグラフ データを更新する外部ワークブックの設定の完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://パス/存在しない/存在します"、false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

おめでとう！ Aspose.Slides for Java を使用して、Java Slides で更新されたグラフ データを含む外部ワークブックを設定する方法を学習しました。これは、PowerPoint プレゼンテーション内のグラフを外部データ ソースから動的に更新する場合に非常に役立ちます。

## よくある質問

### チャートの外部ワークブック データを更新するにはどうすればよいですか?

グラフの外部ワークブック データを更新するには、指定された URL にある外部ワークブック内のデータを変更するだけです。次回プレゼンテーションを開いたときに、Aspose.Slides for Java は外部ワークブックから更新されたデータを取得し、それに応じてグラフを更新します。

### ローカル ファイルを外部ワークブックとして使用できますか?

はい、URL の代わりにファイル パスを指定することで、ローカル ファイルを外部ワークブックとして使用できます。ファイル パスが正しく、Java アプリケーションからアクセスできることを確認してください。

### Aspose.Slides for Java で外部ワークブックを使用する場合に制限はありますか?

外部ワークブックの使用は強力な機能ですが、外部ワークブックのデータが利用できるかどうかは、指定された URL またはファイル パスでのアクセス可能性に依存することに注意してください。データ取得の問題を避けるために、プレゼンテーションを開いたときに外部データ ソースが利用可能であることを確認してください。

### 外部ワークブックを設定した後にグラフの外観をカスタマイズできますか?

はい、外部ワークブックを設定した後でも、タイトル、ラベル、色などを含むグラフの外観をカスタマイズできます。 Aspose.Slides for Java は、ニーズを満たす広範なグラフ書式設定オプションを提供します。

### Aspose.Slides for Java に関するその他のドキュメントやリソースはどこで見つけられますか?

詳細なドキュメントと追加リソースについては、次の場所にある Aspose.Slides for Java ドキュメントを参照してください。[ここ](https://reference.aspose.com/slides/java/).