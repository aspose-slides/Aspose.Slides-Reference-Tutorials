---
title: Java スライドでチャート画像を取得する
linktitle: Java スライドでチャート画像を取得する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java Slides でグラフ画像を取得する方法を学びます。このステップバイステップのガイドでは、ソース コードとシームレスな統合のためのヒントを提供します。
type: docs
weight: 19
url: /ja/java/data-manipulation/get-chart-image-java-slides/
---

## Java スライドでのチャート画像の取得の概要

Aspose.Slides for Java は、PowerPoint プレゼンテーションをプログラムで操作できるようにする強力なライブラリです。このライブラリを使用すると、グラフなどのプレゼンテーションからさまざまな要素を作成、操作、抽出できます。一般的な要件の 1 つは、スライドからグラフ画像を取得することです。このガイドでは、その方法を説明します。

## 前提条件

コードに入る前に、次の前提条件が満たされていることを確認してください。

- Java Development Kit (JDK) がシステムにインストールされています。
-  Aspose.Slides for Java ライブラリがダウンロードされ、プロジェクトに設定されます。からダウンロードできます[ここ](https://releases.aspose.com/slides/java/).

## ステップ 1: プロジェクトをセットアップする

まず、好みの統合開発環境 (IDE) で Java プロジェクトを作成します。 Aspose.Slides for Java ライブラリがプロジェクトの依存関係に追加されていることを確認してください。

## ステップ 2: プレゼンテーションを初期化する

まず、PowerPoint プレゼンテーションを初期化する必要があります。この例では、ドキュメント ディレクトリに「test.pptx」という名前の PowerPoint ファイルがあると仮定します。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## ステップ 3: グラフを追加して画像を取得する

次に、グラフをスライドに追加し、その画像を取得できます。この例では、集合縦棒グラフを追加します。

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

このコード スニペットでは、プレゼンテーションの最初のスライドに集合縦棒グラフを作成し、そのサムネイル イメージを取得します。画像は指定したディレクトリに「image.png」として保存されます。

## Java スライドでチャート画像を取得するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
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

Aspose.Slides for Java を使用して Java Slides からグラフ画像を取得するのは簡単なプロセスです。提供されたコードを使用すると、この機能を Java アプリケーションに簡単に統合でき、PowerPoint プレゼンテーションを効果的に操作できるようになります。

## よくある質問

### Aspose.Slides for Java をインストールするにはどうすればよいですか?

 Aspose.Slides for Java のインストールは簡単です。ライブラリはからダウンロードできます[ここ](https://releases.aspose.com/slides/java/)ドキュメントに記載されているインストール手順に従ってください。

### 画像を取得する前にチャートをカスタマイズできますか?

はい、画像を取得する前に、グラフの外観、データ、その他のプロパティをカスタマイズできます。 Aspose.Slides for Java は、グラフをカスタマイズするための広範なオプションを提供します。

### Aspose.Slides for Java は他にどのような機能を提供しますか?

Aspose.Slides for Java は、スライドの作成、テキスト操作、図形編集など、PowerPoint プレゼンテーションを操作するための幅広い機能を提供します。詳細については、ドキュメントを参照してください。

### Aspose.Slides for Java は商用利用に適していますか?

はい、Aspose.Slides for Java は商用目的で使用できます。個人の開発者と企業の両方に対応するライセンス オプションを提供します。

### チャート画像を別の形式で保存できますか?

確かに！適切なファイル拡張子を指定することで、チャート画像を JPEG や GIF などのさまざまな形式で保存できます。`ImageIO.write`方法。