---
date: '2026-07-27'
description: Aspose.Slides を使用して doughnut chart java を作成する方法を学びます – ライブラリのセットアップ、カスタマイズ可能な
  doughnut chart の追加、hole size の調整、プレゼンテーションの保存までのクイックガイドです。
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Aspose.Slides を使用して doughnut chart java を作成する方法を学びます – ライブラリのセットアップ、カスタマイズ可能な
  doughnut chart の追加、hole size の調整、プレゼンテーションの保存までのクイックガイドです。
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Create Doughnut Chart Java – Aspose.Slides を使用したステップバイステップ
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Create Doughnut Chart Java – Aspose.Slides を使用したステップバイステップ
url: /ja/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java と Aspose.Slides for Presentations を使用したドーナツ グラフの作成方法

## はじめに
視覚的に魅力的なプレゼンテーションを作成することは、情報を効果的に伝えるために不可欠です。**Create doughnut chart java** は、比例データをモダンな外観で示す必要がある場合によくある要件です。このチュートリアルでは、Aspose.Slides for Java のセットアップ方法、ドーナツ グラフの作成、穴のサイズや色のカスタマイズ、そして最終的にプレゼンテーション ファイルを保存する方法を学びます。最後までで、PowerPoint デッキを自動生成する任意の Java プロジェクトに組み込める再利用可能なパターンが手に入ります。

**学習内容:**
- Aspose.Slides for Java のセットアップ
- プレゼンテーションでのドーナツ グラフの作成と構成
- 穴のサイズなど、チャートの美観の調整
- 新しいチャートを含むプレゼンテーションの保存

環境設定から始めましょう！

## クイック回答
- **どのライブラリが doughnut chart java を作成しますか？** Aspose.Slides for Java.  
- **基本的なドーナツ グラフに必要なコード行数は？** プレゼンテーションをインスタンス化した後、約 8〜10 行です。  
- **穴のサイズを変更できますか？** はい、`setHoleSize(double)` メソッドは 0 % から 100 % の値を受け取ります。  
- **サポートされている出力形式は？** PPTX、PDF、XPS、PNG、JPEG など多数（合計 50 以上）。  
- **本番環境でライセンスが必要ですか？** 無制限に使用するには商用ライセンスが必要です。評価目的は無料トライアルで利用可能です。

## Aspose.Slides for Java とは？
**Aspose.Slides for Java** は、Microsoft Office を使用せずに PowerPoint ファイルの作成、変更、変換、レンダリングを可能にする完全に管理された API です。50 以上のファイル形式をサポートし、メモリ使用量を抑えながら数千枚のスライドを含むプレゼンテーションを処理できます。

## プレゼンテーションでドーナツ グラフを使用する理由は？
ドーナツ グラフは、全体に対する部分の関係を示しながら、中心部にラベルや画像を配置するスペースを確保します。Aspose.Slides は、一般的な 2.5 GHz サーバー上で **1 分間に最大 500 スライド** のドーナツ グラフをレンダリングでき、**数百ページに及ぶプレゼンテーション** をファイル全体をメモリに読み込むことなく処理するため、大規模なレポート ソリューションに最適です。

## 前提条件
開始する前に、以下の前提条件を満たしていることを確認してください。

### 必要なライブラリとバージョン
Aspose.Slides for Java を使用するには、Maven または Gradle 経由でプロジェクトに組み込むか、直接ダウンロードしてください。

#### 環境設定要件
- 動作する Java Development Kit (JDK)、できればバージョン 8 以上  
- IntelliJ IDEA や Eclipse などの統合開発環境 (IDE)

### 知識の前提条件
Java と基本的なプログラミング概念に慣れていると役立ちます。Maven または Gradle の基本的な知識があれば、セットアッププロセスがスムーズになります。

## Aspose.Slides for Java の設定
Aspose.Slides をプロジェクトに組み込む方法はいくつかあります。

**Maven:**  
`pom.xml` ファイルに次の依存関係を追加します:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
`build.gradle` ファイルに次を含めます:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
あるいは、最新バージョンを [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) からダウンロードしてください。

### ライセンス取得
- **Free Trial:** Aspose.Slides の機能を試すために、まずトライアル版をダウンロードしてください。  
- **Temporary License:** 制限なしで拡張機能を利用できる一時ライセンスを取得してください。  
- **Purchase:** 継続的に使用するには、ライセンスの購入が必要です。

ライブラリの設定と環境の準備ができたら、ドーナツ グラフの実装に進みましょう。

## Java でドーナツ グラフを作成する方法は？
新しい `Presentation` オブジェクトをロードし、スライドにドーナツ グラフを追加し、穴のサイズを設定してファイルを保存します—すべて数回のシンプルな API 呼び出しで行えます。このアプローチにより、チャートデータ、外観、エクスポート形式を完全に制御でき、サーバーに Microsoft PowerPoint をインストールする必要がありません。

