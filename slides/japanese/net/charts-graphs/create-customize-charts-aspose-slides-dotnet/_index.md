---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET を使用してグラフを作成およびカスタマイズする方法（パーセンテージをデータラベルとして表示する方法を含む）を学びます。このステップバイステップのガイドに従ってください。"
"title": "Aspose.Slides .NET でグラフを作成およびカスタマイズする方法 - パーセンテージをラベルとして表示"
"url": "/ja/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides .NET でグラフを作成およびカスタマイズする方法: パーセンテージをラベルとして表示する

## 導入

データを効果的に提示することは多くの分野で重要であり、複雑な情報を明確なビジュアルに変換するグラフは重要な役割を果たします。完璧なグラフを作成するには、ラベルにパーセンテージを表示するなどのカスタマイズ作業が必要ですが、Aspose.Slides for .NET を使えば、こうした作業が容易になります。このライブラリは、PowerPoint プレゼンテーション内でのグラフの作成と変更のプロセスを簡素化します。

このチュートリアルでは、Aspose.Slides for .NET を使用して積み上げ縦棒グラフを一から作成し、データラベルとしてパーセンテージ値を表示してカスタマイズする方法を学びます。これらの手順に従うことで、正確で視覚的に魅力的なデータ表現でスライドの魅力を高めることができます。

**学習内容:**
- Aspose.Slides for .NET の初期化
- 積み上げ縦棒グラフの作成
- データラベルのパーセンテージを計算して表示する
- チャートのパフォーマンスを最適化するベストプラクティス

実装に進む前に、開始するための準備がすべて整っていることを確認しましょう。

## 前提条件

このチュートリアルを効果的に実行するには、次のものを用意してください。
- **.NET Core SDK** マシンにインストールされています。
- C# および .NET アプリケーション開発に関する基本的な理解。
- C# コードを記述および実行するための Visual Studio または同様の IDE。

グラフを作成するには Aspose.Slides for .NET が必要なので、以下の説明に従って設定されていることを確認してください。

## Aspose.Slides for .NET のセットアップ

Aspose.Slides for .NETは、PowerPointプレゼンテーションをプログラムで操作できる強力なライブラリです。プロジェクトに追加する手順は以下のとおりです。

### インストール

**.NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**パッケージ マネージャー コンソール:**
```powershell
Install-Package Aspose.Slides
```

**NuGet パッケージ マネージャー UI:** 
- NuGet パッケージマネージャーを開き、「Aspose.Slides」を検索します。最新バージョンをインストールしてください。

### ライセンス取得

Aspose.Slidesを最大限に活用するには、まず無料トライアルをお試しください。長期間ご利用いただくには、一時ライセンスの取得またはご購入をご検討ください。 [アポーズ](https://purchase.aspose.com/buy)プロジェクト環境でライセンスを設定するには、ガイドラインに従ってください。

### 基本的な初期化

インストールしたら、 `Presentation` スライドの作成を開始するクラス:
```csharp
using Aspose.Slides;

// プレゼンテーションクラスのインスタンスを初期化する
tPresentation presentation = new Presentation();
```

次に、Aspose.Slides for .NET を使用してグラフの作成とカスタマイズ機能を実装する手順に進みます。

## 実装ガイド

### 積み上げ縦棒グラフを作成する

積み上げ縦棒グラフを作成し、データラベルとしてパーセンテージを表示してカスタマイズすることを目標とします。手順は以下のとおりです。

#### プレゼンテーションを初期化する

まずインスタンスを作成します `Presentation`：
```csharp
using Aspose.Slides;

// プレゼンテーションクラスのインスタンスを初期化する
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### スライドにグラフを追加する

指定した座標と寸法で最初のスライドに積み上げ縦棒グラフを追加します。
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
この行は、 `StackedColumn` 位置 (20, 20) にある幅と高さが 400 のチャート。

#### パーセンテージ計算の合計値を計算する

パーセンテージを表示するには、すべての系列にわたって各カテゴリの合計値を計算します。
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // 各カテゴリのすべての系列の値を合計します
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### データラベルをカスタマイズしてパーセンテージ値を表示する

次に、各シリーズを反復処理し、データ ラベルをカスタマイズします。
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // パーセンテージを計算する
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // 重複を避けるためにテキストをクリアする
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // デフォルトのデータラベルを非表示にするようにラベル形式を設定する
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

このセクションでは、各データ ポイントのパーセンテージを計算し、それをカスタム ラベルとして設定し、デフォルトのラベルと重複しないようにします。

#### プレゼンテーションを保存する

最後に、プレゼンテーションを保存して結果を表示します。
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## 実用的な応用

グラフにパーセンテージを表示すると、次のようなシナリオで特に役立ちます。
1. **財務報告:** ポートフォリオの分配または投資収益をパーセンテージで表示します。
2. **売上分析:** 市場シェア データをパーセンテージで表し、地域全体のパフォーマンスを強調します。
3. **調査結果：** アンケートの回答をパーセンテージで表示して、視覚的に比較しやすくします。
4. **プロジェクト管理：** リソースの割り当てを示すには、パーセンテージ付きの円グラフを使用します。
5. **教育：** 明確なパーセンテージベースのビジュアルを使用して統計の概念を説明します。

これらのカスタマイズされたチャートを CRM や ERP などのシステムに統合すると、ダッシュボードやレポートが強化され、意思決定プロセスを支援できます。

## パフォーマンスに関する考慮事項

Aspose.Slides for .NET を使用する場合、特に大規模なデータセットを扱うときは次の点に注意してください。
- **メモリ管理:** プレゼンテーションオブジェクトを適切に破棄してメモリを解放します。 `using` 該当する場合の声明。
- **効率的なデータ処理:** 計算のオーバーヘッドを削減するために、可能な場合はループの外で計算を実行します。
- **負荷分散:** Web アプリケーションの場合、同時チャート生成リクエストに対してサーバー リソースが適切にプロビジョニングされていることを確認します。

## 結論

このチュートリアルでは、Aspose.Slides for .NET を使用して、パーセンテージ値をラベルとして表示するグラフの作成とカスタマイズについて説明しました。これらのテクニックを習得すれば、詳細かつ視覚的に魅力的なデータ表現でプレゼンテーションを充実させることができます。

次のステップとして、Aspose.Slides で利用可能な他の種類のグラフやカスタマイズオプションを試してみてください。さまざまなデータセットを試して、洞察を明確に伝える強力なビジュアルに変換してみましょう。

## FAQセクション

**Q1: Aspose.Slides for .NET でグラフを作成するときに、大規模なデータ セットをどのように処理すればよいですか?**
A1: 大規模なデータセットの場合は、計算を最適化し、効率的なメモリ管理技術を使用します。メモリの過負荷を回避するために、処理タスクを分割します。

**Q2: Aspose.Slides for .NET を Web アプリケーションで使用できますか?**
A2: はい、ASP.NETアプリケーションに統合できます。最適なパフォーマンスを得るには、適切なサーバーリソースの割り当てを確保してください。

**Q3: Aspose.Slides で作成したグラフを他の形式でエクスポートすることは可能ですか?**
A3: もちろんです！ライブラリの機能を使用して、カスタマイズしたグラフを含むプレゼンテーションを PDF や画像ファイルなどのさまざまな形式でエクスポートできます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}