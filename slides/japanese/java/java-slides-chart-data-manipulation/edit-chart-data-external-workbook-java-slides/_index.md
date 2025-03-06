---
title: Java スライドの外部ワークブックのグラフデータを編集する
linktitle: Java スライドの外部ワークブックのグラフデータを編集する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して外部ブック内のグラフデータを編集する方法を学びます。ソース コード付きのステップ バイ ステップ ガイド。
weight: 17
url: /ja/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java スライドで外部ワークブックのグラフデータを編集する方法の紹介

このガイドでは、Aspose.Slides for Java を使用して外部ブックのグラフ データを編集する方法を説明します。PowerPoint プレゼンテーション内のグラフ データをプログラムで変更する方法を学習します。プロジェクトに Aspose.Slides ライブラリがインストールされ、構成されていることを確認してください。

## 前提条件

- Java 用 Aspose.Slides
- Java開発環境

## ステップ1: プレゼンテーションを読み込む

まず、編集したいデータを含むチャートを含むPowerPointプレゼンテーションを読み込む必要があります。`"Your Document Directory"`プレゼンテーション ファイルへの実際のパスを入力します。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## ステップ2: チャートにアクセスする

プレゼンテーションが読み込まれたら、プレゼンテーション内のグラフにアクセスする必要があります。この例では、グラフが最初のスライドにあり、そのスライドの最初の図形であると想定しています。

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## ステップ3: チャートデータを変更する

次に、グラフ データを変更してみましょう。グラフ内の特定のデータ ポイントを変更することに焦点を当てます。この例では、最初のシリーズの最初のデータ ポイントの値を 100 に設定します。この値は必要に応じて調整できます。

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## ステップ4: プレゼンテーションを保存する

グラフ データに必要な変更を加えた後、変更したプレゼンテーションを新しいファイルに保存します。 必要に応じて、出力ファイルのパスと形式を指定できます。

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## ステップ5: クリーンアップ

リソースを解放するには、プレゼンテーション オブジェクトを破棄することを忘れないでください。

```java
if (pres != null) pres.dispose();
```

これで、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーション内の外部ワークブックのグラフ データを編集できました。このコードを特定のニーズに合わせてカスタマイズし、Java アプリケーションに統合することができます。

## 完全なソースコード

```java
        //外部ワークブックへのパスがプレゼンテーションにほとんど保存されないことに注意してください
        //したがって、例を実行する前に、Data/Chart ディレクトリ D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ から externalWorkbook.xlsx ファイルをコピーしてください。
        //ドキュメント ディレクトリへのパス。
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## 結論

この包括的なガイドでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーション内の外部ワークブックのグラフ データを編集する方法について説明しました。ステップバイステップの手順とソース コードの例に従うことで、グラフ データをプログラムで簡単に変更するための知識とスキルを習得できます。

## よくある質問

### 別のグラフやスライドを指定するにはどうすればよいですか?

別のグラフやスライドにアクセスするには、`getSlides().get_Item()`そして`getShapes().get_Item()`メソッド。インデックスは 0 から始まることに注意してください。

### 同じプレゼンテーション内の複数のグラフのデータを編集できますか?

はい、各グラフのグラフ データ変更手順を繰り返すことで、同じプレゼンテーション内の複数のグラフのデータを編集できます。

### 異なる形式の外部ブック内のデータを編集したい場合はどうすればよいでしょうか?

適切な Aspose.Cells クラスとメソッドを使用してその形式でデータを読み書きすることで、さまざまな外部ブック形式を処理するようにコードを適応させることができます。

### 複数のプレゼンテーションに対してこのプロセスを自動化するにはどうすればよいですか?

ループを作成して複数のプレゼンテーションを処理し、各プレゼンテーションを読み込み、必要な変更を加えて、変更したプレゼンテーションを 1 つずつ保存することができます。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
