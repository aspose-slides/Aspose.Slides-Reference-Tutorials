---
"description": "Aspose.Slides for Java を使用して、Java スライド内の個々の凡例のカスタム フォント スタイル、サイズ、色で PowerPoint プレゼンテーションを強化します。"
"linktitle": "Java スライドの個々の凡例のフォント プロパティ"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Java スライドの個々の凡例のフォント プロパティ"
"url": "/ja/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java スライドの個々の凡例のフォント プロパティ


## Javaスライドの凡例のフォントプロパティの概要

このチュートリアルでは、Aspose.Slides for Java を使用して、Java スライド内の個々の凡例のフォントプロパティを設定する方法を説明します。フォントプロパティをカスタマイズすることで、PowerPoint プレゼンテーション内の凡例をより魅力的で分かりやすくすることができます。

## 前提条件

始める前に、Aspose.Slides for Javaライブラリがプロジェクトに統合されていることを確認してください。ライブラリは以下からダウンロードできます。 [Aspose.Slides for Java ドキュメント](https://reference。aspose.com/slides/java/).

## ステップ1: プレゼンテーションを初期化し、グラフを追加する

まず、PowerPointプレゼンテーションを初期化し、グラフを追加してみましょう。この例では、集合縦棒グラフを例として使用します。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // 残りのコードはここに記述します
} finally {
    if (pres != null) pres.dispose();
}
```

交換する `"Your Document Directory"` PowerPoint ドキュメントが保存されている実際のディレクトリに置き換えます。

## ステップ2: 凡例のフォントプロパティをカスタマイズする

それでは、グラフ内の個々の凡例項目のフォントプロパティをカスタマイズしてみましょう。この例では、2番目の凡例項目（インデックス1）を対象としていますが、必要に応じてインデックスを調整できます。

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

コードの各行の機能は次のとおりです。

- `get_Item(1)` 2番目の凡例項目（インデックス1）を取得します。インデックスを変更することで、別の凡例項目を参照できます。
- `setFontBold(NullableBool.True)` フォントを太字に設定します。
- `setFontHeight(20)` フォントサイズを 20 ポイントに設定します。
- `setFontItalic(NullableBool.True)` フォントを斜体に設定します。
- `setFillType(FillType.Solid)` 凡例エントリのテキストを塗りつぶすように指定します。
- `getSolidFillColor().setColor(Color.BLUE)` 塗りつぶしの色を青に設定します。 `Color.BLUE` ご希望の色で。

## ステップ3: 変更したプレゼンテーションを保存する

最後に、変更を保存するために、変更したプレゼンテーションを新しいファイルに保存します。

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

交換する `"output.pptx"` 希望する出力ファイル名を入力します。

これで完了です。Aspose.Slides for Java を使用して、Java スライド プレゼンテーション内の個々の凡例エントリのフォント プロパティをカスタマイズできました。

## Javaスライドの凡例のフォントプロパティの完全なソースコード

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

このチュートリアルでは、Aspose.Slides for Java を使用して、Java スライド内の個々の凡例のフォントプロパティをカスタマイズする方法を学びました。フォントのスタイル、サイズ、色を調整することで、PowerPoint プレゼンテーションの視覚的な魅力と明瞭性を高めることができます。

## よくある質問

### フォントの色を変更するにはどうすればよいですか?

フォントの色を変更するには、 `tf.getPortionFormat().getFontColor().setColor(yourColor)` 塗りつぶしの色を変更する代わりに、 `yourColor` 希望のフォント色で。

### 他の凡例のプロパティを変更するにはどうすればよいですか?

凡例の位置、サイズ、書式など、その他の様々なプロパティを変更できます。凡例の操作方法の詳細については、Aspose.Slides for Java のドキュメントをご覧ください。

### これらの変更を複数の凡例エントリに適用できますか?

はい、凡例のエントリをループし、インデックスを調整することで複数のエントリにこれらの変更を適用できます。 `get_Item(index)` カスタマイズ コードを繰り返します。

完了したら、プレゼンテーション オブジェクトを破棄してリソースを解放することを忘れないでください。

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}