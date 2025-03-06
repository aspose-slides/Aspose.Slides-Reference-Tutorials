---
title: Aspose.Slides for .NET で美しいグラフを作成する
linktitle: グラフのエンティティと書式設定
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して魅力的なグラフを作成する方法を学びます。ステップバイステップのガイドを使用して、データ視覚化のレベルを高めます。
weight: 13
url: /ja/net/advanced-chart-customization/chart-entities/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


今日のデータ駆動型の世界では、効果的なデータ視覚化が、情報を視聴者に伝える鍵となります。Aspose.Slides for .NET は、目を引くグラフを含む魅力的なプレゼンテーションやスライドを作成できる強力なライブラリです。このチュートリアルでは、Aspose.Slides for .NET を使用して美しいグラフを作成する手順を説明します。各例を複数の手順に分解して、グラフのエンティティと書式設定を理解して実装できるようにします。それでは、始めましょう。

## 前提条件

Aspose.Slides for .NET を使用して美しいグラフを作成する前に、次の前提条件が満たされていることを確認する必要があります。

1.  Aspose.Slides for .NET: Aspose.Slides for .NETライブラリがインストールされていることを確認してください。[Webサイト](https://releases.aspose.com/slides/net/).

2. 開発環境: Visual Studio または .NET 開発をサポートするその他の IDE を使用した開発環境が必要です。

3. 基本的な C# の知識: このチュートリアルでは、C# プログラミングの知識が必須です。

前提条件が整ったので、Aspose.Slides for .NET を使用して美しいグラフを作成してみましょう。

## 名前空間のインポート

まず、Aspose.Slides for .NET を操作するために必要な名前空間をインポートする必要があります。

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## ステップ1: プレゼンテーションを作成する

まず、作業に使用する新しいプレゼンテーションを作成します。このプレゼンテーションは、チャートのキャンバスとして機能します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "Your Document Directory";

//ディレクトリがまだ存在しない場合は作成します。
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

//プレゼンテーションのインスタンス化
Presentation pres = new Presentation();
```

## ステップ2: 最初のスライドにアクセスする

チャートを配置するプレゼンテーションの最初のスライドにアクセスしましょう。

```csharp
//最初のスライドにアクセスする
ISlide slide = pres.Slides[0];
```

## ステップ3: サンプルチャートを追加する

ここで、スライドにサンプル グラフを追加します。この例では、マーカー付きの折れ線グラフを作成します。

```csharp
//サンプルチャートの追加
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## ステップ4: グラフのタイトルを設定する

グラフにタイトルを付けて、より情報量が多く視覚的に魅力的なものにします。

```csharp
//設定チャートタイトル
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## ステップ5: 垂直軸のグリッド線をカスタマイズする

このステップでは、グラフの視覚的な魅力を高めるために、垂直軸のグリッド線をカスタマイズします。

```csharp
//値軸の主グリッド線の形式を設定する
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

//値軸の補助グリッド線の書式を設定する
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

//値軸の数値形式の設定
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## ステップ6: 垂直軸の範囲を定義する

このステップでは、垂直軸の最大値、最小値、単位値を設定します。

```csharp
//設定チャートの最大値、最小値
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## ステップ7: 垂直軸のテキストをカスタマイズする

ここで、垂直軸上のテキストの外観をカスタマイズします。

```csharp
//値軸テキストプロパティの設定
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

//値軸のタイトルの設定
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## ステップ8: 水平軸のグリッド線をカスタマイズする

次に、水平軸のグリッド線をカスタマイズしましょう。

```csharp
//カテゴリ軸の主グリッド線の形式を設定する
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

//カテゴリ軸の補助グリッド線の書式設定
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

//カテゴリ軸テキストプロパティの設定
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## ステップ9: 水平軸ラベルをカスタマイズする

この手順では、水平軸ラベルの位置と回転を調整します。

```csharp
//カテゴリ軸ラベルの位置を設定する
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

//カテゴリ軸ラベルの回転角度の設定
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## ステップ10: 凡例をカスタマイズする

読みやすさを向上させるために、グラフの凡例を強化しましょう。

```csharp
//凡例テキストプロパティの設定
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

//重複するチャートなしでチャートの凡例を表示するよう設定する
chart.Legend.Overlay = true;
```

## ステップ11: グラフの背景をカスタマイズする

チャート、背面の壁、床の背景色をカスタマイズします。

```csharp
//設定表 背面壁色
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//プロットエリアの色の設定
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## ステップ12: プレゼンテーションを保存する

最後に、フォーマットされたグラフを含むプレゼンテーションを保存しましょう。

```csharp
//プレゼンテーションを保存
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## 結論

Aspose.Slides for .NET を使用すると、プレゼンテーションで美しく情報豊富なグラフを作成することがこれまで以上に簡単になります。このチュートリアルでは、グラフのさまざまな側面をカスタマイズして、視覚的に魅力的で情報豊富なグラフを作成するための重要な手順について説明しました。これらのテクニックを使用すると、データを効果的に視聴者に伝える魅力的なグラフを作成できます。

Aspose.Slides for .NET を試して、データの視覚化を次のレベルに引き上げましょう。

## よくある質問

### 1. Aspose.Slides for .NET とは何ですか?

Aspose.Slides for .NET は、.NET 開発者が Microsoft PowerPoint プレゼンテーションを作成、操作、変換できるようにする強力なライブラリです。スライド、図形、グラフなどを操作する幅広い機能を提供します。

### 2. Aspose.Slides for .NET はどこからダウンロードできますか?

 Aspose.Slides for .NETはウェブサイトからダウンロードできます。[ここ](https://releases.aspose.com/slides/net/).

### 3. Aspose.Slides for .NET の無料試用版はありますか?

はい、Aspose.Slides for .NETの無料トライアルは以下から入手できます。[ここ](https://releases.aspose.com/).

### 4. Aspose.Slides for .NET の一時ライセンスを取得するにはどうすればよいですか?

臨時免許証が必要な場合は、[このリンク](https://purchase.aspose.com/temporary-license/).

### 5. Aspose.Slides for .NET のコミュニティまたはサポート フォーラムはありますか?

はい、Aspose.Slidesコミュニティとサポートフォーラムがあります。[ここ](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
