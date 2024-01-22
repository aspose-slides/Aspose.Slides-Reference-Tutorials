---
title: Java スライドにカスタム エラーを追加する
linktitle: Java スライドにカスタム エラーを追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して、Java Slides の PowerPoint グラフにカスタム誤差範囲を追加する方法を学びます。正確なデータ視覚化のためのソースコードを含むステップバイステップのガイド。
type: docs
weight: 11
url: /ja/java/chart-data-manipulation/add-custom-error-java-slides/
---

## Aspose.Slides を使用した Java スライドへのカスタム誤差範囲の追加の概要

このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションのグラフにカスタム誤差範囲を追加する方法を学習します。エラーバーは、グラフ上のデータ ポイントのばらつきや不確実性を表示するのに役立ちます。

## 前提条件

始める前に、以下のものがあることを確認してください。

- Aspose.Slides for Java ライブラリがプロジェクトにインストールされ、構成されています。
- Java 開発環境がセットアップされています。

## ステップ 1: 空のプレゼンテーションを作成する

まず、空の PowerPoint プレゼンテーションを作成します。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//空のプレゼンテーションの作成
Presentation presentation = new Presentation();
```

## ステップ 2: バブル チャートを追加する

次に、プレゼンテーションにバブル チャートを追加します。

```java
//バブル チャートの作成
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## ステップ 3: カスタム誤差範囲を追加する

次に、カスタム誤差範囲をグラフ シリーズに追加しましょう。

```java
//カスタム誤差範囲の追加とその形式の設定
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## ステップ 4: 誤差範囲データを設定する

このステップでは、グラフ シリーズのデータ ポイントにアクセスし、各ポイントのカスタム誤差範囲の値を設定します。

```java
//チャート シリーズのデータ ポイントにアクセスし、個々のポイントの誤差範囲値を設定する
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

//チャートシリーズポイントの誤差範囲の設定
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## ステップ 5: プレゼンテーションを保存する

最後に、カスタム誤差範囲を含むプレゼンテーションを保存します。

```java
//プレゼンテーションの保存
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

それでおしまい！ Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションのグラフにカスタム誤差範囲を正常に追加しました。

## Java スライドにカスタム エラーを追加するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//空のプレゼンテーションの作成
Presentation presentation = new Presentation();
try
{
	//バブル チャートの作成
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	//カスタム誤差範囲の追加とその形式の設定
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	//チャート シリーズのデータ ポイントにアクセスし、個々のポイントの誤差範囲の値を設定する
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	//チャートシリーズポイントの誤差範囲の設定
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	//プレゼンテーションの保存
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

この包括的なチュートリアルでは、Aspose.Slides for Java を使用してグラフにカスタム誤差範囲を追加し、PowerPoint プレゼンテーションを強化する方法を学習しました。誤差範囲は、データの変動性と不確実性に関する貴重な洞察を提供し、グラフをより有益で視覚的に魅力的なものにします。

## よくある質問

### エラーバーの外観をカスタマイズするにはどうすればよいですか?

エラーバーの外観をカスタマイズするには、`IErrorBarsFormat`線のスタイル、線の色、エラーバーの幅などのオブジェクト。

### 他の種類のグラフに誤差範囲を追加できますか?

はい、Aspose.Slides for Java でサポートされているさまざまな種類のグラフ (棒グラフ、折れ線グラフ、散布図など) に誤差範囲を追加できます。

### データポイントごとに異なるエラーバー値を設定するにはどうすればよいですか?

上のコードに示すように、データ ポイントをループし、各ポイントにカスタム誤差範囲値を設定できます。

### 特定のデータポイントの誤差範囲を非表示にすることはできますか?

はい。設定することで、個々のデータ ポイントの誤差範囲の表示を制御できます。`setVisible`の財産`IErrorBarsFormat`物体。