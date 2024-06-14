---
title: Java スライドでチャート画像を取得する
linktitle: Java スライドでチャート画像を取得する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java スライドでチャート画像を取得する方法を学びます。このステップバイステップ ガイドでは、シームレスな統合のためのソース コードとヒントを提供します。
type: docs
weight: 19
url: /ja/java/data-manipulation/get-chart-image-java-slides/
---

## Javaスライドでチャート画像を取得する方法の紹介

Aspose.Slides for Java は、PowerPoint プレゼンテーションをプログラムで操作できる強力なライブラリです。このライブラリを使用すると、グラフなどのプレゼンテーションのさまざまな要素を作成、操作、抽出できます。一般的な要件の 1 つは、スライドからグラフ画像を取得することです。このガイドでは、まさにその方法を説明します。

## 前提条件

コードに進む前に、次の前提条件が満たされていることを確認してください。

- Java 開発キット (JDK) がシステムにインストールされています。
-  Aspose.Slides for Javaライブラリがダウンロードされ、プロジェクトに構成されます。ダウンロードはここから行えます。[ここ](https://releases.aspose.com/slides/java/).

## ステップ1: プロジェクトを設定する

まず、お好みの統合開発環境 (IDE) で Java プロジェクトを作成します。プロジェクトの依存関係に Aspose.Slides for Java ライブラリを追加したことを確認します。

## ステップ2: プレゼンテーションを初期化する

まず、PowerPoint プレゼンテーションを初期化する必要があります。この例では、ドキュメント ディレクトリに「test.pptx」という名前の PowerPoint ファイルがあると想定しています。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## ステップ3: グラフを追加して画像を取得する

次に、スライドにグラフを追加して、その画像を取得します。 この例では、集合縦棒グラフを追加します。

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

このコード スニペットでは、プレゼンテーションの最初のスライドに集合縦棒グラフを作成し、そのサムネイル画像を取得します。画像は、指定されたディレクトリに「image.png」として保存されます。

## Java スライドでチャート画像を取得するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

Aspose.Slides for Java を使用して Java スライドからグラフ画像を取得するのは簡単なプロセスです。提供されているコードを使用すると、この機能を Java アプリケーションに簡単に統合でき、PowerPoint プレゼンテーションを効果的に操作できます。

## よくある質問

### Aspose.Slides for Java をインストールするにはどうすればよいですか?

 Aspose.Slides for Javaのインストールは簡単です。ライブラリは以下からダウンロードできます。[ここ](https://releases.aspose.com/slides/java/)ドキュメントに記載されているインストール手順に従ってください。

### 画像を取得する前にチャートをカスタマイズできますか?

はい、画像を取得する前に、グラフの外観、データ、およびその他のプロパティをカスタマイズできます。Aspose.Slides for Java には、グラフをカスタマイズするための広範なオプションが用意されています。

### Aspose.Slides for Java には他にどのような機能がありますか?

Aspose.Slides for Java は、スライドの作成、テキストの操作、図形の編集など、PowerPoint プレゼンテーションを操作するための幅広い機能を提供します。詳細については、ドキュメントを参照してください。

### Aspose.Slides for Java は商用利用に適していますか?

はい、Aspose.Slides for Java は商用目的で使用できます。個人開発者と企業の両方に対応するライセンス オプションを提供します。

### チャート画像を別の形式で保存できますか?

もちろんです！適切なファイル拡張子を指定することで、チャート画像をJPEGやGIFなどのさまざまな形式で保存できます。`ImageIO.write`方法。