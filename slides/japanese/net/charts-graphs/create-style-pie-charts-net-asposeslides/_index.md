---
"date": "2025-04-15"
"description": "Aspose.Slides を使用して .NET プレゼンテーションで円グラフの作成を自動化し、データの視覚化を簡単に強化する方法を学びます。"
"title": "Aspose.Slides を使用して .NET プレゼンテーションで円グラフを作成およびカスタマイズする方法"
"url": "/ja/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides を使用して .NET プレゼンテーションで円グラフを作成およびカスタマイズする方法

## 導入
魅力的で情報量の多いプレゼンテーションを作成することは、効果的なコミュニケーションに不可欠です。職場でデータを提示する場合でも、最新のプロジェクト成果を紹介する場合でも、その効果は重要です。データを視覚化する効果的な方法の一つは円グラフです。円グラフは、全体の一部を簡潔に表すことができます。しかし、PowerPointなどのプレゼンテーションソフトウェアで円グラフを手動で作成すると、時間がかかり、動的な更新に必要な柔軟性が欠ける可能性があります。

そこでAspose.Slides for .NETの出番です。この包括的なライブラリを使えば、プレゼンテーションをプログラムで作成、変更、スタイル設定できるため、ワークフローを自動化し、プレゼンテーション全体の一貫性を確保したい開発者にとって非常に役立つツールとなります。

このチュートリアルでは、Aspose.Slides for .NET を使用してプレゼンテーションで円グラフを作成およびカスタマイズする方法を学びます。以下の方法を学習します。
- **プレゼンテーションを作成し、スライドにアクセスする**
- **円グラフを追加して設定する**
- **グラフデータと系列をカスタマイズする**
- **円グラフのセクターのスタイル**
- **カスタムラベルを追加する**
- **表示プロパティを設定し、プレゼンテーションを保存する**

魅力的な円グラフを簡単に作成する準備はできましたか? さあ、始めましょう!

## 前提条件
始める前に、次の設定が完了していることを確認してください。

### 必要なライブラリ
- Aspose.Slides for .NET (バージョン 21.11 以降を推奨)

### 環境設定
- .NET Framework または .NET Core/5+/6+ を実行する開発環境
- Visual Studioなどのコードエディタ

### 知識の前提条件
- C#プログラミングの基本的な理解
- オブジェクト指向の概念に精通していること

## Aspose.Slides for .NET のセットアップ
始めるには、Aspose.Slidesライブラリをインストールする必要があります。以下のいずれかの方法でインストールできます。

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**パッケージマネージャーコンソール**
```powershell
Install-Package Aspose.Slides
```

**NuGet パッケージ マネージャー UI**
- Visual Studio でプロジェクトを開きます。
- 「ツール」>「NuGet パッケージ マネージャー」>「ソリューションの NuGet パッケージの管理」に移動します。
- 「Aspose.Slides」を検索し、最新バージョンをインストールします。

### ライセンス取得手順
Aspose.Slides を使用するには、まず一時ライセンスをダウンロードして無料トライアルを開始できます。 [Asposeのウェブサイト](https://purchase.aspose.com/temporary-license/) 取得するには、ライセンスのご購入をご検討ください。継続的なご利用には、フルライセンスのご購入をご検討ください。

### 基本的な初期化とセットアップ
インストールしたら、PPTX ファイルを表す Presentation クラスを初期化します。

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## 実装ガイド
円グラフの作成プロセスを分かりやすいセクションに分け、段階的に知識を深めていきます。各セクションは特定の機能に焦点を当てて設計されているため、段階的に知識を深めることができます。

### プレゼンテーションを作成し、スライドにアクセスする
**概要：** まず、新しいプレゼンテーションを作成し、最初のスライドにアクセスします。これで、グラフやその他の要素を追加するための準備が整います。

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // PPTXファイルを表すプレゼンテーションクラスをインスタンス化する
    Presentation presentation = new Presentation();
    
    // 最初のスライドにアクセス
    ISlide slides = presentation.Slides[0];
}
```

### 円グラフの追加と設定
**概要：** スライドに円グラフを追加し、コンテキストに合わせてタイトルを設定する方法を学びます。

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // PPTXファイルを表すプレゼンテーションクラスをインスタンス化する
    Presentation presentation = new Presentation();
    
    // 最初のスライドにアクセス
    ISlide slides = presentation.Slides[0];
    
    // スライドにデフォルトデータを含むグラフを追加する
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // 設定チャートタイトル
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### グラフデータと系列をカスタマイズする
**概要：** 特定の要件に合わせてデータ カテゴリとシリーズをカスタマイズします。

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // PPTXファイルを表すプレゼンテーションクラスをインスタンス化する
    Presentation presentation = new Presentation();
    
    // 最初のスライドにアクセス
    ISlide slides = presentation.Slides[0];
    
    // スライドにデフォルトデータを含むグラフを追加する
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // 最初の系列を値を表示に設定する
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // チャートデータシートのインデックスの設定
    int defaultWorksheetIndex = 0;
    
    // チャートデータワークシートの取得
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // デフォルトで生成されたシリーズとカテゴリを削除する
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // 新しいカテゴリの追加
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // 新しいシリーズの追加
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // シリーズデータを入力中
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### 円グラフのセクタースタイルをカスタマイズする
**概要：** 円グラフの個々のセクターにスタイルを設定して、視覚的な魅力を高め、重要なデータ ポイントを強調します。

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // PPTXファイルを表すプレゼンテーションクラスをインスタンス化する
    Presentation presentation = new Presentation();
    
    // 最初のスライドにアクセス
    ISlide slides = presentation.Slides[0];
    
    // スライドにデフォルトデータを含むグラフを追加する
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // チャートからシリーズを取得する
    IChartSeries series = chart.ChartData.Series[0];
    
    // シリーズ内の各データポイントのセクタースタイルのカスタマイズ
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // セクター境界の設定
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // セクター境界の設定
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // セクター境界の設定
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### 円グラフにカスタムラベルを追加する
**概要：** カスタム ラベルを追加して円グラフを強化し、データをより明確に表現します。

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // 必要に応じてラベルの位置を調整します
    }
}
```

### 結論
Aspose.Slides を使用して .NET プレゼンテーションで円グラフを作成およびカスタマイズする方法を学習しました。この自動化により、データ視覚化の作業が大幅に効率化され、時間を節約し、プレゼンテーション全体の一貫性を保つことができます。

Aspose.Slides for .NET の機能をさらに詳しく調べるには、他の種類のグラフを作成したり、より複雑なデザイン要素をスライドに統合したりするなどの追加機能を検討してください。

楽しいコーディングを！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}