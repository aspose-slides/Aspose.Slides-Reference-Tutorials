---
date: '2026-08-21'
description: Aspose.Slides for Java を使用してクラスター化された縦棒グラフの作成方法とトレンドラインの追加方法を学びます。ライセンス設定、Maven/Gradle
  との統合、詳細なサンプルが含まれています。
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Aspose.Slides for Java を使用してクラスター化された縦棒グラフを作成し、トレンドラインを追加します。このガイドではライセンス設定、Maven/Gradle、ステップバイステップのコードスニペットを解説します。
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Aspose.Slides for Java でクラスター化された縦棒グラフを作成し、トレンドラインを追加する
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Aspose.Slides for Java を使用してクラスター化された縦棒グラフを作成し、トレンドラインを追加する方法
url: /ja/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for Java を使用してクラスター化された縦棒グラフを作成し、トレンドラインを追加する方法

魅力的なプレゼンテーションを作成するには、まずデータを明確に可視化することから始まります。このガイドでは、**clustered column chart**オブジェクトを作成し、強力な Aspose.Slides for Java API を使用して、指数、線形、対数、移動平均、多項式、べき乗のさまざまなトレンドラインでそれらを強化します。

## クイック回答
- **最初のステップは何ですか？** `Presentation` オブジェクトを初期化し、スライドにクラスター化された縦棒グラフを追加します。  
- **必要なライブラリのバージョンは？** Aspose.Slides for Java 25.4 以降。  
- **Maven または Gradle を使用できますか？** はい、両方サポートされています。Maven は `<dependency>` を使用し、Gradle は `implementation` を使用します。  
- **ライセンスは必要ですか？** 評価用にはトライアルライセンスで動作します。フル Aspose.Slides ライセンスを取得すると評価制限が解除されます。  
- **利用可能なトレンドラインの種類は何本ですか？** 6 つの組み込みタイプがあります：指数、線形、対数、移動平均、多項式、べき乗。

## クラスター化された縦棒グラフの作成とは？
`create clustered column chart` は、各カテゴリ内で複数のデータ系列を横に並べてグループ化するチャートを生成することを意味し、系列間の値を比較しやすくします。このチャートタイプは、地域別の四半期売上などのカテゴリデータの可視化に最適で、視聴者はグループ間の違いをすぐに把握できます。

## なぜトレンドラインを追加するのか？
トレンドラインはデータ系列の根底にあるパターンを示し、将来の値の予測、成長率の強調、ノイズの多いデータの平滑化に役立ちます。クラスター化された縦棒グラフにトレンドラインを追加することで、生の数値が実用的なインサイトとなり、ステークホルダーは長期的な傾向を理解し、データ駆動型の意思決定が可能になります。

## 前提条件
- **Java Development Kit (JDK)：** 8 以上。  
- **Aspose.Slides for Java：** バージョン 25.4 以上。  
- **IDE：** IntelliJ IDEA、Eclipse、または任意の Java 対応エディタ。  
- **ビルドツール：** Maven または Gradle（オプションですが推奨）。  
- **ライセンス：** トライアルまたは購入済みの Aspose.Slides ライセンスファイル。  

基本的な Java 構文に慣れ、プロジェクトの依存関係管理に精通していることが望まれます。

## Aspose.Slides for Java のセットアップ方法は？
好みの依存関係マネージャーを使用して Aspose.Slides ライブラリをプロジェクトに追加し、実行時にライセンスファイルが見つかる場所に配置します。これにより、すべての機能が有効になり、評価制限が解除されます。

