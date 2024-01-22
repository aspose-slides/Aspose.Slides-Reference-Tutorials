---
title: Java スライドのレイアウト モードを設定する
linktitle: Java スライドのレイアウト モードを設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して Java スライドのレイアウト モードを設定する方法を学習します。ソース コードを使用したこのステップバイステップ ガイドで、グラフの位置とサイズをカスタマイズします。
type: docs
weight: 23
url: /ja/java/data-manipulation/set-layout-mode-java-slides/
---

## Java スライドでのレイアウト モードの設定の概要

このチュートリアルでは、Aspose.Slides for Java を使用して Java スライドのグラフのレイアウト モードを設定する方法を学習します。レイアウト モードにより、スライド内のグラフの位置とサイズが決まります。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがインストールされ、Java プロジェクトに設定されていることを確認してください。ライブラリはからダウンロードできます[ここ](https://releases.aspose.com/slides/java/).

## ステップ 1: プレゼンテーションを作成する

まず、新しいプレゼンテーションを作成する必要があります。

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## ステップ 2: スライドとグラフを追加する

次に、スライドとグラフを追加します。この例では、集合縦棒グラフを作成します。

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## ステップ 3: グラフのレイアウトを設定する

次に、グラフのレイアウトを設定しましょう。を使用して、スライド内のグラフの位置とサイズを調整します。`setX`, `setY`, `setWidth`, `setHeight`方法。さらに、`LayoutTargetType`レイアウトモードを決定します。

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

この例では、グラフのレイアウト ターゲット タイプを「内側」に設定しています。これは、グラフの位置とサイズがスライドの内側の領域に相対的に設定されることを意味します。

## ステップ 4: プレゼンテーションを保存する

最後に、グラフのレイアウト設定を使用してプレゼンテーションを保存しましょう。

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Java スライドのレイアウト設定モードの完全なソース コード

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して Java スライドのグラフのレイアウト モードを設定する方法を学習しました。の値を調整することで、特定の要件に応じてグラフの位置とサイズをカスタマイズできます。`setX`, `setY`, `setWidth`, `setHeight` 、 そして`setLayoutTargetType`方法。これにより、スライド内のグラフの配置を制御できるようになります。

## よくある質問

### Aspose.Slides for Java でグラフのレイアウト モードを変更するにはどうすればよいですか?

 Aspose.Slides for Java でグラフのレイアウト モードを変更するには、`setLayoutTargetType`チャートのプロット領域のメソッド。どちらかに設定できます`LayoutTargetType.Inner`または`LayoutTargetType.Outer`ご希望のレイアウトに応じて。

### スライド内のグラフの位置とサイズをカスタマイズできますか?

はい、スライド内のグラフの位置とサイズは、`setX`, `setY`, `setWidth` 、 そして`setHeight`チャートのプロット領域のメソッド。これらの値を調整して、要件に応じてチャートの位置とサイズを調整します。

### Aspose.Slides for Java に関する詳細情報はどこで入手できますか?

 Aspose.Slides for Java の詳細については、[ドキュメンテーション](https://reference.aspose.com/slides/java/)。 Java でスライドやグラフを効果的に操作するのに役立つ詳細な API リファレンスと例が含まれています。