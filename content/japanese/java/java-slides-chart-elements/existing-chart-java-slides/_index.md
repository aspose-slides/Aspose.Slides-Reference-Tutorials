---
title: Java スライド内の既存のグラフ
linktitle: Java スライド内の既存のグラフ
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint プレゼンテーションを強化します。既存のグラフをプログラムで変更する方法を学びます。チャートをカスタマイズするためのソース コードを含むステップバイステップ ガイド。
type: docs
weight: 12
url: /ja/java/chart-elements/existing-chart-java-slides/
---

## Aspose.Slides for Java を使用した Java スライドの既存のグラフの概要

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーション内の既存のグラフを変更する方法を説明します。グラフのデータ、カテゴリ名、系列名を変更し、新しい系列をグラフに追加する手順を説明します。プロジェクトに Aspose.Slides for Java が設定されていることを確認してください。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Aspose.Slides for Java ライブラリがプロジェクトに含まれています。
2. 変更するグラフを含む既存の PowerPoint プレゼンテーション。
3. Java開発環境のセットアップ。

## ステップ 1: プレゼンテーションをロードする

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";

// PPTX ファイルを表すプレゼンテーション クラスをインスタンス化します。
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## ステップ 2: スライドとグラフにアクセスする

```java
//最初のスライドにアクセスする
ISlide sld = pres.getSlides().get_Item(0);

//スライド上のグラフにアクセスする
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## ステップ 3: グラフ データとカテゴリ名を変更する

```java
//チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;

//チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

//グラフのカテゴリ名の変更
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## ステップ 4: 最初のグラフ シリーズを更新する

```java
//最初のチャート シリーズを取得する
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

//シリーズ名を更新
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

//シリーズデータを更新
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## ステップ 5: 2 番目のチャート シリーズを更新する

```java
// 番目のチャート シリーズを見てみましょう
series = chart.getChartData().getSeries().get_Item(1);

//シリーズ名を更新
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

//シリーズデータを更新
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## ステップ 6: 新しい系列をチャートに追加する

```java
//新しいシリーズの追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// 番目のチャート シリーズを見てみましょう
series = chart.getChartData().getSeries().get_Item(2);

//シリーズデータを入力する
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## ステップ 7: グラフの種類を変更する

```java
//グラフの種類をクラスター円柱に変更します。
chart.setType(ChartType.ClusteredCylinder);
```

## ステップ 8: 変更したプレゼンテーションを保存する

```java
//変更したグラフを含むプレゼンテーションを保存する
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

おめでとう！ Aspose.Slides for Java を使用して、PowerPoint プレゼンテーション内の既存のグラフを正常に変更できました。このコードを使用して、PowerPoint プレゼンテーションのグラフをプログラム的にカスタマイズできるようになりました。

## Java スライド内の既存のグラフの完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//PPTX ファイルを表すプレゼンテーション クラスをインスタンス化する// PPTX ファイルを表すプレゼンテーション クラスをインスタンス化する
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
//最初の slideMarker にアクセスします
ISlide sld = pres.getSlides().get_Item(0);
//デフォルトのデータを含むグラフを追加する
IChart chart = (IChart) sld.getShapes().get_Item(0);
//チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;
//チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//グラフのカテゴリ名を変更する
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
//最初のチャート シリーズを取得する
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//シリーズデータ更新中
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");//シリーズ名の変更
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
//Take Second チャート シリーズ
series = chart.getChartData().getSeries().get_Item(1);
//シリーズデータ更新中
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");//シリーズ名の変更
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
//さて、新しいシリーズを追加します
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// 番目のチャート シリーズを取り上げます
series = chart.getChartData().getSeries().get_Item(2);
//シリーズデータを入力中です
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
//プレゼンテーションをグラフとともに保存する
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## 結論

この包括的なチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーション内の既存のグラフを変更する方法を学習しました。ステップバイステップのガイドに従い、ソース コードの例を利用することで、特定の要件を満たすようにグラフを簡単にカスタマイズおよび更新できます。ここで取り上げた内容の要約は次のとおりです。

## よくある質問

### グラフの種類を変更するにはどうすればよいですか?

チャートの種類を変更するには、`chart.setType(ChartType.ChartTypeHere)`方法。交換する`ChartTypeHere`などの目的のグラフ タイプを使用して、`ChartType.ClusteredCylinder`私たちの例では。

### シリーズにさらにデータ ポイントを追加できますか?

はい、次のコマンドを使用して、さらにデータ ポイントを系列に追加できます。`series.getDataPoints().addDataPointForBarSeries(cell)`方法。必ず適切なセル データを指定してください。

### カテゴリ名を更新するにはどうすればよいですか?

次を使用してカテゴリ名を更新できます`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)`新しいカテゴリ名を設定します。

### シリーズ名を変更するにはどうすればよいですか?

シリーズ名を変更するには、次を使用します。`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)`新しいシリーズ名を設定します。

### グラフから系列を削除する方法はありますか?

はい、次のコマンドを使用してグラフから系列を削除できます。`chart.getChartData().getSeries().removeAt(index)`メソッド、ここで`index`は、削除するシリーズのインデックスです。