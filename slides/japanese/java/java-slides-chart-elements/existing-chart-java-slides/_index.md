---
title: Java スライドの既存のチャート
linktitle: Java スライドの既存のチャート
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint プレゼンテーションを強化します。既存のグラフをプログラムで変更する方法を学びます。グラフのカスタマイズのためのソース コードを含むステップ バイ ステップ ガイド。
weight: 12
url: /ja/java/chart-elements/existing-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides for Java を使用した Java スライドの既存チャートの紹介

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーション内の既存のグラフを変更する方法を説明します。グラフ データ、カテゴリ名、シリーズ名を変更し、グラフに新しいシリーズを追加する手順を説明します。プロジェクトに Aspose.Slides for Java が設定されていることを確認してください。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Aspose.Slides for Java ライブラリがプロジェクトに含まれています。
2. 変更するグラフを含む既存の PowerPoint プレゼンテーション。
3. Java開発環境をセットアップしました。

## ステップ1: プレゼンテーションを読み込む

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";

// PPTXファイルを表すプレゼンテーションクラスをインスタンス化する
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## ステップ2: スライドとグラフにアクセスする

```java
//最初のスライドにアクセス
ISlide sld = pres.getSlides().get_Item(0);

//スライド上のチャートにアクセスする
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## ステップ3: グラフデータとカテゴリ名を変更する

```java
//チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;

//チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

//チャートのカテゴリ名を変更する
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## ステップ4: 最初のチャートシリーズを更新する

```java
//最初のチャートシリーズを見てみましょう
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

//シリーズ名を更新
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

//シリーズデータの更新
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## ステップ5: 2番目のチャートシリーズを更新する

```java
//2番目のチャートシリーズを見てみましょう
series = chart.getChartData().getSeries().get_Item(1);

//シリーズ名を更新
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

//シリーズデータの更新
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## ステップ6: グラフに新しいシリーズを追加する

```java
//新しいシリーズの追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

//3番目のチャートシリーズを見てみましょう
series = chart.getChartData().getSeries().get_Item(2);

//シリーズデータを入力する
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## ステップ7: グラフの種類を変更する

```java
//グラフの種類を集合円柱に変更する
chart.setType(ChartType.ClusteredCylinder);
```

## ステップ8: 変更したプレゼンテーションを保存する

```java
//変更したグラフを含むプレゼンテーションを保存する
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

おめでとうございます! Aspose.Slides for Java を使用して、PowerPoint プレゼンテーション内の既存のグラフを正常に変更しました。このコードを使用して、PowerPoint プレゼンテーション内のグラフをプログラムでカスタマイズできるようになりました。

## Java スライドの既存のチャートの完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//PPTX ファイルを表す Presentation クラスをインスタンス化します // PPTX ファイルを表す Presentation クラスをインスタンス化します
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
//最初のスライドマーカーにアクセス
ISlide sld = pres.getSlides().get_Item(0);
//デフォルトデータでグラフを追加
IChart chart = (IChart) sld.getShapes().get_Item(0);
//チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;
//チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//チャートカテゴリ名の変更
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
//最初のチャートシリーズ
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//シリーズデータを更新中
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");//シリーズ名の変更
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
//テイクセカンドチャートシリーズ
series = chart.getChartData().getSeries().get_Item(1);
//シリーズデータを更新中
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");//シリーズ名の変更
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
//今、新しいシリーズを追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
//第3回チャートシリーズ
series = chart.getChartData().getSeries().get_Item(2);
//シリーズデータを入力中
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
//グラフ付きのプレゼンテーションを保存する
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## 結論

この包括的なチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーション内の既存のグラフを変更する方法を学びました。ステップバイステップのガイドに従い、ソース コードの例を利用することで、グラフを簡単にカスタマイズして更新し、特定の要件を満たすことができます。ここで説明した内容を要約します。

## よくある質問

### グラフの種類を変更するにはどうすればよいですか?

チャートの種類を変更するには、`chart.setType(ChartType.ChartTypeHere)`方法。置き換える`ChartTypeHere`希望するチャートタイプ、例えば`ChartType.ClusteredCylinder`私たちの例では。

### シリーズにさらにデータ ポイントを追加できますか?

はい、系列にデータポイントを追加するには、`series.getDataPoints().addDataPointForBarSeries(cell)`方法。適切なセルデータを提供するようにしてください。

### カテゴリ名を更新するにはどうすればよいですか?

カテゴリ名を更新するには、`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)`新しいカテゴリ名を設定します。

### シリーズ名を変更するにはどうすればよいですか?

シリーズ名を変更するには、`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)`新しいシリーズ名を設定します。

### チャートからシリーズを削除する方法はありますか?

はい、チャートからシリーズを削除するには、`chart.getChartData().getSeries().removeAt(index)`方法、ここで`index`削除するシリーズのインデックスです。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
