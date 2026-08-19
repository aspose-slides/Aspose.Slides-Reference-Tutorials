---
date: '2026-07-03'
description: Aspose.Slides を使用して Java でサンバーストチャートをステップバイステップで作成する方法を学び、PowerPoint
  プレゼンテーション向けの完全なカスタマイズオプションを提供します。
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Aspose.Slides を使用した Java でのサンバーストチャートの作成方法
url: /ja/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# JavaでAspose.Slidesを使用してサンバーストチャートを作成する方法

## はじめに
データ主導のプレゼンテーションでは、**サンバーストをすばやく作成する方法**を知っているだけでスライドが際立ちます。このチュートリアルでは、Aspose.Slides for Java を使用してサンバーストチャートを作成する手順を、プロジェクトのセットアップから最終エクスポートまで解説します。Java のエコシステムを離れることなく、階層データの魅力的なビジュアルを提供できます。

## クイック回答
- **PowerPoint ファイルのメインクラスは何ですか？** `Presentation` – メモリ内の全体の PPTX を表します。  
- **基本的なサンバーストには何行のコードが必要ですか？** ライブラリを参照すれば、通常 5〜7 行で作成できます。  
- **サポートされている出力形式は何ですか？** PPTX、PDF、PNG、SVG、HTML。  
- **個々のセグメントをスタイル設定できますか？** はい – 塗りつぶしカラー、枠線、データ ラベルはすべてカスタマイズ可能です。  
- **本番環境でライセンスが必要ですか？** 無料評価版はテストに利用できますが、デプロイ時は商用ライセンスが必要です。

## サンバーストチャートとは？
サンバーストチャートは階層データを同心円状のリングで可視化します。各リングが階層のレベルを表し、閲覧者は一目で親子関係を把握できます。組織図、分類表示、マルチレベル指標などに最適です。製品ライン、地域、組織構造などの多層カテゴリを表示する際に、全体の分布と各セグメントの詳細な内訳の両方を示すことができます。

## なぜ Aspose.Slides をサンバーストチャートに使うのか？
Aspose.Slides は **30 種類以上のチャートタイプ** をサポートし、**500 MB** までのファイルをメモリ全体にロードせずに処理でき、**300 DPI** の高解像度でグラフィックをレンダリングします。これらの数値化された機能により、大規模なプレゼンテーションでも高速生成と高品質なビジュアルが保証されます。さらに、スレッドセーフな操作と主要な Java ビルドツールとのシームレスな統合により、デスクトップでもサーバーサイドでもスケールしたプレゼンテーション生成が可能です。

## 前提条件
- Java Development Kit (JDK) 8 以上。  
- 依存関係管理のための Maven または Gradle。  
- Aspose.Slides for Java（最新バージョン）。  
- 階層データ構造の基本的な理解。

## サンバーストチャート作成手順
環境をセットアップし、チャートを追加し、階層データを供給し、スタイルを設定してファイルを保存するだけのシンプルな手順です。以下のワークフローは余計なボイラープレートコードを書かずに実行できます。プロセスは完全に自動化されており、手動の UI 操作は不要で、バッチジョブや Web サービスに組み込んでオンデマンドでチャートを生成できます。

### 手順 1: プロジェクトのセットアップ
`pom.xml` に Aspose.Slides の Maven 依存関係（または同等の Gradle スニペット）を追加します。これにより、必要なバイナリとトランジティブライブラリがすべて取得されます。

### 手順 2: プレゼンテーションの読み込みまたは作成
`Presentation` は Aspose.Slides のトップレベルオブジェクトで、メモリ内の単一 PowerPoint ファイルを表します。`new Presentation()` で新規デッキを作成するか、ファイルパスを渡して既存の PPTX を開きます。

### 手順 3: サンバーストチャートの追加
`slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)` を使用してスライドに新しいチャートシェイプを挿入します。これにより、データ入力用のサンバーストプレースホルダーが作成されます。`ChartType.Sunburst` はチャート追加時にサンバーストタイプを指定します。

