---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET を使用して、マーカー付きの折れ線グラフを作成する方法を学びましょう。このステップバイステップガイドでは、設定、グラフの作成、カスタマイズについて解説します。"
"title": "Aspose.Slides for .NET を使用して C# でマーカー付き折れ線グラフを作成する方法"
"url": "/ja/net/charts-graphs/create-line-chart-markers-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET を使用して C# でマーカー付き折れ線グラフを作成する方法

## 導入
視覚的に魅力的で情報豊富な折れ線グラフを作成することは、C# で効果的にデータを表示する上で不可欠です。 **Aspose.Slides .NET 版** マーカー付きグラフを含む、プロフェッショナルなグラフの追加プロセスを簡素化します。このチュートリアルでは、Aspose.Slides for .NET を使用して、デフォルトのマーカー付きの折れ線グラフを作成する手順を説明します。

このチュートリアルでは、次の内容を学習します。
- Aspose.Slides for .NET を使用するための環境を設定します。
- マーカーを含む折れ線グラフを使用してプレゼンテーションを作成し、カスタマイズします。
- カテゴリ、系列、データ ポイントなどのグラフ プロパティを構成します。
- 最終的なプレゼンテーション ファイルを保存します。

まず、ソリューションを実装する前に必要な前提条件を確認しましょう。

## 前提条件
始める前に、次のものがあることを確認してください。
- **必要なライブラリ:** Aspose.Slides for .NET は NuGet 経由で開発環境にインストールされます。
- **環境設定要件:** Visual Studio や .NET Framework などの動作する C# 開発環境がマシンにインストールされています。
- **知識の前提条件:** C# プログラミングの基本的な理解と、プログラムによるプレゼンテーションの作成に関する知識。

## Aspose.Slides for .NET のセットアップ
### インストール情報
Aspose.Slides for .NET の使用を開始するには、次のいずれかの方法でプロジェクトに追加します。

**.NET CLI の使用:**
```bash
dotnet add package Aspose.Slides
```

**Visual Studio のパッケージ マネージャー コンソール経由:**
```powershell
Install-Package Aspose.Slides
```

**NuGet パッケージ マネージャー UI:**
- Visual Studio でソリューションを開きます。
- 「ソリューションの NuGet パッケージの管理...」に移動します。
- 「Aspose.Slides」を検索し、最新バージョンをインストールします。

### ライセンス取得
Aspose.Slides を使用する前に、試用版または購入ライセンスを入手してください。
1. **無料トライアル:** 訪問 [Asposeの無料トライアルページ](https://releases.aspose.com/slides/net/) すぐに開始します。
2. **一時ライセンス:** 拡張アクセスについては、 [一時ライセンスページ](https://purchase。aspose.com/temporary-license/).
3. **購入：** Aspose.Slidesを本番環境で使用するには、ライセンスを購入してください。 [Aspose 購入](https://purchase。aspose.com/buy).

### 基本的な初期化
プロジェクトをセットアップし、必要なライセンスを取得したら、次のように Aspose.Slides を初期化します。
```csharp
using Aspose.Slides;
// プレゼンテーションクラスのインスタンスを作成する
Presentation pres = new Presentation();
```
環境が整ったので、マーカー付きの折れ線グラフの作成に進みましょう。

## 実装ガイド
### マーカー付き折れ線グラフを作成する
このセクションでは、Aspose.Slides for .NET を使用して、プレゼンテーションで既定のマーカー付きの折れ線グラフを作成および構成するために必要な各手順を学習します。

#### ステップ1: プレゼンテーションオブジェクトを作成する
まず、 `Presentation` クラス：
```csharp
using (Presentation pres = new Presentation())
{
    ISlide slide = pres.Slides[0];
```
ここでは、新しく作成されたプレゼンテーションの最初のスライドにアクセスします。

#### ステップ2: マーカー付きの折れ線グラフを追加する
次に、スライドにマーカー付きの折れ線グラフを追加します。
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
```
このコードは、新しいチャートタイプを追加します `LineWithMarkers` 座標 `(10, 10)` 寸法付き `400x400`。

#### ステップ3: 既存のシリーズとカテゴリをクリアする
データを追加する前に、既存のシリーズまたはカテゴリをクリアします。
```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```
これにより、チャートが白紙の状態から開始されます。

#### ステップ4: グラフデータワークブックを構成する
アクセス `ChartDataWorkbook` チャートのデータを管理するには:
```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```
このオブジェクトは、系列およびカテゴリ データを含むセルを管理するために重要です。

#### ステップ5: シリーズとカテゴリを追加する
グラフに新しいシリーズを追加し、データ ポイントを入力します。
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
IChartSeries series = chart.ChartData.Series[0];

// カテゴリと対応するデータポイントを定義する
chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "C1"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 1, 24));
chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "C2"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 1, 23));
chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "C3"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 1, -10));
chart.ChartData.Categories.Add(fact.GetCell(0, 4, 0, "C4"));

// 欠損値の処理方法を示すためにヌルデータポイントを追加します
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 1, (double?)null));
```
ここでは、カテゴリとそれに対応する系列データをグラフに入力します。 `null` 値はデモンストレーションとして扱われます。

#### ステップ6: 別のシリーズを追加する
別のシリーズを追加するには、このプロセスを繰り返します。
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 2, "Series 2"), chart.Type);
IChartSeries series2 = chart.ChartData.Series[1];

series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 2, 30));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 2, 10));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 2, 60));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 2, 40));
```

#### ステップ7: 凡例を有効にして構成する
読みやすさを向上させるためにグラフの凡例を有効にします。
```csharp
chart.HasLegend = true;
chart.Legend.Overlay = false;
```
これにより、凡例がグラフ上に重ならなくなり、表示されます。

#### ステップ8: プレゼンテーションを保存する
最後に、新しく追加されたグラフを含むプレゼンテーションを保存します。
```csharp
pres.Save("DefaultMarkersInChart.pptx");
}
```
### トラブルシューティングのヒント
- **データ バインディング エラー:** データ ポイントがカテゴリに正しく対応していることを確認します。
- **チャートが表示されない:** 確認する `chart.HasLegend` その他のプロパティも適切に設定されています。

## 実用的な応用
1. **事業レポート:** マーカー付きの折れ線グラフを使用して、時間の経過に伴う販売実績を追跡し、月間収益の傾向を表示します。
2. **財務分析:** デフォルトのマーカーを使用して株価の動きを視覚化し、ピークと谷を強調表示します。
3. **科学研究:** 分析のためにデータ ポイントを明確に区別する必要がある実験結果を提示します。

## パフォーマンスに関する考慮事項
- 大規模なデータセットを扱う場合は、データ シリーズとカテゴリの数を制限して最適化します。
- .NET でオブジェクトを速やかに破棄するなどのメモリ管理テクニックを使用して、リソースの使用量を削減します。

## 結論
このチュートリアルでは、Aspose.Slides for .NET を使用してマーカー付きの折れ線グラフを作成する方法を学習しました。これらの手順に従うことで、詳細でプロフェッショナルなグラフを作成し、プレゼンテーションをより魅力的にすることができます。スライドショーをさらに充実させるために、Aspose.Slides の他の機能もぜひご検討ください。

### 次のステップ
- Aspose.Slides で利用できるさまざまなグラフ タイプを試してください。
- 視覚的なインパクトを高めるためにグラフの外観をカスタマイズします。
- より高度な機能については、Aspose.Slides の追加ドキュメントを参照してください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}