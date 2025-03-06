---
title: Java スライドにエラー バーを追加する
linktitle: Java スライドにエラー バーを追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して Java で PowerPoint グラフにエラー バーを追加する方法を学びます。エラー バーをカスタマイズするためのソース コードを含むステップ バイ ステップ ガイド。
weight: 13
url: /ja/java/chart-data-manipulation/add-error-bars-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides を使用して Java スライドにエラー バーを追加する方法の紹介

このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint スライドのグラフにエラー バーを追加する方法を説明します。エラー バーは、グラフ内のデータ ポイントの変動性や不確実性に関する貴重な情報を提供します。バブル チャートを作成し、それにエラー バーを追加します。さあ、始めましょう!

## 前提条件

始める前に、JavaプロジェクトにAspose.Slides for Javaライブラリがインストールされ、設定されていることを確認してください。ライブラリは以下からダウンロードできます。[Aspose ウェブサイト](https://downloads.aspose.com/slides/java).

## ステップ1: 空のプレゼンテーションを作成する

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//空のプレゼンテーションを作成しています
Presentation presentation = new Presentation();
```

この手順では、エラー バーを含むグラフを追加する空のプレゼンテーションを作成します。

## ステップ2: バブルチャートを作成する

```java
//バブルチャートを作成する
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

ここでは、バブル チャートを作成し、スライド上の位置と寸法を指定します。

## ステップ3: エラーバーの追加と書式設定

```java
//エラーバーを追加してその形式を設定する
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

この手順では、グラフにエラー バーを追加し、その形式を設定します。値、タイプ、その他のプロパティを変更することで、エラー バーをカスタマイズできます。

- `errBarX` X 軸に沿ったエラー バーを表します。
- `errBarY` Y 軸に沿ったエラー バーを表します。
- X と Y の両方のエラー バーを表示します。
- `setValueType`エラーバーの値のタイプを指定します (例: 固定またはパーセンテージ)。
- `setValue`エラーバーの値を設定します。
- `setType`エラーバーの種類を定義します (例: プラスまたはマイナス)。
- エラーバーの幅は次のように設定します。`getFormat().getLine().setWidth(2)`.
- `setEndCap`エラーバーにエンドキャップを含めるかどうかを指定します。

## ステップ4: プレゼンテーションを保存する

```java
//プレゼンテーションを保存しています
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

最後に、エラー バーを追加したプレゼンテーションを指定した場所に保存します。

これで完了です。Aspose.Slides for Java を使用して、PowerPoint スライドのグラフにエラー バーを正常に追加できました。

## Java スライドにエラー バーを追加するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//空のプレゼンテーションを作成しています
Presentation presentation = new Presentation();
try
{
	//バブルチャートを作成する
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	//エラーバーを追加してその形式を設定する
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
	//プレゼンテーションを保存しています
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用してチャートにエラー バーを追加し、PowerPoint プレゼンテーションを強化する方法について説明しました。エラー バーは、データの変動性と不確実性に関する貴重な情報を提供し、プレゼンテーションをより情報豊富で視覚的に魅力的なものにします。

## よくある質問

### エラーバーの外観をさらにカスタマイズするにはどうすればよいですか?

手順 3 に示すように、線のスタイル、色、幅などのプロパティを変更して、エラー バーをカスタマイズできます。

### 異なる種類のグラフにエラー バーを追加できますか?

はい、Aspose.Slides for Java でサポートされているさまざまなグラフの種類にエラー バーを追加できます。必要なグラフの種類を作成し、同じエラー バーのカスタマイズ手順に従うだけです。

### スライド上のグラフの位置とサイズを調整するにはどうすればよいですか?

チャートの位置とサイズは、`addChart`手順 2 に示すように、この方法を使用します。

### Aspose.Slides for Java の詳細情報はどこで入手できますか?

参照するには[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/)ライブラリの使用に関する詳細情報。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
