---
"description": "Aspose.Slides for Javaを使用して、Javaスライドで穴のサイズをカスタマイズしたドーナツグラフを作成します。グラフのカスタマイズ方法をソースコード付きで段階的に解説します。"
"linktitle": "Javaスライドのドーナツグラフの穴"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドのドーナツグラフの穴"
"url": "/ja/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドのドーナツグラフの穴


## Javaスライドの穴付きドーナツチャートの紹介

このチュートリアルでは、Aspose.Slides for Java を使用して、穴の開いたドーナツグラフを作成する方法を解説します。このステップバイステップガイドでは、ソースコードの例を用いて、手順を詳しく説明します。

## 前提条件

始める前に、Aspose.Slides for JavaライブラリがJavaプロジェクトにインストールされ、セットアップされていることを確認してください。ライブラリは以下からダウンロードできます。 [Aspose.Slides for Java ドキュメント](https://reference。aspose.com/slides/java/).

## ステップ1: 必要なライブラリをインポートする

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ステップ2: プレゼンテーションを初期化する

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";

// プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```

## ステップ3: ドーナツグラフを作成する

```java
try {
    // 最初のスライドにドーナツグラフを作成する
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // ドーナツグラフの穴の大きさを設定します（パーセンテージ）
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // プレゼンテーションをディスクに保存する
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // プレゼンテーションオブジェクトを破棄する
    if (presentation != null) presentation.dispose();
}
```

## ステップ4: コードを実行する

IDEまたはテキストエディタでJavaコードを実行すると、指定した穴のサイズのドーナツグラフが作成されます。 `"Your Document Directory"` プレゼンテーションを保存する実際のパスを入力します。

## Javaスライドのドーナツグラフの穴の完全なソースコード

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// プレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// プレゼンテーションをディスクに書き込む
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Javaを使用して、穴のあるドーナツグラフを作成する方法を学びました。穴のサイズは、 `setDoughnutHoleSize` メソッドパラメータ。

## よくある質問

### グラフのセグメントの色を変更するにはどうすればよいですか?

チャートのセグメントの色を変更するには、 `setDataPointsInLegend` 方法 `IChart` オブジェクトを作成し、各データ ポイントに希望の色を設定します。

### ドーナツ グラフのセグメントにラベルを追加できますか?

はい、ドーナツグラフのセグメントにラベルを追加できます。 `setDataPointsLabelValue` 方法 `IChart` 物体。

### チャートにタイトルを追加することは可能ですか?

もちろんです！チャートにタイトルを追加するには、 `setTitle` 方法 `IChart` オブジェクトを作成し、希望するタイトル テキストを提供します。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}