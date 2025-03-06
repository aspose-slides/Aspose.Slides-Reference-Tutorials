---
title: Java スライドで凡例のカスタム オプションを設定する
linktitle: Java スライドで凡例のカスタム オプションを設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java スライドでカスタム凡例オプションを設定する方法を学習します。PowerPoint グラフの凡例の位置とサイズをカスタマイズします。
weight: 14
url: /ja/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java スライドで凡例のカスタム オプションを設定する


## Java スライドで凡例のカスタム オプションを設定する方法の紹介

このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションのグラフの凡例プロパティをカスタマイズする方法を説明します。プレゼンテーションのニーズに合わせて、凡例の位置、サイズ、その他の属性を変更できます。

## 前提条件

始める前に、次のものがあることを確認してください。

- Aspose.Slides for Java API がインストールされています。
- Java開発環境をセットアップしました。

## ステップ1: 必要なクラスをインポートします。

```java
// Aspose.Slides for Java クラスのインポート
import com.aspose.slides.*;
```

## ステップ 2: ドキュメント ディレクトリへのパスを指定します。

```java
String dataDir = "Your Document Directory";
```

## ステップ3: インスタンスを作成する`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## ステップ 4: プレゼンテーションにスライドを追加します。

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## ステップ 5: スライドに集合縦棒グラフを追加します。

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## ステップ 6. 凡例のプロパティを設定する:

- 凡例の X 位置を設定します (グラフの幅を基準として)。

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- 凡例の Y 位置を設定します (グラフの高さを基準として)。

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- 凡例の幅を設定します（グラフの幅を基準として）：

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- 凡例の高さを設定します（グラフの高さを基準として）：

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## ステップ 7: プレゼンテーションをディスクに保存します。

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

これで完了です。Aspose.Slides for Java を使用して、PowerPoint プレゼンテーション内のグラフの凡例プロパティをカスタマイズできました。

## Java スライドで凡例のカスタム オプションを設定するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
try
{
	//スライドの参照を取得する
	ISlide slide = presentation.getSlides().get_Item(0);
	//スライドに集合縦棒グラフを追加する
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	//凡例プロパティを設定する
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	//プレゼンテーションをディスクに書き込む
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションのグラフの凡例プロパティをカスタマイズする方法を学習しました。凡例の位置、サイズ、その他の属性を変更して、視覚的に魅力的で情報豊富なプレゼンテーションを作成できます。

## よくある質問

## 凡例の位置を変更するにはどうすればいいですか?

凡例の位置を変更するには、`setX`そして`setY`凡例オブジェクトのメソッド。値はグラフの幅と高さを基準に指定されます。

## 凡例のサイズを調整するにはどうすればよいですか?

凡例のサイズは、`setWidth`そして`setHeight`凡例オブジェクトのメソッド。これらの値もグラフの幅と高さに相対的です。

## 他の凡例属性をカスタマイズできますか?

はい、フォント スタイル、境界線、背景色など、凡例のさまざまな属性をカスタマイズできます。凡例のカスタマイズの詳細については、Aspose.Slides のドキュメントを参照してください。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
