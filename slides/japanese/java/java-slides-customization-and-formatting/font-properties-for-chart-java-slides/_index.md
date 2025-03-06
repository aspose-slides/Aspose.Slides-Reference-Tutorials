---
title: Java スライドのグラフのフォント プロパティ
linktitle: Java スライドのグラフのフォント プロパティ
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java スライドのグラフ フォント プロパティを強化します。フォント サイズ、スタイル、色をカスタマイズして、インパクトのあるプレゼンテーションを実現します。
weight: 11
url: /ja/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java スライドのグラフのフォント プロパティの概要

このガイドでは、Aspose.Slides を使用して Java スライドのグラフのフォント プロパティを設定する方法について説明します。グラフ テキストのフォント サイズと外観をカスタマイズして、プレゼンテーションの視覚的な魅力を高めることができます。

## 前提条件

始める前に、Aspose.Slides for Java APIがプロジェクトに統合されていることを確認してください。まだ統合されていない場合は、以下からダウンロードできます。[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/).

## ステップ1: プレゼンテーションを作成する

まず、次のコードを使用して新しいプレゼンテーションを作成します。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ2: グラフを追加する

次に、プレゼンテーションに集合縦棒グラフを追加してみましょう。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

ここでは、幅 500 単位、高さ 400 単位の集合縦棒グラフを、座標 (100, 100) の最初のスライドに追加しています。

## ステップ3: フォントプロパティをカスタマイズする

次に、グラフのフォント プロパティをカスタマイズします。この例では、すべてのグラフ テキストのフォント サイズを 20 に設定しています。

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

このコードは、グラフ内のすべてのテキストのフォント サイズを 20 ポイントに設定します。

## ステップ4: データラベルを表示する

次のコードを使用して、グラフにデータ ラベルを表示することもできます。

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

このコード行は、グラフの最初の系列のデータ ラベルを有効にし、グラフの列に値を表示します。

## ステップ5: プレゼンテーションを保存する

最後に、カスタマイズしたグラフのフォント プロパティを使用してプレゼンテーションを保存します。

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

このコードは、プレゼンテーションを「FontPropertiesForChart.pptx」というファイル名で指定されたディレクトリに保存します。

## Java スライドのチャートのフォント プロパティの完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Javaを使用してJavaスライドのグラフのフォントプロパティをカスタマイズする方法を学びました。これらのテクニックを適用して、グラフやプレゼンテーションの外観を向上させることができます。[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/).

## よくある質問

### フォントの色を変更するにはどうすればよいですか?

グラフテキストのフォント色を変更するには、`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` 、置き換え`Color.RED`希望の色で。

### フォントスタイル（太字、斜体など）を変更できますか？

はい、フォントスタイルは変更できます。`chart.getTextFormat().getPortionFormat().setFontBold(true);`フォントを太字にするには、`setFontItalic(true)`斜体にします。

### 特定のグラフ要素のフォント プロパティをカスタマイズするにはどうすればよいですか?

軸ラベルや凡例テキストなどの特定のグラフ要素のフォント プロパティをカスタマイズするには、それらの要素にアクセスし、上記と同様の方法を使用してフォント プロパティを設定します。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