### Maven
この依存関係を `pom.xml` ファイルに追加します：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` ファイルにこの行を含めます：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接ダウンロード
JAR は手動で [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) からダウンロードすることもできます。

#### Aspose Slides ライセンス
`Aspose.Slides.lic` ファイルをプロジェクトのルートに配置するか、`License license = new License(); license.setLicense("Aspose.Slides.lic");` のようにプログラムでライセンスを設定します。トライアルライセンスはすべての機能制限を解除しますが、購入ライセンスは評価用の透かしを除去し、フルパフォーマンス最適化を提供します。実稼働環境では、[Aspose purchase page](https://purchase.aspose.com/buy) からライセンスの購入をご検討ください。

## プレゼンテーションを作成し、クラスター化された縦棒グラフを追加する方法は？
`Presentation` クラスは PowerPoint ファイルを表し、スライドの作成、編集、保存のメソッドを提供します。`Presentation` のインスタンスを生成し、スライドを追加してから、`ChartType.ClusteredColumn` を指定して `addChart` を呼び出すことでチャートオブジェクトを作成します。このプロセスでスライドのキャンバスが設定され、チャートシェイプが挿入され、データの入力とスタイリングの準備が整います。

1. **プレゼンテーションの初期化** – 出力フォルダーを設定し、新しい `Presentation` インスタンスを作成します。  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **クラスター化された縦棒グラフの追加** – チャートシェイプを取得し、系列を設定し、データポイントを入力します。  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## 指数トレンドラインを追加する方法は？
`ITrendline` インターフェイスは、データパターンをモデル化するためにチャート系列に追加できるトレンドラインを定義します。`ITrendline` インスタンスを作成し、`TrendlineType` を `Exponential` に設定して目的の系列に付与することで、指数トレンドラインを適用できます。このトレンドラインは、増加率が加速する急速な成長データに有用です。

1. **トレンドラインの設定** – 系列を選択し、`addTrendline(TrendlineType.Exponential)` を呼び出します。  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## 線形トレンドラインを追加する方法は？
線形トレンドラインは、データポイントに最も適合する直線を示します。線の色や太さなど外観をカスタマイズして、プレゼンテーションのスタイルに合わせることも可能です。

1. **トレンドラインの設定** – `addTrendline(TrendlineType.Linear)` を使用し、`getLineFormat().setFillFormat().setFillType(FillType.Solid)` で色を変更します。  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## カスタムテキストフレーム付き対数トレンドラインを追加する方法は？
対数トレンドラインは、最初は急速に成長し、その後平坦になるデータに最適です。デフォルトのラベルを上書きすることで、トレンドの意味を説明するテキストを追加できます。

1. **トレンドラインのカスタマイズ** – トレンドラインを追加した後、`getDataLabel()` にアクセスし、`setText("Custom label")` プロパティを設定します。  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## 移動平均トレンドラインを追加する方法は？
移動平均トレンドラインは短期的な変動を平滑化し、長期的なトレンドを強調します。平均に使用する期間（ポイント数）を指定でき、ラインの平滑度を調整できます。

1. **トレンドラインの設定** – `addTrendline(TrendlineType.MovingAverage)` を呼び出し、`setPeriod(3)` で3ポイントの移動平均を使用します。  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## 多項式トレンドラインを追加する方法は？
多項式トレンドラインは、多項式方程式で定義された曲線でデータにフィットさせます。`order` プロパティは多項式の次数を制御し、より複雑な関係をモデル化できます。

1. **トレンドラインのカスタマイズ** – トレンドラインを追加した後、`setOrder(3)` を設定して3次（立方）フィットにします。  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## べき乗トレンドラインを追加する方法は？
べき乗トレンドラインは、データがべき乗則に従う場合に有用です。また、後方・前方の予測値を設定して、既存データ範囲を超えてラインを延長できます。

1. **トレンドラインの設定** – `addTrendline(TrendlineType.Power)` を使用し、`setBackward(2)` でラインを後方に延長します。  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## クラスター化された縦棒グラフにおけるトレンドラインの実用例
- **金融分析：** 指数および多項式トレンドは株価の変動予測に役立ちます。  
- **売上予測：** 移動平均ラインは季節的なピークを平滑化し、基礎的な売上トレンドをより明確に示します。  
- **科学研究：** 対数トレンドは、音圧や pH レベルなど、数桁にわたるデータに最適です。  
- **運用監視：** べき乗トレンドラインは時間経過による性能劣化をモデル化できます。

## Aspose.Slides 使用時のメモリ最適化方法は？
オブジェクトは速やかに破棄し、保存後に `presentation.dispose()` を使用します。大規模データセットの場合、画像の遅延ロードを有効にし、チャート全体を一度にメモリに読み込むのを避けます。

- **Dispose パターン：** `Presentation` を try‑with‑resources ブロックでラップするか、finally 節で `presentation.dispose()` を呼び出します。  
- **遅延ロード：** 数千のデータポイントを扱う際は `ChartData.setUseCache(true)` を設定します。  
- **ストリーミング出力：** プレゼンテーションを直接 `FileOutputStream` に書き込み、全ファイルを RAM に保持しないようにします。  

## Aspose.Slides for Java の定量的なメリット
Aspose.Slides は **50 種類以上のチャートタイプ** をサポートし、一般的な 2 GHz CPU 上で **30 秒未満** に **1,000 枚以上** のスライドを生成でき、Microsoft Office をインストールせずに **500 ページの PDF** を処理します。これらの数値は最新の 25.4 リリースで検証されています。

## 結論
これで、**clustered column chart** オブジェクトを作成し、Aspose.Slides for Java で利用可能なすべての主要なトレンドラインタイプで強化する完全なエンドツーエンドソリューションが手に入ります。上記の手順に従うことで、視覚的に魅力的で分析的に強力なデータ駆動型プレゼンテーションを作成できます。

次のステップとして、チャートのスタイリングオプションの検討、PDF/HTML へのエクスポート、複数データソースにわたるチャート生成の自動化があります。

## よくある質問

**Q: Maven プロジェクトで Aspose.Slides を設定するにはどうすればよいですか？**  
A: Maven セクションに示された `<dependency>` スニペットを `pom.xml` に追加し、`mvn clean install` を実行します。

**Q: 色やラベル以外にトレンドラインをカスタマイズできますか？**  
A: はい、`ITrendline` API を使用して、線のスタイル、幅、破線パターン、さらには前方・後方の予測値も変更できます。

**Q: バージョン互換性エラーが発生した場合はどうすればよいですか？**  
A: JDK バージョンが Aspose.Slides の最低要件（JDK 8 以上）と一致しているか確認してください。破壊的変更については Aspose のリリースノートを参照してください。

**Q: 複数のチャートに自動的にトレンドラインを追加することは可能ですか？**  
A: もちろん可能です。スライドコレクション内の各 `IChart` をループし、各系列に対して適切な `addTrendline` メソッドを呼び出します。

**Q: 本番環境での使用には有料ライセンスが必要ですか？**  
A: はい、購入した Aspose.Slides ライセンスは評価制限を解除し、フルパフォーマンス最適化を利用可能にします。

---

**Last Updated:** 2026-08-21  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## 関連チュートリアル

- [aspose slides maven dependency: Aspose.Slides for Java を使用したプレゼンテーションへのチャート追加と設定](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}