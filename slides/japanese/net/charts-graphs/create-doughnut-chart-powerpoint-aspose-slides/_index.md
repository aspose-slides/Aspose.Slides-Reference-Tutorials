---
"date": "2025-04-15"
"description": "強力な Aspose.Slides for .NET ライブラリを使用して、PowerPoint プレゼンテーションで動的かつ視覚的に魅力的なドーナツ グラフを作成する方法を学びます。"
"title": "Aspose.Slides for .NET を使用して PowerPoint でドーナツ グラフを作成する方法"
"url": "/ja/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET を使用して PowerPoint でドーナツ グラフを作成する方法
視覚的に魅力的なグラフを作成することは、効果的なデータプレゼンテーションに不可欠です。ドーナツグラフは全体の一部を視覚的に表現するのに最適で、パーセンテージベースのデータビジュアライゼーションに最適です。このチュートリアルでは、強力なAspose.Slides for .NETライブラリを使用して、PowerPointでダイナミックなドーナツグラフを作成する方法を説明します。

## 導入
プレゼンテーションでは、複雑なデータセットを視覚的に表現することが求められることが多く、従来の棒グラフや折れ線グラフでは不十分な場合があります。ドーナツグラフは、パーセンテージベースのデータをスタイリッシュかつ明瞭に効果的に伝えるための万能ツールです。このチュートリアルでは、Aspose.Slides for .NET が PowerPoint 内でドーナツグラフを直接作成するプロセスを簡素化する方法を説明します。

**学習内容:**
- Aspose.Slides for .NET のセットアップ
- ドーナツグラフを作成する手順
- チャートにシリーズとカテゴリを追加する
- 明確さを高めるためのデータラベルの設定
- 最終プレゼンテーションを保存する

Aspose.Slides for .NET を活用して、カスタム ドーナツ グラフでプレゼンテーションを強化する方法について詳しく説明します。

## 前提条件
始める前に、以下のものが用意されていることを確認してください。
- **Aspose.Slides for .NET ライブラリ**NuGet または直接ダウンロードで入手できます。
- **開発環境**.NET プロジェクトには Visual Studio が推奨されます。
- C# の基本的な知識と PowerPoint の構造に関する知識。

## Aspose.Slides for .NET のセットアップ
グラフの作成を始めるには、まずプロジェクトにAspose.Slidesライブラリをセットアップする必要があります。インストール方法はいくつかあります。

**.NET CLI の使用:**

```bash
dotnet add package Aspose.Slides
```

**パッケージ マネージャー コンソールの使用:**

```powershell
Install-Package Aspose.Slides
```

**NuGet パッケージ マネージャー UI 経由:**
「Aspose.Slides」を検索し、最新バージョンをインストールします。

インストールが完了したら、プロジェクトの設定を開始できます。Aspose.Slidesを初めてご利用になる場合は、一時ライセンスまたは無料トライアルの取得をご検討ください。制限なくすべての機能をお試しください。

### プロジェクトを初期化する
アプリケーションで Aspose.Slides を初期化する方法は次のとおりです。

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // プレゼンテーションクラスのインスタンスを作成する
        Presentation presentation = new Presentation();
        
        // プレゼンテーションを操作するためのコードをここに記述します
        
        // プレゼンテーションを保存する
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## 実装ガイド
### ドーナツグラフを作成する
#### 概要
まず、PowerPointスライドに空のドーナツグラフを作成します。これは、データを追加したり、外観をカスタマイズしたりするための基盤となります。

**ステップ1: ドーナツグラフを追加する**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // 最初のスライドに、位置 (10, 10)、サイズ (500, 500) のドーナツ グラフを追加します。
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // 既存のシリーズとカテゴリをクリアする
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // 凡例を無効にして見た目をすっきりさせる
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**説明：**
- **チャートを追加**スライドに新しいドーナツ グラフを挿入します。
- **getChartDataWorkbook**: グラフ内のデータ セルにアクセスして操作できるようにします。

### シリーズとカテゴリの追加
#### 概要
次に、シリーズとカテゴリを追加して、グラフに意味のあるデータを入力します。

**ステップ2: データシリーズを追加する**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // シリーズを追加
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // ドーナツの穴と開始角度のカスタマイズ
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // カテゴリを追加する
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // データポイントの塗りつぶしと線の書式設定
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**説明：**
- **追加**グラフに新しいシリーズとカテゴリを挿入します。
- **ドーナツホールのサイズを設定する**ドーナツの穴のサイズを設定し、見た目の魅力を高めます。

### データラベルの構成
#### 概要
データラベルはグラフデータのコンテキストを提供します。カスタマイズして読みやすさを向上させましょう。

**ステップ3: データラベルをカスタマイズする**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // データラベルのカスタマイズ
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**説明：**
- **Iデータラベル**わかりやすく表示するためにデータ ラベルをカスタマイズします。
- **中央テキストの設定**、 **パーセンテージを表示**テキストを中央揃えにしてパーセンテージを表示することで、ラベルの読みやすさを向上させます。

## 結論
このガイドでは、Aspose.Slides for .NET を使用して PowerPoint で動的なドーナツグラフを作成する方法を学習しました。この強力なライブラリは幅広いカスタマイズに対応しており、プレゼンテーションのニーズに合わせてグラフを正確にカスタマイズできます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}