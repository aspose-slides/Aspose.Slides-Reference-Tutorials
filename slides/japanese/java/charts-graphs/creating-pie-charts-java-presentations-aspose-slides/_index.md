---
date: '2026-08-01'
description: Aspose Slides ライセンスの使用方法を学び、Java プレゼンテーションで pie charts を作成およびカスタマイズします。ステップバイステップの手順に従って、pie
  chart データを設定し、chart slides を効率的に追加します。
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Aspose Slides ライセンスの使用方法を学び、Java プレゼンテーションで pie charts を作成およびカスタマイズします。ステップバイステップの手順に従って、pie
  chart データを設定し、chart slides を効率的に追加します。
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Aspose Slides ライセンスを使用して Java で pie charts を作成
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Aspose Slides ライセンスを使用して Java で pie charts を作成
url: /ja/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides を使用した Java プレゼンテーションで円グラフを作成する方法

## はじめに

プロフェッショナルな見た目のプレゼンテーションを作成する必要がある場合、**Aspose Slides ライセンス**を使用すると、プログラムでチャートを生成およびスタイル設定する機能が得られます。このガイドでは、円グラフの作成方法、データの設定方法、そしてそれを Java のスライドデッキに埋め込む方法を学びます—Microsoft PowerPoint に依存せずに。セットアップ、コードの流れ、ベストプラクティスのヒントを順に説明し、数分で洗練されたビジュアルレポートを提供できるようにします。

**学べること:**
- 有効なライセンスを使用した Aspose.Slides for Java の設定
- 円グラフの作成とカスタマイズ手順
- 円グラフのデータ設定方法とチャートスライドの追加方法
- 一般的な落とし穴とパフォーマンスのコツ

環境が整っていることを確認しましょう。

## クイック回答
- **Aspose Slides ライセンスで何ができるか？** フル機能のチャート作成、PDF/HTML へのエクスポート、ウォーターマークの除去が可能です。
- **必要な Java バージョンは？** JDK 16 以上。
- **Maven または Gradle が必要ですか？** どちらでも動作します。ライブラリは両方で利用可能です。
- **円グラフは何件のデータポイントを保持できますか？** メモリ問題なく最大 10 000 件まで。
- **スライドを画像としてエクスポートできますか？** はい – PNG、JPEG、SVG などがサポートされています。

## 前提条件

開始する前に、以下が揃っていることを確認してください：

- **必要なライブラリ:** Aspose.Slides for Java（バージョン 25.4 以降）—このバージョンは最新のファイル形式とパフォーマンス最適化をサポートします。
- **環境設定:** JDK 16 以上がインストールされ、IDE またはビルドシステムで設定されていること。
- **基本知識:** Java、Maven または Gradle、オブジェクト指向プログラミングの概念に慣れていること。

## Aspose.Slides for Java の設定

Aspose.Slides for Java を使用するには、プロジェクトに追加します。以下は、最も一般的なビルドツールで依存関係を追加する方法です：

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**直接ダウンロード:** 最新の JAR は [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) からダウンロードできます。

### ライセンス取得

