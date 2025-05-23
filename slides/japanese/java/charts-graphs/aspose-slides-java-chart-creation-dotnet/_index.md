---
"date": "2025-04-17"
"description": "Aspose.Slides for Java を使用して、.NET プレゼンテーションでグラフを作成およびカスタマイズする方法を学びます。このステップバイステップガイドに従って、プレゼンテーションのデータの視覚化を強化しましょう。"
"title": "Aspose.Slides for Java .NET プレゼンテーションでのグラフ作成"
"url": "/ja/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java を使用して .NET プレゼンテーションでグラフを作成する
## 導入
魅力的なプレゼンテーションを作成するには、多くの場合、グラフなどの視覚的なデータ表現を組み込むことで、視聴者の理解とエンゲージメントを高める必要があります。Aspose.Slides for Javaを使用して、.NETプレゼンテーションに動的でカスタマイズ可能なグラフを追加したい開発者の方のために、このチュートリアルをご用意しました。プレゼンテーションの初期化、さまざまな種類のグラフの追加、グラフデータの管理、そして系列データの効果的な書式設定の方法について詳しく説明します。
**学習内容:**
- .NET 環境で Aspose.Slides for Java をセットアップして使用する方法。
- Aspose.Slides を使用して新しいプレゼンテーションを初期化します。
- スライドにグラフを追加してカスタマイズします。
- グラフ データ ワークブックを管理します。
- 系列データの書式設定、特に負の値の処理。
前提条件のセクションに移行すると、簡単に実行できるようになります。
## 前提条件
Aspose.Slides for Java を使用してグラフを作成する前に、必要なものを概説しましょう。
### 必要なライブラリとバージョン
次の依存関係があることを確認してください。
- **Aspose.Slides for Java**: バージョン25.4以降。
### 環境設定要件
- .NET アプリケーションをサポートする開発環境。
- Java プログラミング概念の基本的な理解。
### 知識の前提条件
- .NET アプリケーション コンテキストでプレゼンテーションを作成する知識。
- Java の依存関係とその管理 (Maven/Gradle) を理解する。
## Aspose.Slides for Java のセットアップ
Aspose.Slides を使い始めるには、プロジェクトに依存関係として追加する必要があります。手順は以下のとおりです。
### メイヴン
次の依存関係を `pom.xml` ファイル：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### グラドル
これをあなたの `build.gradle` ファイル：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### 直接ダウンロード
または、最新バージョンを以下からダウンロードすることもできます。 [Aspose.Slides for Java リリース](https://releases。aspose.com/slides/java/).
#### ライセンス取得手順
- **無料トライアル**一時ライセンスから始めて、機能を調べてみましょう。
- **購入**広範囲に使用する場合はライセンスの購入を検討してください。
#### 基本的な初期化とセットアップ
コード内で Aspose.Slides を初期化する方法は次のとおりです。
```java
import com.aspose.slides.Presentation;
// 新しいプレゼンテーションオブジェクトを初期化する
Presentation pres = new Presentation();
try {
    // ここでのあなたの論理は...
} finally {
    if (pres != null) pres.dispose();
}
```
この設定により、リソース管理が効率的に処理されます。
## 実装ガイド
機能の実装方法を段階的に説明します。
### プレゼンテーションの初期化
**概要：**
プレゼンテーションインスタンスを作成すると、その後のすべての操作の基盤が整います。この機能では、Aspose.Slides を使ってゼロから始める方法を説明します。
#### ステップ1: 必要なパッケージをインポートする
```java
import com.aspose.slides.Presentation;
```
#### ステップ2: 新しいプレゼンテーションオブジェクトを作成する
やり方は次のとおりです:
```java
Presentation pres = new Presentation();
try {
    // ここにコードロジックを記述します...
} finally {
    if (pres != null) pres.dispose(); // リソースが解放されることを保証する
}
```
*これにより、プレゼンテーション オブジェクトが使用後に適切に破棄され、メモリ リークが防止されます。*
### スライドにグラフを追加する
**概要：**
スライドにグラフを追加すると、データの視覚化がより効果的かつ魅力的になります。
#### ステップ1: 必要なパッケージをインポートする
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```
#### ステップ2: プレゼンテーションを初期化し、グラフを追加する
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // チャートのカスタマイズのための追加ロジック...
} finally {
    if (pres != null) pres.dispose();
}
```
*ここでは、指定した座標と寸法で最初のスライドに集合縦棒グラフを追加します。*
### チャートデータ管理ワークブック
**概要：**
グラフのデータ ワークブックを効率的に管理することで、シリーズやカテゴリをシームレスに操作できるようになります。
#### ステップ1: 必要なパッケージをインポートする
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```
#### ステップ2: データワークブックにアクセスしてクリアする
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // 既存のデータを消去
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // カスタマイズ ロジックをここに記述します...
} finally {
    if (pres != null) pres.dispose();
}
```
*新しいシリーズやカテゴリを追加するときに、白紙の状態から始めるには、ワークブックをクリアすることが重要です。*
### チャートにシリーズとカテゴリを追加する
**概要：**
この機能では、シリーズとカテゴリを管理することで、意味のあるデータ ポイントを追加する方法を示します。
#### ステップ1: シリーズとカテゴリを追加する
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // 既存のシリーズとカテゴリをクリアする
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // 新しいシリーズとカテゴリを追加する
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // さらにカスタマイズロジック...
} finally {
    if (pres != null) pres.dispose();
}
```
*シリーズとカテゴリを追加すると、より整理されたデータの表示が可能になります。*
### シリーズデータの入力と書式設定
**概要：**
グラフにデータ ポイントを入力し、外観をフォーマットして読みやすさを向上させます (特に負の値を扱う場合)。
#### ステップ1: シリーズデータを入力する
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // シリーズとカテゴリを追加する（以前のロジックを再利用）
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // 負の値の系列をフォーマットする
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // プレゼンテーションを保存する
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*このセクションでは、データを入力し、色の書式設定を適用して視覚化を改善する方法を説明します。*

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}