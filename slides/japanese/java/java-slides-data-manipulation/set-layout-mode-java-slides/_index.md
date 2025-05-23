---
"description": "Aspose.Slides を使用して Java スライドのレイアウトモードを設定する方法を学びます。このステップバイステップガイドでは、ソースコードを使ってグラフの位置とサイズをカスタマイズできます。"
"linktitle": "Javaスライドでレイアウトモードを設定する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドでレイアウトモードを設定する"
"url": "/ja/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドでレイアウトモードを設定する


## Javaスライドのレイアウトモードの設定の概要

このチュートリアルでは、Aspose.Slides for Java を使用して、Java スライド内のグラフのレイアウトモードを設定する方法を学びます。レイアウトモードは、スライド内のグラフの位置とサイズを決定します。

## 前提条件

始める前に、Aspose.Slides for JavaライブラリがJavaプロジェクトにインストールされ、設定されていることを確認してください。ライブラリは以下からダウンロードできます。 [ここ](https://releases。aspose.com/slides/java/).

## ステップ1：プレゼンテーションを作成する

まず、新しいプレゼンテーションを作成する必要があります。

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## ステップ2: スライドとグラフを追加する

次に、スライドとグラフを追加します。この例では、集合縦棒グラフを作成します。

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## ステップ3: グラフレイアウトを設定する

それでは、グラフのレイアウトを設定しましょう。スライド内のグラフの位置とサイズは、 `setX`、 `setY`、 `setWidth`、 `setHeight` 方法を設定します。さらに、 `LayoutTargetType` レイアウトモードを決定します。

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

この例では、チャートのレイアウト ターゲット タイプを「Inner」に設定しています。つまり、チャートはスライドの内部領域を基準にして配置およびサイズ設定されます。

## ステップ4: プレゼンテーションを保存する

最後に、グラフのレイアウト設定を含めたプレゼンテーションを保存しましょう。

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Javaスライドのレイアウトモードを設定するための完全なソースコード

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

このチュートリアルでは、Aspose.Slides for Javaを使用してJavaスライドのグラフのレイアウトモードを設定する方法を学びました。グラフの位置とサイズは、以下の値を調整することで、特定の要件に合わせてカスタマイズできます。 `setX`、 `setY`、 `setWidth`、 `setHeight`、 そして `setLayoutTargetType` 方法。これにより、スライド内のグラフの配置を制御できます。

## よくある質問

### Aspose.Slides for Java でグラフのレイアウト モードを変更するにはどうすればよいですか?

Aspose.Slides for Javaでグラフのレイアウトモードを変更するには、 `setLayoutTargetType` グラフのプロットエリアでメソッドを設定します。 `LayoutTargetType.Inner` または `LayoutTargetType.Outer` 希望するレイアウトに応じて異なります。

### スライド内のグラフの位置とサイズをカスタマイズできますか?

はい、スライド内のグラフの位置とサイズをカスタマイズできます。 `setX`、 `setY`、 `setWidth`、 そして `setHeight` グラフのプロットエリアに表示されるメソッド。これらの値を調整して、必要に応じてグラフの位置とサイズを調整します。

### Aspose.Slides for Java の詳細情報はどこで入手できますか?

Aspose.Slides for Javaの詳細については、 [ドキュメント](https://reference.aspose.com/slides/java/)Java でスライドやグラフを効果的に操作するのに役立つ詳細な API リファレンスと例が含まれています。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}