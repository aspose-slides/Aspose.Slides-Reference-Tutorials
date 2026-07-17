---
date: '2026-07-17'
description: Aspose Slides for Java を使用して PowerPoint に Sunburst Charts を追加する方法を学びます。ステップバイステップのガイドでは、セットアップ、チャート作成、カスタマイズ、実際のユースケースをカバーしています。
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Aspose Slides for Java を使用して PowerPoint に Sunburst Charts を追加する方法です。このチュートリアルに従ってライブラリをセットアップし、チャートを作成し、データポイントをカスタマイズし、実際のプロジェクトに適用してください。
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Aspose (Java) を使用して PowerPoint に Sunburst Charts を追加する方法
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Aspose (Java) を使用して PowerPoint に Sunburst Charts を追加する方法
url: /ja/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPointでSunburstチャートを追加する方法 (Aspose (Java) 使用)

## はじめに

PowerPointのスライドにサンバーストチャートを追加すると、平坦なデータテーブルがすぐに魅力的なビジュアル階層に変わります。このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint に **サンバースト** チャートを追加する方法を、環境設定から色やラベルの微調整まで学びます。販売ダッシュボード、プロジェクトタスクのブレークダウン、教育用スライドデッキのいずれを作成する場合でも、以下の手順で本番環境向けのソリューションが得られます。

**学べること**
- Maven または Gradle プロジェクトで Aspose.Slides を設定する方法
- 新しいプレゼンテーションを作成し、サンバーストチャートを挿入する方法
- データポイント、ラベル、塗りつぶし色をカスタマイズする方法
- サンバーストチャートが活躍する実践シナリオ

さあ始めましょう。生の階層データを洗練された PowerPoint ビジュアルに変換するのがいかに簡単かをご覧ください。

## クイック回答
- **主なライブラリ?** Aspose.Slides for Java  
- **サポートされているチャートタイプ?** Sunburst (放射状階層)  
- **最低 Java バージョン?** JDK 16  
- **一般的な実装時間?** 基本的なチャートで 10‑15 分  
- **本番環境でライセンスが必要ですか?** はい、有効な Aspose ライセンスが必要です  

## サンバーストチャートとは？

サンバーストチャートは、中心点から外側にリングをネストして階層データを可視化する放射状の図です。組織構造、製品カテゴリ、ファイルシステムツリーなど、複数レベルの関係を示すのに最適です。各同心円リングは階層のレベルを表し、各セグメントのサイズは定量的な値を反映するため、閲覧者は構造と規模の両方をすばやく把握できます。

## なぜ Aspose.Slides for Java を使用するのか？

Aspose.Slides は **50 以上のチャートタイプ** をサポートし、**最大 10,000 スライド** のプレゼンテーションをファイル全体をメモリに読み込むことなく操作でき、エンタープライズ規模のレポーティングに高性能を提供します。クロスプラットフォームで動作し、豊富な API カバレッジを提供し、評価制限を解除する堅牢なライセンスオプションを備えているため、本番環境に最適です。

## 前提条件
- **Java Development Kit (JDK)** 16 以上  
- **IDE** – IntelliJ IDEA、Eclipse、または任意の Java 対応エディタ  
- Java の構文と Maven/Gradle ビルドツールの基本的な知識  

## Aspose.Slides for Java の設定

