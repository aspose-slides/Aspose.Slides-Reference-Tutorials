---
title: Java スライドの個々の凡例のフォント プロパティ
linktitle: Java スライドの個々の凡例のフォント プロパティ
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java スライドの個々の凡例のカスタム フォント スタイル、サイズ、色を使用して PowerPoint プレゼンテーションを強化します。
type: docs
weight: 12
url: /ja/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

## Java スライドの個々の凡例のフォント プロパティの概要

このチュートリアルでは、Aspose.Slides for Java を使用して Java Slides の個々の凡例のフォント プロパティを設定する方法を説明します。フォントのプロパティをカスタマイズすると、PowerPoint プレゼンテーションの凡例をより視覚的に魅力的で有益なものにすることができます。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがプロジェクトに統合されていることを確認してください。からダウンロードできます。[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/).

## ステップ 1: プレゼンテーションを初期化し、グラフを追加する

まず、PowerPoint プレゼンテーションを初期化し、グラフを追加することから始めましょう。この例では、集合縦棒グラフを例として使用します。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    //コードの残りの部分はここにあります
} finally {
    if (pres != null) pres.dispose();
}
```

交換する`"Your Document Directory"`PowerPoint ドキュメントが配置されている実際のディレクトリに置き換えます。

## ステップ 2: 凡例のフォント プロパティをカスタマイズする

次に、グラフ内の個々の凡例エントリのフォント プロパティをカスタマイズしましょう。この例では、2 番目の凡例エントリ (インデックス 1) をターゲットにしていますが、特定の要件に応じてインデックスを調整できます。

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

コードの各行の動作は次のとおりです。

- `get_Item(1)` 2 番目の凡例エントリ (インデックス 1) を取得します。インデックスを変更して、別の凡例エントリをターゲットにすることができます。
- `setFontBold(NullableBool.True)`フォントを太字に設定します。
- `setFontHeight(20)`フォント サイズを 20 ポイントに設定します。
- `setFontItalic(NullableBool.True)`フォントを斜体に設定します。
- `setFillType(FillType.Solid)`凡例エントリのテキストを塗りつぶすように指定します。
- `getSolidFillColor().setColor(Color.BLUE)`塗りつぶしの色を青に設定します。交換できます`Color.BLUE`ご希望の色で。

## ステップ 3: 変更したプレゼンテーションを保存する

最後に、変更したプレゼンテーションを新しいファイルに保存して、変更を保存します。

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

交換する`"output.pptx"`好みの出力ファイル名を付けます。

それでおしまい！ Aspose.Slides for Java を使用して、Java Slides プレゼンテーション内の個々の凡例エントリのフォント プロパティを正常にカスタマイズしました。

## Java スライドの個々の凡例のフォント プロパティの完全なソース コード

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して Java Slides の個々の凡例のフォント プロパティをカスタマイズする方法を学びました。フォントのスタイル、サイズ、色を調整することで、PowerPoint プレゼンテーションの視覚的な魅力と明瞭さを向上させることができます。

## よくある質問

### フォントの色を変更するにはどうすればよいですか?

フォントの色を変更するには、次を使用します`tf.getPortionFormat().getFontColor().setColor(yourColor)`塗りつぶしの色を変更する代わりに。交換する`yourColor`希望のフォントの色で。

### 他の凡例プロパティを変更するにはどうすればよいですか?

位置、サイズ、形式など、凡例の他のさまざまなプロパティを変更できます。凡例の操作の詳細については、Aspose.Slides for Java のドキュメントを参照してください。

### これらの変更を複数の凡例エントリに適用できますか?

はい、凡例エントリをループし、インデックスを調整することでこれらの変更を複数のエントリに適用できます。`get_Item(index)`そしてカスタマイズコードを繰り返します。

リソースの解放が完了したら、プレゼンテーション オブジェクトを忘れずに破棄してください。

```java
if (pres != null) pres.dispose();
```