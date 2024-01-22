---
title: Aspose.Slides for .NET でのチャートの傾向線の探索
linktitle: チャートの傾向線
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: このステップバイステップ ガイドでは、Aspose.Slides for .NET を使用してグラフにさまざまな傾向線を追加する方法を学びます。データ視覚化スキルを簡単に強化しましょう。
type: docs
weight: 12
url: /ja/net/advanced-chart-customization/chart-trend-lines/
---

データの視覚化とプレゼンテーションの世界では、グラフを組み込むことは、情報を効果的に伝える強力な方法となり得ます。 Aspose.Slides for .NET は、傾向線をグラフに追加する機能など、グラフを操作するための機能豊富なツール セットを提供します。このチュートリアルでは、Aspose.Slides for .NET を使用してグラフに傾向線を追加するプロセスを段階的に詳しく説明します。 

## 前提条件

Aspose.Slides for .NET の使用を開始する前に、次の前提条件が満たされていることを確認する必要があります。

1.  Aspose.Slides for .NET: ライブラリにアクセスして使用するには、Aspose.Slides for .NET がインストールされている必要があります。ライブラリは次から入手できます。[ダウンロードページ](https://releases.aspose.com/slides/net/).

2. 開発環境: 開発環境をセットアップしておく必要があります。できれば Visual Studio などの .NET 統合開発環境を使用してください。

3. C# の基礎知識: C# を使用して Aspose.Slides for .NET を操作するため、C# プログラミングの基本を理解していると役立ちます。

前提条件を説明したので、グラフに傾向線を追加するプロセスを段階的に説明していきます。

## 名前空間のインポート

まず、必要な名前空間を C# プロジェクトにインポートしていることを確認してください。これらの名前空間は、Aspose.Slides for .NET を操作するために不可欠です。

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## ステップ 1: プレゼンテーションを作成する

このステップでは、作業用の空のプレゼンテーションを作成します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";

//ディレクトリが存在しない場合は作成します。
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

//空のプレゼンテーションの作成
Presentation pres = new Presentation();
```

## ステップ 2: スライドにグラフを追加する

次に、集合縦棒グラフをスライドに追加します。

```csharp
//集合縦棒グラフの作成
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## ステップ 3: チャートに傾向線を追加する

ここで、さまざまなタイプのトレンド ラインをチャート シリーズに追加します。

### 指数近似曲線の追加

```csharp
//チャート シリーズ 1 に指数関数的なトレンド ラインを追加する
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### 線形傾向線の追加

```csharp
//チャート シリーズ 1 に線形トレンド ラインを追加
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### 対数傾向線の追加

```csharp
//チャート シリーズ 2 に対数トレンド ラインを追加
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### 移動平均トレンドラインの追加

```csharp
//チャート シリーズ 2 に移動平均トレンド ラインを追加
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### 多項式近似曲線の追加

```csharp
//チャート シリーズ 3 に多項式トレンド ラインを追加
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### 電力トレンド ラインの追加

```csharp
//チャート シリーズ 3 にパワー トレンド ラインを追加
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## ステップ 4: プレゼンテーションを保存する

傾向線をグラフに追加した後、プレゼンテーションを保存します。

```csharp
//プレゼンテーションの保存
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

それでおしまい！ Aspose.Slides for .NET を使用して、グラフにさまざまな傾向線を追加することができました。

## 結論

Aspose.Slides for .NET は、グラフを簡単に作成および操作できる多機能ライブラリです。このステップバイステップのガイドに従うことで、さまざまなタイプの傾向線をグラフに追加して、データの視覚的表現を強化できます。

### よくある質問

### Aspose.Slides for .NET のドキュメントはどこで見つけられますか?
ドキュメントにアクセスできます[ここ](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET をダウンロードするにはどうすればよいですか?
ダウンロード ページから Aspose.Slides for .NET をダウンロードできます。[ここ](https://releases.aspose.com/slides/net/).

### Aspose.Slides for .NET に利用できる無料トライアルはありますか?
はい、次のサイトにアクセスして、Aspose.Slides for .NET を無料で試すことができます。[このリンク](https://releases.aspose.com/).

### Aspose.Slides for .NET はどこで購入できますか?
 Aspose.Slides for .NET を購入するには、購入ページにアクセスしてください[ここ](https://purchase.aspose.com/buy).

### Aspose.Slides for .NET の一時ライセンスは必要ですか?
 Aspose.Slides for .NET の一時ライセンスは、以下から取得できます。[このリンク](https://purchase.aspose.com/temporary-license/).