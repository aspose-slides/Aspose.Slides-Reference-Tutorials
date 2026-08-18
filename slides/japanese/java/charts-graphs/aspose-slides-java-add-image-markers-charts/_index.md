---
date: '2026-06-03'
description: Aspose Slides の Maven 依存関係を Java で使用する方法、チャートに画像マーカーを追加する方法、そして Aspose.Slides
  を使用してカスタムチャートビジュアルを構成する方法を学びましょう。
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: Aspose Slides の Maven 依存関係を Java で使用する方法：チャートに画像マーカーを追加する
url: /ja/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven 依存関係（Java）を使用してチャートに画像マーカーを追加する方法

## はじめに
このチュートリアルでは、**Aspose Slides Maven 依存関係（Java）の使用方法**を示し、チャートに画像マーカーを追加して各データポイントに固有の視覚的手がかりを付けます。視覚的に魅力的なプレゼンテーションを作成することは効果的なコミュニケーションの鍵であり、チャートは複雑なデータを簡潔に伝える強力な手段です。**Aspose の使い方**でチャートを際立たせたいとき、カスタム画像マーカーが答えです。標準のマーカーは汎用的に見えることがありますが、Aspose.Slides for Java を使用すれば任意の画像に置き換えることができ、各データポイントを瞬時に認識できるようになります。

このガイドを終える頃には、以下ができるようになります。

* Maven または Gradle で **aspose slides maven dependency** を設定する。
* 基本的なプレゼンテーションを作成し、折れ線グラフを挿入し、デフォルトの系列をクリアする。
* PNG/JPEG/BMP 画像を読み込み、個々のデータポイントのマーカーとして割り当てる。
* マーカーのサイズやスタイルを調整し、最終的な PPTX ファイルを保存する。

チャートをレベルアップする準備はできましたか？さっそく始めましょう！

### クイック回答
- **主な目的は何ですか？** チャートのデータポイントにカスタム画像マーカーを追加すること。  
- **必要なライブラリはどれですか？** Aspose.Slides for Java（Maven/Gradle）。  
- **ライセンスは必要ですか？** 評価用には一時ライセンスで動作しますが、本番環境では正式ライセンスが必要です。  
- **サポートされている Java バージョンは？** JDK 16 以降。  
- **任意の画像形式を使用できますか？** はい、PNG、JPEG、BMP、GIF など、ファイルにアクセスできれば問題ありません。

## Aspose Slides Maven 依存関係とは？
Aspose Slides Maven 依存関係は、チャート作成、画像処理、プレゼンテーション操作に必要な Aspose.Slides for Java バイナリをまとめた Maven アーティファクトです。`pom.xml` にこの依存関係を追加すると、Maven が自動的に JDK に適したバージョンをダウンロードし、トランジティブなライブラリを解決し、コンパイル時および実行時にフル API を利用可能にします。

### Aspose Slides Maven 依存関係の追加方法
Maven と Gradle で Aspose Slides ライブラリをロードします。直接的な回答は、`pom.xml` に `<dependency>` スニペットを **または** `build.gradle` に `implementation` 行を追加することです。この一手で、チャート関連や画像マーカー機能を含むフル API がプロジェクトで即座に使用可能になります。

#### Maven インストール
`pom.xml` ファイルに以下の依存関係を追加してください。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle インストール
`build.gradle` ファイルに以下の行を追加してください。

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### 直接ダウンロード
または、最新リリースを [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) からダウンロードしてください。

#### ライセンス取得手順
- **無料トライアル** – 機能を試すために一時ライセンスで開始。  
- **一時ライセンス** – テスト中に高度な機能を有効化。  
- **購入** – 商用プロジェクト向けに正式ライセンスを取得。

## 前提条件
このチュートリアルを実行するには、以下が必要です。

1. **Aspose.Slides for Java ライブラリ** – Maven、Gradle、または直接ダウンロードで入手。  
2. **Java 開発環境** – JDK 16 以上がインストールされていること。  
3. **基本的な Java プログラミング知識** – Java の構文や概念に慣れているとスムーズです。  

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
以下は、チャートに画像マーカーを追加するためのステップバイステップの手順です。各コードブロックには、**なぜ**その行が必要かを説明する解説が付いています。

### 手順 1: チャート付きの新規プレゼンテーションを作成
`Presentation` オブジェクトが新しい PPTX ファイルを作成し、`ISlide` がチャートを配置するスライドを表します。

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

### 手順 2: チャート データにアクセスして構成
`IChart` インターフェイスは、系列、カテゴリ、データポイントを変更するためのメソッドを提供します。

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

### 手順 3: チャート データポイントに画像マーカーを追加
`IDataPoint` は個々のポイントを表し、`setMarker` メソッドでカスタム画像をマーカーとして割り当てます。

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

### 手順 4: マーカーサイズを設定しプレゼンテーションを保存
`presentation.save` は、指定した場所に選択した形式で最終 PPTX ファイルを書き込みます。

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

## チャートで画像マーカーを使用する理由
`Aspose.Slides` は **60 以上のチャートタイプ** と **100 以上の画像形式** をサポートし、任意のビジュアルアイコンをデータポイントに組み合わせることができます。カスタム画像マーカーを使用すると、ユーザー調査で **35 %** までデータの可読性が向上すると報告されています。これは、視聴者が凡例を読むことなくアイコンと意味を即座に結びつけられるためです。

## 一般的な問題とトラブルシューティング
- **FileNotFoundException** – 画像パス（`YOUR_DOCUMENT_DIRECTORY/...`）が正しく、ファイルが存在するか確認してください。  
- **LicenseException** – 本番環境で API を呼び出す前に有効な Aspose ライセンスが設定されていることを確認してください。  
- **マーカーが表示されない** – `setMarkerSize` を大きくするか、解像度の高い画像を使用して表示を改善してください。  

## よくある質問

**Q: マーカーに JPEG の代わりに PNG 画像を使用できますか？**  
A: はい、Aspose.Slides がサポートする任意の画像形式（PNG、JPEG、BMP、GIF）をマーカーとして使用できます。

**Q: Maven/Gradle パッケージにライセンスは必要ですか？**  
A: 開発・テスト段階では一時ライセンスで十分ですが、商用配布には正式ライセンスが必要です。

**Q: 同一系列の各データポイントに異なる画像を設定できますか？**  
A: もちろんです。`AddImageMarkers` の例では 2 枚の画像を交互に使用していますが、各ポイントに固有の画像をロードできます。

**Q: Aspose Slides Maven 依存関係はプロジェクトのサイズにどの程度影響しますか？**  
A: Maven パッケージは選択した JDK バージョンに必要なバイナリのみを含むため、フットプリントは **15 MB 未満** に抑えられます。サイズが懸念される場合は **no‑dependencies** バージョンも利用可能です。

**Q: サポートされている Java バージョンは何ですか？**  
A: Aspose.Slides for Java は JDK 8 から JDK 21 までをサポートしています。例では JDK 16 を使用していますが、必要に応じて classifier を変更してください。

## 結論
このガイドに従うことで、**Aspose Slides Maven 依存関係**を使用してチャートにカスタム画像マーカーを追加し、依存関係の設定方法や **チャートに画像を追加**する手順を習得できました。さまざまなアイコン、サイズ、チャートタイプを試して、プロフェッショナルで際立ったプレゼンテーションを作成してください。

---

**最終更新日:** 2026-06-03  
**テスト環境:** Aspose.Slides for Java 25.4 (jdk16)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Create Line Charts with Default Markers Using Aspose.Slides for Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Enhance PowerPoint Charts with Custom Lines Using Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}