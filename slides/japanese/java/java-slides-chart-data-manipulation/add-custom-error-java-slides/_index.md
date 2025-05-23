---
"description": "Aspose.Slidesを使用して、JavaスライドのPowerPointグラフにカスタムエラーバーを追加する方法を学びましょう。ソースコード付きのステップバイステップガイドで、正確なデータ視覚化を実現します。"
"linktitle": "Javaスライドにカスタムエラーを追加する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドにカスタムエラーを追加する"
"url": "/ja/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドにカスタムエラーを追加する


## Aspose.Slides を使用して Java スライドにカスタム エラー バーを追加する方法の紹介

このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションのグラフにカスタムのエラーバーを追加する方法を学習します。エラーバーは、グラフ上のデータポイントの変動や不確実性を示すのに役立ちます。

## 前提条件

始める前に、次のものがあることを確認してください。

- Aspose.Slides for Java ライブラリがプロジェクトにインストールされ、構成されています。
- Java 開発環境をセットアップしました。

## ステップ1: 空のプレゼンテーションを作成する

まず、空の PowerPoint プレゼンテーションを作成します。

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// 空のプレゼンテーションを作成しています
Presentation presentation = new Presentation();
```

## ステップ2: バブルチャートを追加する

次に、プレゼンテーションにバブル チャートを追加します。

```java
// バブルチャートを作成する
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## ステップ3: カスタムエラーバーを追加する

ここで、チャート シリーズにカスタム エラー バーを追加してみましょう。

```java
// カスタムエラーバーを追加してその形式を設定する
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## ステップ4: エラーバーデータを設定する

この手順では、グラフ系列のデータ ポイントにアクセスし、各ポイントのカスタム エラー バーの値を設定します。

```java
// チャート系列のデータポイントにアクセスし、個々のポイントのエラーバーの値を設定する
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// チャート系列ポイントのエラーバーの設定
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## ステップ5: プレゼンテーションを保存する

最後に、カスタム エラー バーを含むプレゼンテーションを保存します。

```java
// プレゼンテーションを保存しています
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

これで完了です。Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションのグラフにカスタム エラー バーを追加することができました。

## Javaスライドにカスタムエラーを追加するための完全なソースコード

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// 空のプレゼンテーションを作成しています
Presentation presentation = new Presentation();
try
{
	// バブルチャートを作成する
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// カスタムエラーバーを追加してその形式を設定する
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// チャート系列のデータポイントにアクセスし、個々のポイントのエラーバーの値を設定する
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// チャート系列ポイントのエラーバーの設定
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// プレゼンテーションを保存しています
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

この包括的なチュートリアルでは、Aspose.Slides for Java を使用してグラフにカスタムエラーバーを追加することで、PowerPoint プレゼンテーションを強化する方法を学びました。エラーバーは、データの変動性と不確実性に関する貴重な洞察を提供し、グラフの情報量と視覚的な魅力を高めます。

## よくある質問

### エラーバーの外観をカスタマイズするにはどうすればよいですか?

エラーバーの外観は、 `IErrorBarsFormat` 線のスタイル、線の色、エラーバーの幅などのオブジェクト。

### 他の種類のグラフにエラー バーを追加できますか?

はい、棒グラフ、折れ線グラフ、散布図など、Aspose.Slides for Java でサポートされているさまざまなグラフ タイプにエラー バーを追加できます。

### 各データ ポイントに異なるエラー バー値を設定するにはどうすればよいですか?

上記のコードに示すように、データ ポイントをループし、各ポイントにカスタム エラー バーの値を設定できます。

### 特定のデータ ポイントのエラー バーを非表示にすることは可能ですか?

はい、個々のデータポイントのエラーバーの表示を制御するには、 `setVisible` の財産 `IErrorBarsFormat` 物体。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}