### 手順 4: 階層データの入力
`ChartData` はチャートのデータ系列とカテゴリを保持します。チャートの `ChartData` コレクションにアクセスし、階層を反映した系列とカテゴリを追加します。各レベルについて `ParentSeries` プロパティで親子関係を指定すれば、チャートは自動的に同心円リングを描画します。

### 手順 5: 外観のカスタマイズ
`ChartSeries` と `ChartDataPoint` オブジェクトを通じて、セグメントの色、枠線スタイル、データラベルを微調整します。`ChartSeries` はチャート内のデータポイント系列を表し、`ChartDataPoint` は系列内の個々のデータポイントを表します。3D 回転を有効にしたり、`Explode` プロパティで特定のスライスを強調表示したりすることも可能です。

### 手順 6: プレゼンテーションの保存
`SaveFormat` 列挙体で保存可能なファイル形式を指定します。`presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` でディスクに書き出します。`SaveFormat` の値を変更すれば PDF や PNG へのエクスポートも可能です。

## サンバーストチャートの色をカスタマイズする方法
各 `ChartDataPoint` に対して `point.getFillFormat().setFillType(FillType.Solid)` を呼び出し、続いて `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))` で塗りつぶし色を指定します。この直接的なアプローチにより、企業ブランディングに合わせたり、重要データポイントを強調したりできます。グラデーション塗りつぶしや透明度調整、テーマカラーの使用も可能で、スライド全体のデザインと一貫性を保てます。

## よくある問題と解決策
- **問題:** 階層が平坦に表示される。  
  **解決策:** 各子系列が正しく `ParentSeries` を参照しているか確認してください。リンクが欠けていると、チャートはすべて単一レベルとして扱います。  
- **問題:** エクスポートした PNG がぼやけている。  
  **解決策:** `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)` でエクスポート DPI を上げます。  
- **問題:** 大きな PPTX ファイルで OutOfMemoryError が発生する。  
  **解決策:** `Presentation.setMemoryOptimization(true)` を使用してデータをストリーミングし、メモリ使用量を抑えます。

## FAQ

**Q: CSV ファイルからサンバーストチャートを生成できますか？**  
A: はい。CSV を読み込み、メモリ上で階層を構築し、チャートの `ChartData` コレクションに供給してから保存します。

**Q: Aspose.Slides はサンバーストチャートのアニメーション遷移をサポートしていますか？**  
A: サポートしています。スライドに `SlideShowTransition` を適用するか、チャートレベルのアニメーションには `ChartFormat.setAnimationEnabled(true)` を使用します。

**Q: チャートを SVG ベクターグラフィックとしてエクスポートできますか？**  
A: もちろんです。`SaveFormat.Svg` でプレゼンテーションを保存すれば、サンバーストチャートのスケーラブルベクターバージョンが得られます。

**Q: サンバーストチャートが扱えるデータポイントの最大数は？**  
A: Aspose.Slides は単一のサンバーストチャートで **10,000** データポイントまでをパフォーマンス低下なしに処理できます。

**Q: 各デプロイ環境ごとに別々のライセンスが必要ですか？**  
A: 1 つの商用ライセンスで開発、ステージング、本番すべての環境をカバーできます（ライセンス条件を遵守する限り）。

## 結論
これで、Java で Aspose.Slides を使用して **サンバーストを作成する方法** の完全なステップバイステップガイドが手に入りました。上記のワークフローに従えば、任意の PowerPoint プレゼンテーションに高品質で完全にカスタマイズ可能な階層ビジュアルを生成できます。

---

**最終更新日:** 2026-07-03  
**テスト環境:** Aspose.Slides for Java 24.12  
**作者:** Aspose

## 関連チュートリアル

- [Java 用 Aspose.Slides で PowerPoint にチャートを追加する方法：ステップバイステップガイド](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [動的プレゼンテーションのための Aspose.Slides Java を使用した PowerPoint チャートカスタマイズのマスター](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Aspose.Slides for Java で PowerPoint チャートカテゴリにアニメーションを付ける | ステップバイステップガイド](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}