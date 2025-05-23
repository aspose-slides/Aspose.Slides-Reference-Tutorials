---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET を使用して動的なドーナツグラフを作成する方法を学びましょう。セットアップや高度な機能など、ステップバイステップの手順については、このガイドをご覧ください。"
"title": "Aspose.Slides .NET でドーナツ チャートを作成する手順ガイド | チャートとグラフ"
"url": "/ja/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ステップバイステップガイド: Aspose.Slides .NET でドーナツグラフを作成する

## 導入

データ分析結果をチームやクライアントにプレゼンテーションする必要があり、情報を魅力的に視覚化する必要があると想像してみてください。そんな時、ドーナツチャートは、生の数字を分かりやすい分析情報に変換できる万能ツールです。Aspose.Slides for .NETを使えば、プレゼンテーションスライドにカスタムドーナツチャートを簡単に効率的に作成できます。このガイドでは、Aspose.Slidesを使って、視覚的に魅力的なドーナツチャートを作成し、カスタマイズ可能な系列設定も含めた方法を説明します。

**学習内容:**
- Aspose.Slides for .NET を使用した開発環境のセットアップ
- プレゼンテーションでドーナツグラフを作成およびカスタマイズする
- カテゴリ名やリーダーラインなどの高度な機能を実装する
- 大規模データセットのパフォーマンスの最適化

始めるために必要な前提条件について詳しく見ていきましょう。

## 前提条件

この機能を実装する前に、開発環境が適切に設定されていることを確認してください。このチュートリアルは、.NETプログラミングの基礎知識とVisual Studioまたは同様のIDEの使用経験があることを前提としています。

### 必要なライブラリとバージョン
- **Aspose.Slides .NET 版**最新バージョンとの互換性を確認するには、 [公式文書](https://reference。aspose.com/slides/net/).

### 環境設定要件
- 動作する .NET 環境。
- Visual Studio などのコード エディターへのアクセス。

### 知識の前提条件
- C# および .NET フレームワークの基本的な理解。
- プレゼンテーション ソフトウェアの概念に関する知識 (オプションですが役立ちます)。

## Aspose.Slides for .NET のセットアップ

プロジェクトでAspose.Slidesを使用するには、NuGet経由でインストールする必要があります。以下の方法があります。

**.NET CLI の使用:**
```bash
dotnet add package Aspose.Slides
```

**パッケージマネージャーの使用:**
```powershell
Install-Package Aspose.Slides
```

**NuGet パッケージ マネージャー UI:**
「Aspose.Slides」を検索し、最新バージョンをインストールします。

### ライセンス取得手順

1. **無料トライアル**から始めましょう [無料トライアル](https://releases.aspose.com/slides/net/) 基本的な機能を調べます。
2. **一時ライセンス**評価目的で全機能にアクセスする必要がある場合は、次のサイトにアクセスして一時ライセンスを取得してください。 [ここ](https://purchase。aspose.com/temporary-license/).
3. **購入**商用利用の場合は、 [Aspose ウェブサイト](https://purchase。aspose.com/buy).

インストールしてライセンスを取得したら、プロジェクトで Aspose.Slides を初期化します。
```csharp
using Aspose.Slides;

// Aspose.Slides for .NET を初期化する
var presentation = new Presentation();
```

## 実装ガイド

### 新しいプレゼンテーションを作成し、ドーナツグラフを追加する

#### 概要
まず、新しいプレゼンテーションを作成し、最初のスライドにドーナツグラフを追加します。このセクションでは、既存のプレゼンテーションの読み込み、スライドへのアクセス、グラフの挿入について説明します。

**ステップ1: プレゼンテーションを読み込むか作成する**
まず、ドキュメント ディレクトリを指定して、既存のプレゼンテーションを読み込みます。
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
既存のファイルがない場合は、新しいファイルを作成します。 `new Presentation()`。

**ステップ2：最初のスライドにアクセスする**
グラフを追加する最初のスライドにアクセスします。
```csharp
ISlide slide = pres.Slides[0];
```

**ステップ3: ドーナツグラフを追加する**
指定した座標と寸法でドーナツ グラフを追加します。
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### データワークブックの構成

#### 概要
このセクションでは、ドーナツ グラフに関連付けられたデータ ブックを構成する方法について説明します。

**ステップ4: 既存のデータにアクセスして消去する**
グラフのデータブックにアクセスし、既存の系列またはカテゴリをクリアします。
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**ステップ5: 凡例を無効にしてシリーズを追加する**
凡例を無効にしてグラフをすっきりと保ち、カスタム構成で最大 15 個のシリーズを追加します。
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### カテゴリとデータポイントの追加

#### 概要
次に、各シリーズのカテゴリとデータ ポイントをグラフに入力してみましょう。

**ステップ6: カテゴリを追加する**
ループして 15 個のカテゴリを追加します。
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**ステップ7: データポイントを入力する**
現在のカテゴリ内の各系列にデータ ポイントを追加します。
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // 外観をカスタマイズする
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // 最後のシリーズのラベル形式を設定する
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // ラベル表示を設定する
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### プレゼンテーションを保存する

**ステップ8: ファイルを保存する**
最後に、プレゼンテーションを指定したディレクトリに保存します。
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}