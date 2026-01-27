---
date: '2026-01-11'
description: Aspose Slides for Java の使い方を学び、チャートに画像マーカーを追加し、カスタムチャートビジュアル用に Aspose
  Slides の Maven 依存関係を設定します。
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: Aspose Slides Java の使い方 - チャートに画像マーカーを追加する
url: /ja/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Java の使い方: チャートに画像マーカーを追加する

## はじめに
視覚的に魅力的なプレゼンテーションを作成することは、効果的なコミュニケーションの鍵であり、チャートは複雑なデータを簡潔に伝える強力なツールです。**Aspose の使い方**でチャートを際立たせたいときは、カスタム画像マーカーが答えです。標準のマーカーは汎用的に見えることがありますが、Aspose.Slides for Java を使用すれば任意の画像に置き換えることができ、各データポイントを瞬時に認識できるようになります。

このチュートリアルでは、**Aspose Slides Maven 依存関係**の設定から画像の読み込み、データポイントへの適用まで、ラインチャートに画像マーカーを追加する全プロセスを順を追って説明します。最後までに、**マーカーの追加方法**や**チャートシリーズへの画像追加**に慣れ、すぐに実行できるコードサンプルを手に入れることができます。

**学べること**
- Aspose.Slides for Java のセットアップ方法（Maven/Gradle を含む）
- 基本的なプレゼンテーションとチャートの作成
- チャートのデータポイントに画像マーカーを追加
- 最適な可視化のためのマーカーサイズとスタイルの設定

チャートをさらに高める準備はできましたか？始める前に前提条件を確認しましょう！

### クイック回答
- **主な目的は何ですか？** チャートのデータポイントにカスタム画像マーカーを追加することです。  
- **必要なライブラリは？** Aspose.Slides for Java（Maven/Gradle）。  
- **ライセンスは必要ですか？** 評価には一時ライセンスで十分です。商用には正式ライセンスが必要です。  
- **サポートされている Java バージョンは？** JDK 16 以降。  
- **任意の画像形式を使用できますか？** はい、ファイルにアクセスできる限り PNG、JPEG、BMP などが使用可能です。

### 前提条件
1. **Aspose.Slides for Java ライブラリ** – Maven、Gradle、または直接ダウンロードで入手。  
2. **Java 開発環境** – JDK 16 以上がインストールされていること。  
3. **基本的な Java プログラミング知識** – Java の構文や概念に慣れていると役立ちます。

## Aspose Slides Maven 依存関係とは？

Maven 依存関係は、使用している Java バージョンに適したバイナリを取得します。`pom.xml` に追加することで、コンパイル時および実行時にライブラリが利用可能になります。

### Maven インストール
`pom.xml` ファイルに以下の依存関係を追加してください。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle インストール
`build.gradle` ファイルに以下の行を含めてください。

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接ダウンロード
あるいは、最新リリースを [Aspose.Slides for Java リリース](https://releases.aspose.com/slides/java/) からダウンロードしてください。

#### ライセンス取得手順
- **無料トライアル** – 機能を試すために一時ライセンスで開始。  
- **一時ライセンス** – テスト中に高度な機能を有効化。  
- **購入** – 商用プロジェクト向けに正式ライセンスを取得。

## 基本的な初期化と設定

まず、`Presentation` オブジェクトを作成します。このオブジェクトは PowerPoint ファイル全体を表し、チャートを保持します。

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## 実装ガイド

以下は、チャートに画像マーカーを追加する手順をステップバイステップで示したものです。各コードブロックには説明が付いており、各行が **なぜ** 必要かが分かります。

### 手順 1: 新しいプレゼンテーションとチャートの作成
最初のスライドにデフォルトマーカー付きのラインチャートを追加します。

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### 手順 2: チャートデータへのアクセスと設定
デフォルトの系列をクリアし、独自の系列を追加して、カスタムデータポイント用にワークシートを準備します。

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### 手順 3: チャートデータポイントに画像マーカーを追加
ここでは、画像を使用して **マーカーを追加する方法** を示します。プレースホルダーのパスを実際の画像の場所に置き換えてください。

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### 手順 4: マーカーサイズの設定とプレゼンテーションの保存
可視性を高めるためにマーカースタイルを調整し、最終的な PPTX ファイルを書き出します。

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## よくある問題とトラブルシューティング
- **FileNotFoundException** – 画像パス（`YOUR_DOCUMENT_DIRECTORY/...`）が正しく、ファイルが存在することを確認してください。  
- **LicenseException** – 本番環境で API を呼び出す前に、有効な Aspose ライセンスが設定されていることを確認してください。  
- **マーカーが表示されない** – `setMarkerSize` を増やすか、より高解像度の画像を使用して表示を改善してください。

## よくある質問

**Q: マーカーに JPEG の代わりに PNG 画像を使用できますか？**  
A: はい、Aspose.Slides がサポートする任意の画像形式（PNG、JPEG、BMP、GIF）をマーカーとして使用できます。

**Q: Maven/Gradle パッケージにライセンスは必要ですか？**  
A: 開発・テストには一時ライセンスで十分ですが、商用配布には正式ライセンスが必要です。

**Q: 同じ系列の各データポイントに異なる画像を追加できますか？**  
A: もちろんです。`AddImageMarkers` の例では 2 つの画像を交互に使用していますが、各ポイントに固有の画像をロードすることも可能です。

**Q: `aspose slides maven dependency` はプロジェクトのサイズにどのように影響しますか？**  
A: Maven パッケージは選択した JDK バージョンに必要なバイナリのみを含むため、フットプリントは適切に抑えられます。サイズが問題の場合は **no‑dependencies** バージョンも使用できます。

**Q: サポートされている Java バージョンは何ですか？**  
A: Aspose.Slides for Java は JDK 8 から JDK 21 をサポートしています。例は JDK 16 を使用していますが、必要に応じて classifier を調整できます。

## 結論
このガイドに従うことで、**Aspose の使い方**としてカスタム画像マーカーでチャートを強化する方法、**Aspose Slides Maven 依存関係**の設定方法、そして **チャートシリーズに画像を追加**する方法を習得し、洗練されたプロフェッショナルな外観を実現できます。さまざまなアイコン、サイズ、チャートタイプを試して、真に際立つプレゼンテーションを作成してください。

**最終更新日:** 2026-01-11  
**テスト環境:** Aspose.Slides for Java 25.4 (jdk16)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}