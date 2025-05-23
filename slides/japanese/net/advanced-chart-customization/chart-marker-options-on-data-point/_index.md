---
"description": "Aspose.Slides for .NET を使用して PowerPoint のグラフを強化する方法を学びましょう。データポイントマーカーを画像でカスタマイズし、魅力的なプレゼンテーションを作成します。"
"linktitle": "データポイントのチャートマーカーオプション"
"second_title": "Aspose.Slides .NET PowerPoint 処理 API"
"title": "Aspose.Slides .NET でデータ ポイントにチャート マーカー オプションを使用する"
"url": "/ja/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides .NET でデータ ポイントにチャート マーカー オプションを使用する


プレゼンテーションやデータビジュアライゼーションの作業において、Aspose.Slides for .NET は、グラフの作成、カスタマイズ、操作のための幅広い強力な機能を提供します。このチュートリアルでは、データポイントのグラフマーカーオプションを使用してグラフプレゼンテーションを強化する方法を学びます。このステップバイステップガイドでは、前提条件の確認や名前空間のインポートから、各例を複数のステップに分解して、プロセスを順を追って説明します。

## 前提条件

データ ポイントでグラフ マーカー オプションを使用する前に、次の前提条件が満たされていることを確認してください。

- Aspose.Slides for .NET: Aspose.Slides for .NETがインストールされていることを確認してください。ダウンロードは以下から行えます。 [Webサイト](https://releases。aspose.com/slides/net/).

- サンプル プレゼンテーション: このチュートリアルでは、「Test.pptx」というサンプル プレゼンテーションを使用します。このプレゼンテーションはドキュメント ディレクトリに保存されている必要があります。

それでは、まず必要な名前空間をインポートしてみましょう。

## 名前空間のインポート

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

必要な名前空間をインポートし、プレゼンテーションを初期化しました。次は、データポイントでチャートマーカーオプションを使用する手順に進みます。

## ステップ1: デフォルトのチャートを作成する

```csharp

// ドキュメント ディレクトリへのパス。
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// デフォルトのチャートを作成する
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

指定された場所とサイズで、スライド上に「LineWithMarkers」タイプのデフォルトのグラフを作成します。

## ステップ2: デフォルトのグラフデータワークシートインデックスを取得する

```csharp
// デフォルトのグラフデータワークシートインデックスを取得する
int defaultWorksheetIndex = 0;
```

ここでは、デフォルトのグラフ データ ワークシートのインデックスを取得します。

## ステップ3: チャートデータワークシートを取得する

```csharp
// チャートデータワークシートの取得
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

チャート データを操作するために、チャート データ ワークブックを取得します。

## ステップ4: チャートシリーズの変更

```csharp
// デモシリーズを削除
chart.ChartData.Series.Clear();

// 新しいシリーズを追加
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

この手順では、既存のデモ シリーズを削除し、「シリーズ 1」という名前の新しいシリーズをチャートに追加します。

## ステップ5: データポイントの塗りつぶしを設定する

```csharp
// マーカーの画像を設定する
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// 最初のチャートシリーズを見てみましょう
IChartSeries series = chart.ChartData.Series[0];

// 画像塗りつぶしで新しいデータポイントを追加する
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

データ ポイントに画像マーカーを設定することで、各データ ポイントがグラフ上でどのように表示されるかをカスタマイズできます。

## ステップ6: チャート系列マーカーのサイズを変更する

```csharp
// チャート系列マーカーのサイズを変更する
series.Marker.Size = 15;
```

ここでは、グラフ シリーズ マーカーのサイズを調整して、視覚的に魅力的になるようにします。

## ステップ7: プレゼンテーションを保存する

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

最後に、新しいグラフ設定でプレゼンテーションを保存します。

## 結論

Aspose.Slides for .NET を使えば、様々なカスタマイズオプションを用いて、魅力的なグラフプレゼンテーションを作成できます。このチュートリアルでは、データポイントにグラフマーカーオプションを適用し、データの視覚的表現を強化する方法に焦点を当てました。Aspose.Slides for .NET を使えば、プレゼンテーションをワンランクアップさせ、より魅力的で情報量の多いものにすることができます。

Aspose.Slides for .NET についてご質問やサポートが必要な場合は、お気軽に [Aspose.Slides ドキュメント](https://reference.aspose.com/slides/net/) または、 [Asposeコミュニティ](https://forum.aspose.com/) サポートのため。

## よくある質問（FAQ）

### Aspose.Slides for .NET でデータ ポイントのマーカーとしてカスタム画像を使用できますか?
はい、このチュートリアルで説明されているように、Aspose.Slides for .NET ではカスタム画像をデータ ポイントのマーカーとして使用できます。

### Aspose.Slides for .NET でグラフの種類を変更するにはどうすればよいですか?
異なる値を指定することでチャートの種類を変更できます。 `ChartType` 「棒グラフ」、「円グラフ」、「面グラフ」など、グラフを作成するときに選択します。

### Aspose.Slides for .NET は最新バージョンの PowerPoint と互換性がありますか?
Aspose.Slides for .NET は、さまざまな PowerPoint 形式で動作するように設計されており、最新の PowerPoint バージョンとの互換性を維持するために定期的に更新されます。

### Aspose.Slides for .NET のその他のチュートリアルやリソースはどこで入手できますか?
追加のチュートリアルやリソースについては、 [Aspose.Slides ドキュメント](https://reference。aspose.com/slides/net/).

### Aspose.Slides for .NET の試用版はありますか?
はい、Aspose.Slides for .NETの無料試用版をダウンロードしてお試しいただけます。 [ここ](https://releases。aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}