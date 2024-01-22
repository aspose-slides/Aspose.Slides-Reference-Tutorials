---
title: Java スライドの外部ワークブックのグラフ データを編集する
linktitle: Java スライドの外部ワークブックのグラフ データを編集する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して外部ワークブック内のグラフ データを編集する方法を学びます。ソースコード付きのステップバイステップガイド。
type: docs
weight: 17
url: /ja/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

## Java スライドでの外部ワークブックのグラフ データの編集の概要

このガイドでは、Aspose.Slides for Java を使用して外部ワークブック内のグラフ データを編集する方法を説明します。 PowerPoint プレゼンテーション内のグラフ データをプログラムで変更する方法を学習します。 Java 用の Aspose.Slides ライブラリがプロジェクトにインストールされ、構成されていることを確認してください。

## 前提条件

- Java 用 Aspose.Slides
- Java開発環境

## ステップ 1: プレゼンテーションをロードする

まず、データを編集するグラフを含む PowerPoint プレゼンテーションをロードする必要があります。交換する`"Your Document Directory"`プレゼンテーション ファイルへの実際のパスを含めます。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## ステップ 2: チャートにアクセスする

プレゼンテーションがロードされたら、プレゼンテーション内のグラフにアクセスする必要があります。この例では、グラフが最初のスライドにあり、そのスライドの最初の図形であると仮定します。

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## ステップ 3: グラフ データを変更する

次に、グラフのデータを変更してみましょう。グラフ内の特定のデータ ポイントの変更に焦点を当てます。この例では、最初の系列の最初のデータ ポイントの値を 100 に設定します。必要に応じてこの値を調整できます。

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## ステップ 4: プレゼンテーションを保存する

グラフ データに必要な変更を加えた後、変更したプレゼンテーションを新しいファイルに保存します。要件に応じて出力ファイルのパスと形式を指定できます。

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## ステップ 5: クリーンアップ

プレゼンテーション オブジェクトを破棄してリソースを解放することを忘れないでください。

```java
if (pres != null) pres.dispose();
```

これで、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーション内の外部ワークブックのグラフ データを正常に編集できました。このコードを特定のニーズに合わせてカスタマイズし、Java アプリケーションに統合できます。

## 完全なソースコード

```java
        //外部ワークブックへのパスはプレゼンテーションにはほとんど保存されないことに注意してください
        //したがって、サンプルを実行する前に、Data/Chart ディレクトリ D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ からファイル externalWorkbook.xlsx をコピーしてください。
        //ドキュメントディレクトリへのパス。
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save(RunExamples.getOutPath() + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## 結論

この包括的なガイドでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーション内の外部ワークブックのグラフ データを編集する方法を説明しました。段階的な手順とソース コードの例に従うことで、グラフ データをプログラムで簡単に変更するための知識とスキルを習得できます。

## よくある質問

### 別のグラフまたはスライドを指定するにはどうすればよいですか?

別のグラフまたはスライドにアクセスするには、`getSlides().get_Item()`そして`getShapes().get_Item()`方法。インデックス付けは 0 から始まることに注意してください。

### 同じプレゼンテーション内の複数のグラフのデータを編集できますか?

はい、各グラフに対してグラフ データの変更手順を繰り返すことで、同じプレゼンテーション内の複数のグラフのデータを編集できます。

### 外部ワークブック内のデータを別の形式で編集したい場合はどうすればよいですか?

適切な Aspose.Cells クラスとメソッドを使用して、その形式でデータを読み書きすることで、さまざまな外部ワークブック形式を処理できるようにコードを調整できます。

### 複数のプレゼンテーションでこのプロセスを自動化するにはどうすればよいですか?

複数のプレゼンテーションを処理するループを作成し、各プレゼンテーションをロードし、必要な変更を加え、変更されたプレゼンテーションを 1 つずつ保存することができます。