Aspose はすべての機能を解放する無料トライアルを提供していますが、評価用ウォーターマークを除去し、パフォーマンス向上を得るためには **有効な Aspose Slides ライセンス** が本番使用に必要です。購入オプションは [purchase page](https://purchase.aspose.com/buy) に掲載されています。ライセンスファイルを取得したら、アプリケーション起動時に一度ロードします：

`License` loads and applies your Aspose.Slides license.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## 実装ガイド

### プレゼンテーションに円グラフを作成・追加

#### 概要
このセクションでは、円グラフの作成方法、データ系列の設定方法、スライドへの埋め込み方法を説明します。プレゼンテーションオブジェクトの初期化から最終ファイルの保存までの全体フローが確認できます。

#### 手順 1: プレゼンテーションの初期化  
`Presentation` は Aspose.Slides のトップレベルオブジェクトで、メモリ内の PowerPoint ファイルを表します。インスタンスを作成すると、変更可能な空のスライドデッキが得られます。

```java
demo.Presentation pres = new demo.Presentation();
```  
この行は新しいプレゼンテーションを作成し、以降のすべての変更が適用されます。

#### 手順 2: スライドに円グラフを追加  
`Chart` はチャートオブジェクト（円グラフを含む）をカプセル化するクラスです。スライドにチャートを追加するには、位置とサイズを指定する単一のメソッド呼び出しを行います。

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` と `yPosition` はチャートの左上隅を設定します。  
- `width` と `height` はスライド上のチャートの表示領域を定義します。

#### 手順 3: 円グラフデータの設定  
`ChartData` はチャートのデータ系列を保持します。  
**円グラフのデータはどう設定しますか？**  
まず簡潔に答えてください: `ChartData` コレクションに系列を追加し、`ChartDataPoint` オブジェクトに数値とカテゴリ名を設定します。この方法により、最大 10 000 スライスを表示しつつラベルの書式を保持できます。データ設定後、色、凡例、データラベルを企業のスタイルガイドに合わせてカスタマイズできます。

以下のコードは 2 つのカテゴリを追加し、ラベルを表示します：

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
このスニペットはデータ系列を作成し、2 つのポイントを挿入し、チャートにカテゴリラベルを有効にします。

#### 手順 4: プレゼンテーションの保存  
最後に、プレゼンテーションを任意のファイル形式（PPTX、PDF、または PNG）で保存します。`save` メソッドは有効なライセンスを考慮し、トライアルのウォーターマークが表示されないようにします。

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### よくある問題と解決策
- **ライセンスが見つからないエラー:** ライセンスファイルのパスが正しいこと、`License` オブジェクトが Aspose.Slides の呼び出し前にインスタンス化されていることを確認してください。
- **空のチャート:** `ChartData` 系列に少なくとも 1 つの `ChartDataPoint` が含まれていることを確認してください。系列が空だとチャート領域が空白になります。
- **大規模データセットでのパフォーマンス低下:** `presentation.getSlides().removeAt(index)` で未使用スライドを削除し、重い処理後に `System.gc()` を呼び出してください。

## 実用例
1. **ビジネスレポート:** 単一の円グラフで地域別の市場シェアや収益分布を可視化します。
2. **学術プレゼンテーション:** アンケート結果や実験結果を分かりやすく提示します。
3. **プロジェクトダッシュボード:** タスク完了率やリソース配分をスライド上で即座に表現します。

Aspose.Slides と JDBC を組み合わせてデータベースからリアルタイムデータを取得し、週次のエグゼクティブブリーフィング用に最新のチャートを生成することもできます。

## パフォーマンス上の考慮点
高解像度画像や大規模データセットを多数含むプレゼンテーションを扱う際は：

- `try‑with‑resources` または明示的な `dispose()` 呼び出しでオブジェクトを速やかに解放します。
- スライドリソースの遅延ロードを有効にしてメモリ使用量を抑えます。
- バッチ処理では、可能な限り単一の `Presentation` インスタンスを再利用し、JVM のオーバーヘッドを削減します。

## 結論
これで、**Aspose Slides ライセンス**を使用して Java で円グラフを作成するための完全な本番対応ワークフローが手に入りました。棒グラフ、折れ線グラフ、ドーナツグラフなどの追加チャートタイプを試して、スライドをさらに充実させてください。次に、API のエクスポート機能を活用し、PDF レポートや PNG 画像を自動生成してみましょう。

## よくある質問

**Q: 1 つのスライドに複数のチャートを追加するには？**  
A: 各チャートに対して `slide.getShapes().addChart()` を呼び出し、インスタンスごとに固有の座標とサイズを指定します。

**Q: Aspose.Slides for Java の代替はありますか？**  
A: Apache POI と JFreeChart が一般的な代替ですが、包括的なエクスポートオプションやライセンスモデルは Aspose には及びません。

**Q: Aspose.Slides を使ってプレゼンテーションを他の形式に変換できますか？**  
A: はい—単一の `save` 呼び出しで PDF、XPS、HTML、PNG、JPEG、SVG などにエクスポートできます。

**Q: 大規模開発チーム向けのライセンスはどう扱うべきですか？**  
A: 複数の開発者とサーバーをカバーするエンタープライズライセンスを購入してください。ボリュームディスカウントは Aspose の営業にお問い合わせください。

**Q: チャートデータが頻繁に更新される場合は？**  
A: Aspose.Slides をデータソース（例: SQL クエリ）と統合し、実行時にチャートを再構築します。API は動的データバインディングをサポートしています。

## リソース
- **ドキュメント:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)
- **ダウンロード:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **購入:** [Buy a License](https://purchase.aspose.com/buy)
- **無料トライアル:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **一時ライセンス:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)
- **サポート:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**最終更新日:** 2026-08-01  
**テスト環境:** Aspose.Slides for Java 25.4  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Slides for Java を使用したプレゼンテーションへのチャート追加と設定方法](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Aspose.Slides を使用した Java プレゼンテーションでのチャート作成とカスタマイズ](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [Aspose.Slides Java でプレゼンテーションを作成・設定する方法：ステップバイステップガイド](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}