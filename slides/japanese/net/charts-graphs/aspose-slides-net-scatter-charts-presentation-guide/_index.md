---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET を使って、散布図でプレゼンテーションの魅力を高める方法を学びましょう。この包括的なガイドに従って、効果的に散布図を作成およびカスタマイズしましょう。"
"title": "Aspose.Slides .NET を使用してプレゼンテーションに散布図を追加する手順ガイド"
"url": "/ja/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides .NET を使用してプレゼンテーションに散布図を追加する: ステップバイステップガイド

## 導入
散布図を簡単に組み込んでプレゼンテーションの質を高めたいとお考えですか？Aspose.Slides for .NETを使えば、グラフの作成とカスタマイズが驚くほど簡単になります。このチュートリアルでは、Aspose.Slides for .NETを使ってスライドに散布図を追加する方法を解説します。これらのテクニックを習得すれば、データをより効果的に提示し、視覚的に魅力的なプレゼンテーションを作成できるようになります。

**学習内容:**
- プロジェクトに Aspose.Slides for .NET を設定する
- 新しいプレゼンテーションを作成し、最初のスライドにアクセスする
- 滑らかな線の散布図をスライドに追加する
- 既存のシリーズをクリアし、新しいシリーズをチャートに追加する
- データポイントとマーカースタイルを変更して視覚化を強化する
- プレゼンテーションを指定したディレクトリに保存する

まず前提条件を確認しましょう。

## 前提条件
Aspose.Slides for .NET を実装する前に、次のものを用意してください。
- **Aspose.Slides for .NET ライブラリ**バージョン23.7以降。
- **開発環境**Visual Studio 2019 以降と .NET Framework 4.6.1+ または .NET Core/5+。
- **C#の基礎知識**C# でのオブジェクト指向プログラミングに精通していること。

## Aspose.Slides for .NET のセットアップ
Aspose.Slides を使い始めるには、プロジェクトにライブラリをインストールする必要があります。手順は以下のとおりです。

**.NET CLI の使用:**
```bash
dotnet add package Aspose.Slides
```

**パッケージ マネージャー コンソールの使用:**
```powershell
Install-Package Aspose.Slides
```

**NuGet パッケージ マネージャー UI:**
- 「Aspose.Slides」を検索し、最新バージョンをインストールします。

### ライセンス取得
無料トライアルから始めるか、すべての機能を試すための一時ライセンスを申請してください。ご購入は以下の手順に従ってください。
1. 訪問 [Aspose.Slides を購入](https://purchase.aspose.com/buy) フルライセンスを購入します。
2. 一時ライセンスについては、 [一時ライセンスページ](https://purchase。aspose.com/temporary-license/).

ライセンス ファイルを取得したら、次のコマンドを使用してプロジェクトに追加します。
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## 実装ガイド
機能に基づいて実装を論理的なセクションに分割します。

### プレゼンテーションを作成してスライドを追加する
このセクションでは、プレゼンテーションを作成し、最初のスライドにアクセスする方法を説明します。

#### 概要
まず、 `Presentation` クラスはPowerPointファイルを表します。このオブジェクトモデルを使用すると、スライドへのアクセスは簡単です。

#### 実装手順
**ステップ1: プレゼンテーションの初期化**
```csharp
using Aspose.Slides;

// 新しいプレゼンテーションを作成する
t Presentation pres = new Presentation();
```
このコードは新しいプレゼンテーション ドキュメントを初期化します。

**ステップ2: 最初のスライドにアクセスする**
```csharp
// プレゼンテーションの最初のスライドにアクセスする
ISlide slide = pres.Slides[0];
```
ここ、 `pres.Slides[0]` 最初のスライドにアクセスします。 

### スライドに散布図を追加する
それでは、プレゼンテーションに散布図を追加してみましょう。

#### 概要
グラフを追加すると、プレゼンテーションでデータを視覚的に表現できます。Aspose.Slides を使えば、散布図をはじめとするさまざまな種類のグラフを簡単に組み込むことができます。

#### 実装手順
**ステップ1: 散布図を作成して追加する**
```csharp
using Aspose.Slides.Charts;

// 滑らかな線でデフォルトの散布図を作成して追加する
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
このスニペットは、指定された位置とサイズで散布図を追加します。

### チャートデータをクリアして系列を追加する
#### 概要
既存の系列を消去したり、新しい系列を追加したりして、チャートをカスタマイズする必要がある場合があります。このセクションでは、その機能について説明します。

#### 実装手順
**ステップ1: チャートデータワークブックにアクセスする**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// 既存のシリーズをクリアする
chart.ChartData.Series.Clear();
```
このコードは既存のデータをクリアして、新しいシリーズを最初から開始します。

**ステップ2: 新しいシリーズを追加する**
```csharp
// 「シリーズ1」という名前の新しいシリーズを追加します
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// 「シリーズ2」という名前の別のシリーズを追加します
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
これらの手順により、グラフに 2 つの新しいシリーズが追加されます。

### 最初のシリーズのデータポイントとマーカースタイルを変更する
#### 概要
データ ポイントとマーカー スタイルをカスタマイズして、散布図をより見やすく表示します。

#### 実装手順
**ステップ1: データポイントにアクセスして追加する**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// データポイント（1, 3）と（2, 10）を追加します。
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**ステップ2: マーカースタイルを変更する**
```csharp
// シリーズの種類を変更し、マーカーのスタイルを変更します
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### 第 2 シリーズのデータ ポイントとマーカー スタイルを変更する
#### 概要
同様に、プレゼンテーションのニーズに合わせて 2 番目のシリーズをカスタマイズします。

#### 実装手順
**ステップ1: 複数のデータポイントにアクセスして追加する**
```csharp
// 2番目のチャートシリーズにアクセスする
series = chart.ChartData.Series[1];

// 複数のデータポイントを追加する
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**ステップ2: マーカースタイルを変更する**
```csharp
// 2番目のシリーズのマーカーのサイズとシンボルを変更する
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### プレゼンテーションを保存
最後に、プレゼンテーションを指定されたディレクトリに保存します。

#### 実装手順
**ステップ1: ディレクトリを定義する**
出力ディレクトリが存在することを確認してください。存在しない場合は作成してください。
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// プレゼンテーションを保存する
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
このコードは、プレゼンテーション ファイルを指定された場所に保存します。

## 結論
Aspose.Slides for .NET を使用して、プレゼンテーションに散布図を追加することができました。ライブラリ内で利用可能な追加機能やカスタマイズを引き続き活用して、データ視覚化スキルをさらに向上させましょう。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}