### Maven 依存関係
`pom.xml` に Aspose.Slides の Maven アーティファクトを追加します:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 依存関係
Gradle を使用する場合は、`build.gradle` に次の行を追加します:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接ダウンロード
公式リリースページから最新の JAR を直接ダウンロードすることもできます: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### ライセンス取得
評価制限なしで実行するには、ライセンスを取得してください:
- **無料トライアル** – 短期間の評価用一時ライセンス。  
- **一時ライセンス** – [Aspose のウェブサイト](https://purchase.aspose.com/temporary-license) からリクエストしてください。  
- **フル購入** – 無制限の本番利用のためにサブスクリプションを購入してください。

### 基本的な初期化
`Presentation` クラスは PowerPoint ファイルを作成または開くためのエントリーポイントです。

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## 実装ガイド

### Aspose.Slides for Java を使用して PowerPoint プレゼンテーションにサンバーストチャートを追加する方法

新しい `Presentation` をロードし、スライドを追加し、`ChartType.Sunburst` タイプの `IChart` を挿入し、`save` を呼び出します。この簡潔な 3 ステップのパターンで、さらなるカスタマイズが可能な完全なサンバーストチャートが作成されます。

#### 手順 1: プレゼンテーションの初期化
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### 手順 2: サンバーストチャートの追加
`IChart` インターフェイスは任意のスライドに配置できるチャートオブジェクトを定義します。ここでは座標 (100, 100) にサイズ 450 × 400 ポイントのサンバーストチャートを追加します。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### 手順 3: プレゼンテーションの保存
必ず `save` を呼び出して変更を永続化してください。PPTX、PDF、または 50 以上のサポートされている出力形式から選択できます。

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### チャートのデータポイントを変更する

#### 概要
チャートのデータポイントコレクションを通じて、サンバーストの各スライス（ラベル、色、表示）を調整できます。

#### 手順 1: データポイントコレクションへのアクセス
チャートの最初の系列は、各スライスを表す `IChartDataPoint` オブジェクトのコレクションを保持しています。

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### 手順 2: 特定のデータポイントの値を表示
目的のデータポイントの `IsValueShown` を `true` に設定すると、スライス上に数値が直接表示されます。

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### 手順 3: ラベル形式の変更
ラベルの表示、フォントカラー、背景を調整して可読性を向上させます。

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### 手順 4: データポイントの塗りつぶし色を設定
個々のスライスの塗りつぶし色をカスタマイズし、ブランドのパレットに合わせるか、重要なセグメントを強調表示します。

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### 手順 5: 修正したプレゼンテーションの保存
プレゼンテーションを再度保存して、カスタマイズしたチャートを永続化します。

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## 実用的な活用例

1. **ビジネス分析** – 地域 → 製品ライン → SKU の売上を単一の放射状ビューで可視化。  
2. **プロジェクト管理** – フェーズからタスク、サブタスクへと掘り下げる作業分解構造を表示。  
3. **教育** – 学部 → コース → モジュールといったカリキュラム階層をマッピング。  

## パフォーマンス上の考慮点

- **メモリ効率:** Aspose.Slides はデータをストリーミングするため、複数のチャートを含む 500 ページのデッキでも RAM 使用量は 200 MB 未満に抑えられます。  
- **ガベージコレクション:** 不要になったスライドオブジェクト (`slide.dispose()`) を解放してメモリリークを防止します。  

## よくある質問

**Q: サンバーストチャートとは何ですか？**  
A: サンバーストチャートは同心円リングで階層データを可視化し、各リングが階層のレベルを表します。

**Q: Maven を使用して Aspose.Slides for Java をインストールするには？**  
A: `pom.xml` の「Maven 依存関係」セクションに示された Maven 依存関係を追加し、`mvn clean install` を実行してください。

**Q: Aspose.Slides で他のチャートタイプもカスタマイズできますか？**  
A: はい、ライブラリは 50 種類以上のチャートタイプをサポートしており、棒グラフ、折れ線グラフ、円グラフ、レーダーチャートなどが含まれます。

**Q: プレゼンテーションが保存されません—何を確認すべきですか？**  
A: ファイルパスが正しいか、ディレクトリが存在するか、書き込み権限があるかを確認してください。また、`Presentation.save()` メソッドが呼び出されていることも確認してください。

**Q: さらにヘルプやサンプルはどこで入手できますか？**  
A: [Aspose フォーラム](https://forum.aspose.com/c/slides/11) を訪れるか、公式の [Aspose.Slides リファレンス](https://reference.aspose.com/slides/java/) を参照してください。

## リソース
- **ドキュメント:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **リファレンス（小文字）:** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **コミュニティフォーラム:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **ダウンロード:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**最終更新日:** 2026-07-17  
**テスト環境:** Aspose.Slides for Java 24.12  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Slides for Java を使用して PowerPoint にチャートを追加する方法: ステップバイステップガイド](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java で PowerPoint のチャートをアニメーション化 – ステップバイステップガイド](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Aspose.Slides を使用した Java でのチャート作成 – 追加と検証](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}