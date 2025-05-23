---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET を使用して、視覚的に魅力的なパーセンテージベースの積み上げ縦棒グラフを作成する方法を学びましょう。このステップバイステップのガイドに従って、明確なデータ視覚化を実現しましょう。"
"title": "Aspose.Slides を使用して .NET でパーセンテージベースの積み上げ縦棒グラフを作成する方法"
"url": "/ja/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET を使用してパーセンテージベースの積み上げ縦棒グラフを作成する方法

## 導入

データビジュアライゼーションにおいて、情報を明確かつ効果的に提示することは、効果的な意思決定に不可欠です。複雑なデータセットを直感的に表示するには、パーセンテージベースの積み上げ縦棒グラフが最適です。このガイドでは、プレゼンテーションファイルの操作用に設計された堅牢なライブラリであるAspose.Slides for .NETを使用して、これらのグラフを作成する手順を説明します。

このチュートリアルに従うと、次のことが学べます。
- グラフデータを設定し、数値形式を構成します。
- シリーズを追加し、その外観をカスタマイズします。
- 読みやすさを向上させるためにラベルをフォーマットします。

始める準備はできましたか？必要な前提条件から始めましょう。

## 前提条件

パーセンテージベースの積み上げ縦棒グラフを作成する前に、環境が正しく設定されていることを確認してください。以下のものが必要です。

### 必要なライブラリ、バージョン、依存関係
- **Aspose.Slides .NET 版**: このライブラリがインストールされていることを確認してください。

### 環境設定要件
- .NET SDK がインストールされた開発環境。
- C# コードを実行するための Visual Studio または互換性のある IDE。

### 知識の前提条件
- C# プログラミングの基本的な理解。
- .NET プロジェクトのセットアップとパッケージ管理に関する知識。

## Aspose.Slides for .NET のセットアップ

Aspose.Slides を使用してグラフの作成を開始するには、まず次のいずれかの方法でライブラリをインストールします。

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**パッケージマネージャー**
```powershell
Install-Package Aspose.Slides
```

**NuGet パッケージ マネージャー UI**
- 「Aspose.Slides」を検索し、最新バージョンをインストールします。

### ライセンス取得手順

まずは無料トライアルで一時ライセンスをダウンロードしてください。 [Asposeのウェブサイト](https://purchase.aspose.com/temporary-license/)継続して使用する場合は、フルライセンスの購入を検討してください。 

セットアップが完了したら、プロジェクトで Aspose.Slides を起動します。
```csharp
using Aspose.Slides;
```

## 実装ガイド

環境が準備できたら、パーセンテージベースの積み上げ縦棒グラフの作成を手順ごとに詳しく説明します。

### チャートの作成と設定

#### 概要
インスタンスを作成する `Presentation` スライドの操作に不可欠なクラスです。次に、スライドに積み上げ縦棒グラフを追加して設定します。

#### 積み上げ縦棒グラフの追加
```csharp
// プレゼンテーションクラスのインスタンスを作成する
document = new Presentation();

// 最初のスライドへの参照を取得する
slide = document.Slides[0];

// 位置 (20, 20) にサイズ (500x400) の PercentsStackedColumn チャートを追加します。
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### 数値形式の設定
データがパーセンテージとして表示されていることを確認します。
```csharp
// 縦軸の数値形式を設定する
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // 数値の形式をパーセンテージに設定する
```

#### データシリーズとポイントの追加
既存のシリーズデータをクリアし、新しいデータを追加します。
```csharp
// 既存のシリーズデータをクリアする
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Access チャート データ ワークブック
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// 新しいデータシリーズ「Reds」を追加します
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// シリーズの塗りつぶし色を赤に設定する
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// 「Reds」シリーズのラベル形式のプロパティを構成する
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // パーセンテージ形式を設定する
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// 別のシリーズ「ブルース」を追加
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// シリーズの塗りつぶし色を青に設定する
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // パーセンテージ形式を設定する
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### プレゼンテーションを保存する
プレゼンテーションをファイルに保存します。
```csharp
// プレゼンテーションをPPTX形式で保存する
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### トラブルシューティングのヒント
- すべての名前空間が正しくインポートされていることを確認します。
- プロパティ名とメソッド呼び出しのタイプミスをチェックします。
- ファイルを保存するためのパスが存在し、正しい権限があることを確認します。

## 実用的な応用

パーセンテージベースの積み上げ縦棒グラフが役立つシナリオをいくつか示します。
1. **売上分析**総売上高の割合として、さまざまな地域にわたる製品のパフォーマンスを視覚化します。
2. **予算配分**会社全体の支出に関連して各部門が予算をどのように割り当てているかを示します。
3. **市場調査**さまざまな製品カテゴリーの消費者の嗜好を時間の経過とともに比較します。
4. **教育データ**生徒の科目別の成績の分布を表示します。
5. **ヘルスケア統計**複数の健康状態にわたる患者の人口統計を表します。

## パフォーマンスに関する考慮事項

最適なパフォーマンスを得るには、次の点を考慮してください。
- データ ポイントの数を必要なものに制限します。
- 実行時処理を最小限に抑えるためにデータを事前にロードします。
- Aspose.Slides for .NET で効率的なメモリ管理プラクティスを使用します。

## 結論

おめでとうございます！Aspose.Slides for .NET を使用して、パーセンテージベースの積み上げ縦棒グラフを作成する方法を習得しました。このツールは、複雑なデータをより分かりやすく、視覚的に魅力的なものにすることで、プレゼンテーションの質を高めます。

次のステップは？Aspose.Slides で利用可能な他のチャートタイプを調べたり、この機能を大規模なアプリケーションに統合したりしてみましょう。コーディングを楽しみましょう！

## FAQセクション

**Q1: Aspose.Slides は無料で使用できますか?**
A1: はい、無料トライアルで Aspose.Slides の機能をテストすることができます。

**Q2: Aspose.Slides for .NET ではどのような種類のグラフがサポートされていますか?**
A2: 円グラフ、棒グラフ、縦棒グラフ、折れ線グラフなど、さまざまなグラフをサポートしています。

**Q3: Aspose.Slides for .NET を使い始めるにはどうすればよいですか?**
A3: 上記のように、NuGetまたは.NET CLIを使用してライブラリをインストールしてください。最初のチャートを作成するには、ドキュメントに従ってください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}