---
title: Aspose.Slides .NET のデータ ポイントでのチャート マーカー オプションの使用
linktitle: データポイントのチャートマーカーオプション
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して PowerPoint グラフを強化する方法を学びます。画像を使用してデータ ポイント マーカーをカスタマイズします。魅力的なプレゼンテーションを作成します。
type: docs
weight: 11
url: /ja/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

プレゼンテーションやデータ視覚化を操作する場合、Aspose.Slides for .NET は、グラフを作成、カスタマイズ、操作するための強力な機能を幅広く提供します。このチュートリアルでは、データ ポイントでチャート マーカー オプションを使用してチャートのプレゼンテーションを強化する方法を説明します。このステップバイステップのガイドでは、前提条件と名前空間のインポートから始まり、各例を複数のステップに分割するまでのプロセスを説明します。

## 前提条件

データ ポイントでのチャート マーカー オプションの使用に入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Slides for .NET: Aspose.Slides for .NET がインストールされていることを確認してください。からダウンロードできます。[Webサイト](https://releases.aspose.com/slides/net/).

- サンプル プレゼンテーション: このチュートリアルでは、「Test.pptx」という名前のサンプル プレゼンテーションを使用します。このプレゼンテーションはドキュメント ディレクトリにあるはずです。

それでは、必要な名前空間をインポートすることから始めましょう。

## 名前空間のインポート

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

必要な名前空間をインポートし、プレゼンテーションを初期化しました。次に、データ ポイントでチャート マーカー オプションを使用してみましょう。

## ステップ 1: デフォルトのグラフの作成

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//デフォルトのグラフの作成
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

スライド上の指定された位置とサイズで、タイプ「LineWithMarkers」のデフォルトのグラフを作成します。

## ステップ 2: デフォルトのグラフ データ ワークシート インデックスの取得

```csharp
//デフォルトのチャート データ ワークシート インデックスの取得
int defaultWorksheetIndex = 0;
```

ここでは、デフォルトのチャート データ ワークシートのインデックスを取得します。

## ステップ 3: グラフ データ ワークシートを取得する

```csharp
//チャートデータワークシートの取得
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

チャート データを操作するためにチャート データ ワークブックをフェッチします。

## ステップ 4: チャート系列を変更する

```csharp
//デモシリーズを削除する
chart.ChartData.Series.Clear();

//新しいシリーズを追加
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

このステップでは、既存のデモ シリーズを削除し、「シリーズ 1」という名前の新しいシリーズをチャートに追加します。

## ステップ 5: データポイントの画像塗りつぶしを設定する

```csharp
//マーカーに画像を設定する
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

//最初のチャート シリーズを取得する
IChartSeries series = chart.ChartData.Series[0];

//画像塗りつぶしを使用して新しいデータ ポイントを追加する
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

データ ポイントにピクチャ マーカーを設定し、各データ ポイントがグラフ上でどのように表示されるかをカスタマイズできるようにします。

## ステップ 6: チャート系列マーカーのサイズを変更する

```csharp
//チャートシリーズのマーカーサイズの変更
series.Marker.Size = 15;
```

ここでは、グラフ系列マーカーのサイズを調整して、視覚的に魅力的なものにします。

## ステップ 7: プレゼンテーションを保存する

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

最後に、新しいグラフ設定を使用してプレゼンテーションを保存します。

## 結論

Aspose.Slides for .NET を使用すると、さまざまなカスタマイズ オプションを使用して魅力的なグラフ プレゼンテーションを作成できます。このチュートリアルでは、データ ポイントでチャート マーカー オプションを使用して、データの視覚的表現を強化することに重点を置きました。 Aspose.Slides for .NET を使用すると、プレゼンテーションを次のレベルに引き上げ、より魅力的で有益なものにすることができます。

 Aspose.Slides for .NET についてご質問がある場合、またはサポートが必要な場合は、お気軽に次のサイトにアクセスしてください。[Aspose.Slides ドキュメント](https://reference.aspose.com/slides/net/)または、に連絡してください[Aspose コミュニティ](https://forum.aspose.com/)サポートのための。

## よくある質問 (FAQ)

### Aspose.Slides for .NET でカスタム イメージをデータ ポイントのマーカーとして使用できますか?
はい、このチュートリアルで説明しているように、Aspose.Slides for .NET でカスタム イメージをデータ ポイントのマーカーとして使用できます。

### Aspose.Slides for .NET でグラフの種類を変更するにはどうすればよいですか?
別のグラフの種類を指定することで、グラフの種類を変更できます。`ChartType` 「棒」、「円」、「面」などのグラフを作成するときに使用します。

### Aspose.Slides for .NET は PowerPoint の最新バージョンと互換性がありますか?
Aspose.Slides for .NET は、さまざまな PowerPoint 形式で動作するように設計されており、最新の PowerPoint バージョンとの互換性を維持するために定期的に更新されます。

### Aspose.Slides for .NET のその他のチュートリアルやリソースはどこで見つけられますか?
追加のチュートリアルとリソースについては、[Aspose.Slides ドキュメント](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET の試用版は入手できますか?
はい、以下から無料試用版をダウンロードして、Aspose.Slides for .NET を試すことができます。[ここ](https://releases.aspose.com/).