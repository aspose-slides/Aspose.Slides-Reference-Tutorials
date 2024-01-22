---
title: Java スライドのドーナツ チャートの穴
linktitle: Java スライドのドーナツ チャートの穴
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java スライドでカスタムの穴サイズを持つドーナツ チャートを作成します。チャートをカスタマイズするためのソース コードを含むステップバイステップ ガイド。
type: docs
weight: 11
url: /ja/java/chart-elements/doughnut-chart-hole-java-slides/
---

## Java スライドでの穴のあるドーナツ グラフの紹介

このチュートリアルでは、Aspose.Slides for Java を使用して穴のあるドーナツ グラフを作成する方法を説明します。このステップバイステップのガイドでは、ソース コードの例を使用してプロセスを説明します。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがインストールされ、Java プロジェクトに設定されていることを確認してください。からダウンロードできます。[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/).

## ステップ 1: 必要なライブラリをインポートする

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ステップ 2: プレゼンテーションを初期化する

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";

// Presentationクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

## ステップ 3: ドーナツ チャートを作成する

```java
try {
    //最初のスライドでドーナツ グラフを作成する
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    //ドーナツ チャートの穴のサイズを設定します (パーセント単位)。
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    //プレゼンテーションをディスクに保存する
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    //プレゼンテーションオブジェクトを破棄する
    if (presentation != null) presentation.dispose();
}
```

## ステップ 4: コードを実行する

IDE またはテキスト エディタで Java コードを実行して、指定した穴サイズのドーナツ チャートを作成します。必ず交換してください`"Your Document Directory"`プレゼンテーションを保存する実際のパスに置き換えます。

## Java スライドのドーナツ チャート ホールの完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
// Presentationクラスのインスタンスを作成する
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	//プレゼンテーションをディスクに書き込む
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して穴のあるドーナツ グラフを作成する方法を学習しました。を調整することで穴のサイズをカスタマイズできます。`setDoughnutHoleSize`メソッドのパラメータ。

## よくある質問

### チャートセグメントの色を変更するにはどうすればよいですか?

グラフセグメントの色を変更するには、`setDataPointsInLegend`のメソッド`IChart`オブジェクトを選択し、各データ ポイントに必要な色を設定します。

### ドーナツ グラフのセグメントにラベルを追加できますか?

はい、ドーナツ チャートのセグメントにラベルを追加するには、`setDataPointsLabelValue`のメソッド`IChart`物体。

### グラフにタイトルを追加することはできますか?

確かに！を使用してグラフにタイトルを追加できます。`setTitle`のメソッド`IChart`オブジェクトを作成し、必要なタイトル テキストを指定します。