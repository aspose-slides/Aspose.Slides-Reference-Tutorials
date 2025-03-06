---
title: Java スライドのドーナツ チャートの穴
linktitle: Java スライドのドーナツ チャートの穴
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java スライドでカスタムの穴のサイズを持つドーナツ グラフを作成します。グラフのカスタマイズに関するソース コード付きのステップ バイ ステップ ガイド。
weight: 11
url: /ja/java/chart-elements/doughnut-chart-hole-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java スライドの穴付きドーナツ チャートの紹介

このチュートリアルでは、Aspose.Slides for Java を使用して穴の開いたドーナツ グラフを作成する手順を説明します。このステップ バイ ステップ ガイドでは、ソース コードの例を使用してプロセスを順を追って説明します。

## 前提条件

始める前に、JavaプロジェクトにAspose.Slides for Javaライブラリがインストールされ、設定されていることを確認してください。[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/).

## ステップ1: 必要なライブラリをインポートする

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ステップ2: プレゼンテーションを初期化する

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";

//プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

## ステップ3: ドーナツグラフを作成する

```java
try {
    //最初のスライドにドーナツグラフを作成する
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    //ドーナツグラフの穴のサイズを設定します（パーセンテージ）
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    //プレゼンテーションをディスクに保存する
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    //プレゼンテーションオブジェクトを破棄する
    if (presentation != null) presentation.dispose();
}
```

## ステップ4: コードを実行する

IDEまたはテキストエディタでJavaコードを実行して、穴のサイズが指定されたドーナツグラフを作成します。`"Your Document Directory"`プレゼンテーションを保存する実際のパスを入力します。

## Java スライドのドーナツ チャート ホールの完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションクラスのインスタンスを作成する
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

このチュートリアルでは、Aspose.Slides for Javaを使用して穴のあるドーナツグラフを作成する方法を学びました。穴のサイズは、`setDoughnutHoleSize`メソッドパラメータ。

## よくある質問

### グラフのセグメントの色を変更するにはどうすればよいですか?

チャートセグメントの色を変更するには、`setDataPointsInLegend`方法`IChart`オブジェクトを作成し、各データ ポイントに希望の色を設定します。

### ドーナツ グラフのセグメントにラベルを追加できますか?

はい、ドーナツグラフのセグメントにラベルを追加することができます。`setDataPointsLabelValue`方法`IChart`物体。

### チャートにタイトルを追加することは可能ですか?

もちろんです！チャートにタイトルを追加するには、`setTitle`方法`IChart`オブジェクトを作成し、必要なタイトル テキストを指定します。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
