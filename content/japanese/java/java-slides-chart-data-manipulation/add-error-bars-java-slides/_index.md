---
title: Java スライドにエラーバーを追加する
linktitle: Java スライドにエラーバーを追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して Java で PowerPoint グラフに誤差範囲を追加する方法を学びます。誤差範囲をカスタマイズするためのソース コードを含むステップバイステップ ガイド。
type: docs
weight: 13
url: /ja/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Aspose.Slides を使用した Java スライドへのエラーバーの追加の概要

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint スライドのグラフに誤差範囲を追加する方法を説明します。エラーバーは、グラフ内のデータ ポイントの変動性や不確実性に関する貴重な情報を提供します。バブル チャートを作成し、それに誤差範囲を追加します。始めましょう！

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがインストールされ、Java プロジェクトに設定されていることを確認してください。ライブラリはからダウンロードできます。[Aspose ウェブサイト](https://downloads.aspose.com/slides/java).

## ステップ 1: 空のプレゼンテーションを作成する

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//空のプレゼンテーションの作成
Presentation presentation = new Presentation();
```

このステップでは、誤差範囲を含むグラフを追加する空のプレゼンテーションを作成します。

## ステップ 2: バブル チャートを作成する

```java
//バブル チャートの作成
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

ここでは、バブル チャートを作成し、スライド上の位置と寸法を指定します。

## ステップ 3: 誤差範囲の追加と形式の設定

```java
//誤差範囲の追加とその形式の設定
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

このステップでは、グラフに誤差範囲を追加し、その形式を設定します。値、タイプ、その他のプロパティを変更することで誤差範囲をカスタマイズできます。

- `errBarX`は、X 軸に沿った誤差バーを表します。
- `errBarY`は、Y 軸に沿った誤差バーを表します。
- X と Y の両方のエラーバーを表示します。
- `setValueType`誤差範囲の値のタイプを指定します (固定またはパーセンテージなど)。
- `setValue`エラーバーの値を設定します。
- `setType`誤差範囲のタイプ (プラスまたはマイナスなど) を定義します。
- 次を使用してエラーバーの線の幅を設定します。`getFormat().getLine().setWidth(2)`.
- `setEndCap`エラーバーにエンドキャップを含めるかどうかを指定します。

## ステップ 4: プレゼンテーションを保存する

```java
//プレゼンテーションの保存
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

最後に、エラーバーを追加したプレゼンテーションを指定した場所に保存します。

それでおしまい！ Aspose.Slides for Java を使用して、PowerPoint スライドのグラフに誤差範囲を正常に追加しました。

## Java スライドにエラーバーを追加するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//空のプレゼンテーションの作成
Presentation presentation = new Presentation();
try
{
	//バブル チャートの作成
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	//誤差範囲の追加とその形式の設定
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	//プレゼンテーションの保存
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用してグラフに誤差範囲を追加し、PowerPoint プレゼンテーションを強化する方法を検討しました。エラーバーはデータの変動性と不確実性に関する貴重な洞察を提供し、プレゼンテーションをより有益で視覚的に魅力的なものにします。

## よくある質問

### エラーバーの外観をさらにカスタマイズするにはどうすればよいですか?

手順 3 で示したように、線のスタイル、色、幅などのプロパティを変更することで誤差範囲をカスタマイズできます。

### さまざまな種類のグラフに誤差範囲を追加できますか?

はい、Aspose.Slides for Java でサポートされているさまざまなグラフ タイプに誤差範囲を追加できます。目的のグラフ タイプを作成し、同じエラーバーのカスタマイズ手順に従うだけです。

### スライド上のグラフの位置とサイズを調整するにはどうすればよいですか?

のパラメータを調整することで、チャートの位置と寸法を制御できます。`addChart`ステップ 2 に示す方法。

### Aspose.Slides for Java に関する詳細情報はどこで入手できますか?

を参照できます。[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/)図書館の利用方法について詳しくは、こちらをご覧ください。