### Presentation オブジェクトの初期化
`Presentation` クラスは、Aspose.Slides のトップレベルオブジェクトで、メモリ内の PowerPoint ファイルを表します。  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
この手順で、スライド、シェイプ、チャートを追加できる空のプレゼンテーションが作成されます。

### スライドにドーナツ グラフを追加
`ISlide` は単一スライドのインターフェイスで、最初のスライドを取得するか新しいスライドを追加できます。  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
`addChart` メソッドはドーナツ グラフを作成します。パラメータはスライド上の位置 (X, Y) とサイズ (幅, 高さ) を定義します。

### ドーナツ の穴のサイズを設定
`Chart` は `setHoleSize(double)` を公開しており、チャート半径に対する内部半径のパーセンテージで穴のサイズを制御します。  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
穴のサイズを 90 % に設定すると、チャートはほぼ完全な円に見え、外側のセグメントを強調したい場合に便利です。

### プレゼンテーションの保存
`presentation.save(String, SaveFormat)` は、選択した形式でファイルをディスクに書き込みます。  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
この例では結果を `DoughnutHoleSize_out.pptx` として保存しますが、PDF、PNG、または 50 以上のサポート形式のいずれかを選択することもできます。

### リソースのクリーンアップ
`presentation.dispose()` を呼び出すと、ネイティブリソースが解放され、メモリリークが防止されます。特に長時間稼働するサーバー アプリケーションで重要です。  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## 実用的な応用例
ドーナツ グラフは多用途です。以下はその活用シーンの例です：

1. **Budget Allocation:** 予算が部門ごとにどのように配分されているかを表示します。  
2. **Survey Results:** 複数選択肢の質問への回答を可視化します。  
3. **Website Traffic Sources:** オーガニック、広告、リファラルなど、さまざまなチャネルからのトラフィック割合を示します。

## パフォーマンス上の考慮点
Aspose.Slides を使用する際、最適なパフォーマンスのために次のヒントを考慮してください。

- 使用が終わったらすぐに `Presentation` オブジェクトを破棄してネイティブメモリを解放します。  
- 大規模データセットにはストリーム (`FileInputStream`、`ByteArrayOutputStream`) を使用し、ファイル全体を RAM にロードするのを避けます。  
- ループで多数のスライドを生成する際は、チャートオブジェクトを再利用してオブジェクト生成のオーバーヘッドを削減します。

## よくある問題と解決策
- **Error while saving:** 出力ディレクトリが存在し、アプリケーションに書き込み権限があることを確認してください。  
- **Missing chart data:** `setHoleSize` を呼び出す前に、チャートの `ChartData` コレクションにデータを設定してください。  
- **Memory spikes:** 数千枚のスライドを含むプレゼンテーションでは、`Presentation.setSlideSize` を小さいサイズに設定し、途中のスライドを速やかに破棄してください。

## よくある質問

**Q: ドーナツ グラフのセグメントの色を調整できますか？**  
A: はい。`chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` を使用し、目的の RGB カラーを指定します。

**Q: チャートにデータ ラベルを追加するには？**  
A: `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` を呼び出すと、各セグメント内に値を表示できます。

**Q: PPTX 以外の形式でチャートを保存できますか？**  
A: もちろんです。Aspose.Slides は PDF、XPS、PNG、JPEG、TIFF など多数の形式（合計 50 以上）をサポートしています。

**Q: 大きなプレゼンテーションの読み込み中に例外が発生した場合はどうすればよいですか？**  
A: ストリームを受け取る `Presentation` コンストラクタを使用し、`loadOptions.setLoadFormat(LoadFormat.Pptx)` を有効にしてファイルをストリーミングし、メモリ使用量を削減してください。

**Q: ライブ データ ソースでチャートの更新を自動化できますか？**  
A: はい。データベースや REST API からデータを取得し、`ChartData` コレクションを更新してから、プレゼンテーションを保存する前に `chart.refresh()` を呼び出します。

## リソース
- **Documentation:** 詳細な API リファレンスは [Aspose.Slides for Java](https://reference.aspose.com/slides/java/) で確認してください。  
- **Download:** 最新のライブラリ バージョンは [Aspose.Slides releases](https://releases.aspose.com/slides/java/) から入手してください。  
- **Purchase:** フルアクセスには、[Aspose Purchase](https://purchase.aspose.com/buy) でライセンスを購入してください。  
- **Free Trial:** ダウンロードページで提供されている無料トライアルで Aspose.Slides を試すことができます。  
- **Temporary License:** 制限なしで拡張テストを行うための一時ライセンスを取得してください。  
- **Support:** 質問がありますか？[Aspose Forum](https://forum.aspose.com/c/slides/11) でサポートをご利用ください。

---

**最終更新日:** 2026-07-27  
**テスト環境:** Aspose.Slides for Java 24.12  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Slides for Java を使用して PowerPoint にチャートを追加する方法：ステップバイステップ ガイド](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides を使用した Java でのチャート作成方法：包括的ガイド](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}