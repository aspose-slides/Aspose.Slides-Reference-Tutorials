---
"description": "Aspose.Slidesを使って、Javaスライドで魅力的なグラフを作成し、プロパティを管理する方法を学びましょう。ステップバイステップのガイドとソースコードで、効果的なプレゼンテーションを作成できます。"
"linktitle": "Javaスライドでプロパティチャートを管理する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドでプロパティチャートを管理する"
"url": "/ja/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドでプロパティチャートを管理する


## Aspose.Slides を使用した Java スライドのプロパティとグラフの管理の概要

このチュートリアルでは、Aspose.Slides を使用して Java スライドのプロパティを管理し、グラフを作成する方法を説明します。Aspose.Slides は、PowerPoint プレゼンテーションを操作するための強力な Java API です。ソースコード例を含め、ステップバイステップで手順を説明します。

## 前提条件

始める前に、Java用のAspose.Slidesライブラリがプロジェクトにインストールされ、設定されていることを確認してください。ダウンロードはこちらから。 [ここ](https://releases。aspose.com/slides/java/).

## スライドにグラフを追加する

スライドにグラフを追加するには、次の手順に従います。

1. 必要なクラスをインポートし、Presentation クラスのインスタンスを作成します。

```java
// プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

2. グラフを追加したいスライドにアクセスします。この例では、最初のスライドにアクセスします。

```java
// 最初のスライドにアクセス
ISlide slide = presentation.getSlides().get_Item(0);
```

3. デフォルトデータを含むグラフを追加します。今回は、StackedColumn3Dグラフを追加します。

```java
// デフォルトデータでグラフを追加する
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## チャートデータの設定

グラフデータを設定するには、グラフデータワークブックを作成し、系列とカテゴリを追加する必要があります。以下の手順に従ってください。

4. チャート データ シートのインデックスを設定します。

```java
// チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;
```

5. グラフ データ ワークブックを取得します。

```java
// チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. グラフに系列を追加します。この例では、「Series 1」と「Series 2」という2つの系列を追加します。

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. グラフにカテゴリを追加します。ここでは3つのカテゴリを追加します。

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 3D回転プロパティの設定

次に、チャートの 3D 回転プロパティを設定します。

8. 直角軸を設定します。

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. X軸とY軸の回転角度を設定します。この例では、X軸を40度、Y軸を270度回転させます。

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. 深度パーセンテージを 150 に設定します。

```java
chart.getRotation3D().setDepthPercents(150);
```

## シリーズデータの入力

11. 番目のグラフ シリーズを取得し、データ ポイントを入力します。

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// シリーズデータを入力する
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 重なりを調整する

12. 系列の重複値を設定します。例えば、重複しない場合は100に設定します。

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## プレゼンテーションを保存する

最後に、プレゼンテーションをディスクに保存します。

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

これで完了です。Java で Aspose.Slides を使用して、カスタム プロパティを持つ 3D 積み上げ縦棒グラフを作成できました。

## Javaスライドでプロパティチャートを管理するための完全なソースコード

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
// 最初のスライドにアクセス
ISlide slide = presentation.getSlides().get_Item(0);
// デフォルトデータでグラフを追加する
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// チャートデータシートのインデックスの設定
int defaultWorksheetIndex = 0;
// チャートデータワークシートの取得
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// シリーズを追加
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// カテゴリーを追加
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Rotation3Dプロパティを設定する
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// 第2チャートシリーズ
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// シリーズデータを入力中
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// OverLap値を設定する
series.getParentSeriesGroup().setOverlap((byte) 100);
// プレゼンテーションをディスクに書き込む
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## 結論

このチュートリアルでは、Aspose.Slides を使用して Java スライドのプロパティ管理とグラフ作成の世界を詳しく解説しました。Aspose.Slides は、開発者が PowerPoint プレゼンテーションを効率的に操作できるようにする強力な Java API です。基本的な手順を説明し、ソースコード例も提供して、プロセスを分かりやすく解説しました。

## よくある質問

### グラフの種類を変更するにはどうすればよいですか?

チャートの種類を変更するには、 `ChartType` グラフを追加する際のパラメータ。利用可能なグラフの種類については、Aspose.Slides のドキュメントを参照してください。

### グラフの色をカスタマイズできますか?

はい、系列データ ポイントまたはカテゴリの塗りつぶしプロパティを設定することで、グラフの色をカスタマイズできます。

### シリーズにデータ ポイントを追加するにはどうすればよいですか?

系列にデータポイントを追加するには、 `series.getDataPoints().addDataPointForBarSeries()` メソッドを使用し、データ値を含むセルを指定します。

### 異なる回転角度を設定するにはどうすればよいですか?

X軸とY軸に異なる回転角度を設定するには、 `chart.getRotation3D().setRotationX()` そして `chart.getRotation3D().setRotationY()` 希望の角度値を設定します。

### 他にカスタマイズできる 3D プロパティは何ですか?

Aspose.Slides のドキュメントを参照すると、深度、遠近感、照明など、グラフのその他の 3D プロパティを調べることができます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}