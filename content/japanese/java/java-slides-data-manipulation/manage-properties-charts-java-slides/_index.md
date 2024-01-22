---
title: Java スライドでのプロパティ チャートの管理
linktitle: Java スライドでのプロパティ チャートの管理
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して、見事なグラフを作成し、Java スライドのプロパティを管理する方法を学びます。強力なプレゼンテーションのためのソースコードを含むステップバイステップのガイド。
type: docs
weight: 13
url: /ja/java/data-manipulation/manage-properties-charts-java-slides/
---

## Aspose.Slides を使用した Java スライドのプロパティとチャートの管理の概要

このチュートリアルでは、Aspose.Slides を使用して Java スライドでプロパティを管理し、グラフを作成する方法を説明します。 Aspose.Slides は、PowerPoint プレゼンテーションを操作するための強力な Java API です。ソースコードの例を含め、段階的にプロセスを説明します。

## 前提条件

始める前に、Java 用の Aspose.Slides ライブラリがプロジェクトにインストールされ、設定されていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/slides/java/).

## スライドにグラフを追加する

グラフをスライドに追加するには、次の手順に従います。

1. 必要なクラスをインポートし、Presentation クラスのインスタンスを作成します。

```java
// Presentationクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

2. グラフを追加するスライドにアクセスします。この例では、最初のスライドにアクセスします。

```java
//最初のスライドにアクセスする
ISlide slide = presentation.getSlides().get_Item(0);
```

3. デフォルトのデータを含むグラフを追加します。この場合、StackedColumn3D チャートを追加します。

```java
//デフォルトのデータを含むグラフを追加する
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## チャートデータの設定

グラフ データを設定するには、グラフ データ ワークブックを作成し、シリーズとカテゴリを追加する必要があります。次の手順を実行します：

4. チャートデータシートのインデックスを設定します。

```java
//チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;
```

5. チャート データ ワークブックを取得します。

```java
//チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. グラフに系列を追加します。この例では、「シリーズ 1」と「シリーズ 2」という名前の 2 つのシリーズを追加します。

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. チャートにカテゴリを追加します。ここでは、3 つのカテゴリを追加します。

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 3D 回転プロパティの設定

次に、グラフの 3D 回転プロパティを設定しましょう。

8. 直角軸を設定します。

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. X 軸と Y 軸の回転角度を設定します。この例では、X を 40 度、Y を 270 度回転します。

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. 深さのパーセンテージを 150 に設定します。

```java
chart.getRotation3D().setDepthPercents(150);
```

## シリーズデータの入力

11. 番目のグラフ シリーズを取得し、データ ポイントを入力します。

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

//シリーズデータを入力する
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## オーバーラップの調整

12. シリーズのオーバーラップ値を設定します。たとえば、重複をなくす場合は 100 に設定できます。

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## プレゼンテーションの保存

最後に、プレゼンテーションをディスクに保存します。

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

それでおしまい！ Java の Aspose.Slides を使用して、カスタム プロパティを含む 3D 積み上げ縦棒グラフを正常に作成できました。

## Java スライドでプロパティ チャートを管理するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
// Presentationクラスのインスタンスを作成する
Presentation presentation = new Presentation();
//最初のスライドにアクセスする
ISlide slide = presentation.getSlides().get_Item(0);
//デフォルトのデータを含むグラフを追加する
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
//チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;
//チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//シリーズを追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
//カテゴリーの追加
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
//Rotation3D プロパティを設定する
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// 番目のチャート シリーズを取得する
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
//シリーズデータを入力中です
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
//オーバーラップ値を設定する
series.getParentSeriesGroup().setOverlap((byte) 100);
//プレゼンテーションをディスクに書き込む
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides を使用して Java スライドでプロパティを管理し、グラフを作成する世界を詳しく掘り下げました。 Aspose.Slides は、開発者が PowerPoint プレゼンテーションを効率的に操作できるようにする堅牢な Java API です。重要な手順を説明し、プロセスをガイドするソース コードの例を提供しました。

## よくある質問

### グラフの種類を変更するにはどうすればよいですか?

グラフの種類を変更するには、`ChartType`チャートを追加するときのパラメータ。使用可能なグラフの種類については、Aspose.Slides のドキュメントを参照してください。

### グラフの色をカスタマイズできますか?

はい、系列のデータ ポイントまたはカテゴリの塗りつぶしプロパティを設定することで、グラフの色をカスタマイズできます。

### シリーズにさらにデータ ポイントを追加するにはどうすればよいですか?

を使用して、系列にさらにデータ ポイントを追加できます。`series.getDataPoints().addDataPointForBarSeries()`メソッドを使用して、データ値を含むセルを指定します。

### 別の回転角度を設定するにはどうすればよいですか?

 X 軸と Y 軸に異なる回転角度を設定するには、次を使用します。`chart.getRotation3D().setRotationX()`そして`chart.getRotation3D().setRotationY()`希望の角度値を指定します。

### 他にどのような 3D プロパティをカスタマイズできますか?

Aspose.Slides ドキュメントを参照して、深さ、遠近感、照明などのチャートの他の 3D プロパティを調べることができます。