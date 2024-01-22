---
title: Java スライドで凡例のカスタム オプションを設定する
linktitle: Java スライドで凡例のカスタム オプションを設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java Slides でカスタム凡例オプションを設定する方法を学びます。 PowerPoint グラフの凡例の位置とサイズをカスタマイズします。
type: docs
weight: 14
url: /ja/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

## Java スライドでの凡例のカスタム オプションの設定の概要

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションのグラフの凡例プロパティをカスタマイズする方法を示します。プレゼンテーションのニーズに合わせて凡例の位置、サイズ、その他の属性を変更できます。

## 前提条件

始める前に、以下のものがあることを確認してください。

- Aspose.Slides for Java API がインストールされています。
- Java開発環境のセットアップ。

## ステップ 1: 必要なクラスをインポートします。

```java
// Java クラスの Aspose.Slides をインポートする
import com.aspose.slides.*;
```

## ステップ 2: ドキュメント ディレクトリへのパスを指定します。

```java
String dataDir = "Your Document Directory";
```

## ステップ 3: のインスタンスを作成する`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## ステップ 4: プレゼンテーションにスライドを追加します。

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## ステップ 5: 集合縦棒グラフをスライドに追加します。

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## ステップ 6. 凡例のプロパティを設定します。

- 凡例の X 位置を設定します (グラフの幅を基準にして)。

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- 凡例の Y 位置を設定します (グラフの高さを基準にして)。

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- 凡例の幅を設定します (グラフの幅を基準にして)。

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- 凡例の高さを設定します (グラフの高さを基準にして)。

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

それでおしまい！ Aspose.Slides for Java を使用して、PowerPoint プレゼンテーション内のグラフの凡例プロパティを正常にカスタマイズできました。

## Java スライドの凡例カスタム オプションを設定するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
// Presentationクラスのインスタンスを作成する
Presentation presentation = new Presentation();
try
{
	//スライドのリファレンスを取得する
	ISlide slide = presentation.getSlides().get_Item(0);
	//スライドに集合縦棒グラフを追加する
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	//凡例のプロパティを設定する
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

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションのグラフの凡例プロパティをカスタマイズする方法を学びました。凡例の位置、サイズ、その他の属性を変更して、視覚的に魅力的で有益なプレゼンテーションを作成できます。

## よくある質問

## 凡例の位置を変更するにはどうすればよいですか?

凡例の位置を変更するには、`setX`そして`setY`凡例オブジェクトのメソッド。値は、グラフの幅と高さに相対して指定されます。

## 凡例のサイズを調整するにはどうすればよいですか?

凡例のサイズを調整するには、`setWidth`そして`setHeight`凡例オブジェクトのメソッド。これらの値は、グラフの幅と高さにも相対的です。

## 他の凡例属性をカスタマイズできますか?

はい、フォント スタイル、境界線、背景色など、凡例のさまざまな属性をカスタマイズできます。凡例のカスタマイズに関する詳細については、Aspose.Slides ドキュメントを参照してください。