---
title: Aspose.Slides for .NET のチャートのトレンド ラインの探索
linktitle: チャートトレンドライン
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: このステップバイステップ ガイドでは、Aspose.Slides for .NET を使用してさまざまなトレンド ラインをグラフに追加する方法を説明します。データ視覚化スキルを簡単に強化できます。
weight: 12
url: /ja/net/advanced-chart-customization/chart-trend-lines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for .NET のチャートのトレンド ラインの探索


データの視覚化とプレゼンテーションの世界では、グラフを組み込むことは情報を効果的に伝える強力な手段となります。Aspose.Slides for .NET は、グラフにトレンド ラインを追加する機能など、グラフを操作するための機能豊富なツール セットを提供します。このチュートリアルでは、Aspose.Slides for .NET を使用して、トレンド ラインをグラフに追加するプロセスを段階的に説明します。 

## 前提条件

Aspose.Slides for .NET の使用を開始する前に、次の前提条件が満たされていることを確認する必要があります。

1. Aspose.Slides for .NET: ライブラリにアクセスして使用するには、Aspose.Slides for .NETがインストールされている必要があります。ライブラリは以下から入手できます。[ダウンロードページ](https://releases.aspose.com/slides/net/).

2. 開発環境: 開発環境をセットアップする必要があります。Visual Studio などの .NET 統合開発環境を使用することをお勧めします。

3. C# の基礎知識: Aspose.Slides for .NET を操作するために C# を使用するため、C# プログラミングの基礎を理解していると役立ちます。

前提条件について説明したので、チャートにトレンド ラインを追加するプロセスを段階的に説明しましょう。

## 名前空間のインポート

まず、必要な名前空間を C# プロジェクトにインポートしてください。これらの名前空間は、Aspose.Slides for .NET を操作するために不可欠です。

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## ステップ1: プレゼンテーションを作成する

このステップでは、作業するための空のプレゼンテーションを作成します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "Your Document Directory";

//ディレクトリがまだ存在しない場合は作成します。
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

//空のプレゼンテーションを作成しています
Presentation pres = new Presentation();
```

## ステップ2: スライドにグラフを追加する

次に、スライドに集合縦棒グラフを追加します。

```csharp
//集合縦棒グラフの作成
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## ステップ3: チャートにトレンドラインを追加する

ここで、チャート シリーズにさまざまな種類のトレンド ラインを追加します。

### 指数トレンドラインの追加

```csharp
//チャートシリーズ 1 に指数トレンド ラインを追加する
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### 線形トレンドラインの追加

```csharp
//チャートシリーズ 1 に線形トレンド ラインを追加する
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### 対数トレンドラインの追加

```csharp
//チャートシリーズ 2 に対数トレンド ラインを追加する
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### 移動平均トレンドラインの追加

```csharp
//チャートシリーズ2に移動平均トレンドラインを追加する
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### 多項式トレンドラインの追加

```csharp
//チャートシリーズ 3 に多項式トレンド ラインを追加する
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### パワートレンドラインの追加

```csharp
//チャートシリーズ 3 にパワートレンドラインを追加する
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## ステップ4: プレゼンテーションを保存する

チャートにトレンド ラインを追加したら、プレゼンテーションを保存します。

```csharp
//プレゼンテーションを保存しています
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

これで完了です。Aspose.Slides for .NET を使用して、さまざまなトレンド ラインをグラフに追加できました。

## 結論

Aspose.Slides for .NET は、グラフを簡単に作成および操作できる多機能ライブラリです。このステップバイステップ ガイドに従うことで、さまざまな種類のトレンド ラインをグラフに追加し、データの視覚的表現を強化できます。

### よくある質問

### Aspose.Slides for .NET のドキュメントはどこにありますか?
ドキュメントにアクセスできます[ここ](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET をダウンロードするにはどうすればいいですか?
 Aspose.Slides for .NETはダウンロードページからダウンロードできます。[ここ](https://releases.aspose.com/slides/net/).

### Aspose.Slides for .NET の無料試用版はありますか?
はい、Aspose.Slides for .NETを無料でお試しいただけます。[このリンク](https://releases.aspose.com/).

### Aspose.Slides for .NET はどこで購入できますか?
 Aspose.Slides for .NETを購入するには、購入ページにアクセスしてください。[ここ](https://purchase.aspose.com/buy).

### Aspose.Slides for .NET には一時ライセンスが必要ですか?
 Aspose.Slides for .NETの一時ライセンスは以下から入手できます。[このリンク](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
