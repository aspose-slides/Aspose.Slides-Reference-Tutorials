---
date: '2026-08-16'
description: Aspose.Slides を使用して Java で doughnut chart を追加する方法を学びます。このステップバイステップガイドでは、Maven
  の依存関係設定、チャートの構成、色、ラベル、PPTX の保存について解説します。
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Aspose.Slides を使用して Java で doughnut chart を追加する方法。このガイドに従って Maven
  を設定し、色やラベルをカスタマイズし、PPTX ファイルを生成してください。
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Java と Aspose.Slides で doughnut chart を追加する方法
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Java と Aspose.Slides で doughnut chart を追加する方法
url: /ja/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java と Aspose.Slides でドーナツ グラフを追加する方法

## はじめに

プログラムで **ドーナツ グラフ** を作成すると、生の数値をすぐにストーリーを伝える目を引くビジュアルに変換できます。Java では **Aspose.Slides** がこのプロセスをシンプルにし、PowerPoint を開くことなくプレゼンテーション用のグラフを生成できます。このチュートリアルでは、Maven の Aspose Slides 依存関係の設定からシリーズ、カテゴリ、色、ラベルのカスタマイズ、最終的なプレゼンテーションの保存まで、**ドーナツ グラフを追加する方法** をステップバイステップで学びます。

このガイドの最後までに、レポートやダッシュボード、または自動化されたスライドデッキに最適な、任意の PPTX ファイルに動的なドーナツ グラフを埋め込むことができるようになります。

### クイック回答
- **使用されているライブラリは何ですか？** Aspose.Slides for Java  
- **主なタスクは？** PPTX ファイルにドーナツ グラフを追加する  
- **ライブラリの追加方法は？** Maven の Aspose Slides 依存関係を使用します（または Gradle）  
- **最低限の Java バージョンは？** JDK 16 以上  
- **色やラベルをカスタマイズできますか？** はい、API は完全な書式設定コントロールを提供します  

## ドーナツ グラフとは何か、なぜ使用するのか

ドーナツ グラフは、中心が空白の円グラフの変形で、複数のデータ系列を同心円状に表示できます。**中心に追加情報のスペースを確保しながら、複数のカテゴリにわたる全体に対する部分を可視化します。** これにより、複数四半期にわたる地域別売上比較、部門別予算配分、または階層的な比率データを示す必要があるあらゆるシナリオに最適です。

## なぜ Aspose.Slides for Java を使用するのか

Microsoft Office をインストールせずにドーナツ グラフを追加でき、ライブラリは **50 以上の入力および出力フォーマット** を処理し、500 スライドを超えるプレゼンテーションにも対応します。Aspose.Slides は同一ハードウェア上のネイティブ Office 自動化と比較して **最大 3 倍速いレンダリング** を実現し、Windows、Linux、macOS で動作します。これらの定量的な利点により、ヘッドレスサーバー上で予測可能なパフォーマンスで大規模なスライドデッキを生成できます。

## 前提条件

- **必要なライブラリ**  
  - Aspose.Slides for Java 25.4 以降（ドーナツ グラフを追加できるライブラリ）。

- **環境**  
  - マシンに JDK 16 以上がインストールされていること。  
  - IntelliJ IDEA、Eclipse、NetBeans などの IDE。

- **知識**  
  - 基本的な Java 構文とオブジェクト指向の概念。  
  - 依存関係管理のための Maven または Gradle の知識。

## Maven Aspose Slides 依存関係

次の Maven 依存関係を `pom.xml` に追加します。これはプロジェクトにライブラリを取り込むために必要な **maven aspose slides dependency** です。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Gradle を使用したい場合は、以下の同等のスニペットを使用してください。

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

公式リリースページから JAR を直接ダウンロードすることもできます：
[Aspose.Slides for Java リリース](https://releases.aspose.com/slides/java/)

### ライセンスの取得

評価用ウォーターマークを削除し、フル機能セットを有効にするには：

- **無料トライアル** – 一時ライセンスで開始します。  
- **一時ライセンス** – [Aspose のウェブサイト](https://purchase.aspose.com/temporary-license/)から取得してください。  
- **商用ライセンス** – 本番利用のために購入します。

コード内でライセンスを適用します：

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## 実装ガイド

### プレゼンテーションの初期化とドーナツ グラフの追加

Presentation は PowerPoint プレゼンテーションを表す Aspose.Slides のクラスです。  
既存の PPTX をロードするか、新しい `Presentation` オブジェクトを作成し、最初のスライドにドーナツ グラフを追加します。

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### チャート データ ワークブックの設定と既存データのクリア

ワークブックはチャートのデータを保持する内部スプレッドシートです。  
チャートが使用しているワークブックを取得し、デフォルトのシリーズやカテゴリをすべてクリアして、クリーンな状態から開始できるようにします。

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### チャートへのシリーズ追加

シリーズはチャート上にプロットされるデータポイントの集合を表します。  
最大 15 系列まで追加可能です。各シリーズはカスタマイズでき、ここでは爆発効果、ドーナツ ホールのサイズ、最初のスライス角度を設定します。

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### カテゴリとデータポイントの追加

カテゴリはチャート軸に沿った各データポイントのラベルです。  
15 個のカテゴリを作成し、各シリーズにデータポイントを設定します。最後のシリーズには特別なラベル書式が適用されます。

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### 色とデータラベルのカスタマイズ

`FillType.Solid` はチャート要素の単色塗りつぶしを指定します。  
各シリーズに単色塗りつぶしを設定し、データラベルを有効にします。最後のシリーズではラベルのフォントカラーも変更します。

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### プレゼンテーションの保存

`save` は選択した形式でプレゼンテーションをファイルに書き込みます。  
更新したプレゼンテーションを PPTX 形式でディスクに保存するか、必要に応じて PDF にエクスポートします。

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## よくある問題と解決策

- **ライセンスが見つかりません** – `license.lic` のパスが正しく、ファイルが読み取り可能であることを確認してください。  
- **チャートが空白になる** – 新しいシリーズ/カテゴリを追加する前に、既存のものをクリアしたことを確認してください。  
- **色が正しくない** – 塗りつぶしと線の書式の両方で `FillType.Solid` が設定されていることを確認してください。  
- **多数のシリーズでのパフォーマンス** – メモリ使用量を抑えるため、シリーズ/カテゴリの数を制限するか、ワークブックのセルを再利用してください。  

## よくある質問

**Q: 既存の PPTX ファイルがなくてもドーナツ グラフを生成できますか？**  
A: はい、`new Presentation()` をインスタンス化して空のスライドデッキから開始し、上記のようにチャートを追加します。

**Q: Aspose.Slides は PDF へのエクスポートをサポートしていますか？**  
A: もちろんです。チャート作成後、`pres.save("output.pdf", SaveFormat.Pdf);` を呼び出すとスライドの PDF バージョンが取得できます。

**Q: ドーナツ ホールのサイズはどう変更しますか？**  
A: `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` を使用します。`value` は 0 から 100 の範囲です。

**Q: 最後のシリーズだけでなく、すべてのシリーズにデータラベルを追加できますか？**  
A: はい、`if (i == ...)` 条件の外にラベル書式ブロックを移動し、各 `dataPoint` に適用すれば可能です。

**Q: サポートされている Java のバージョンは何ですか？**  
A: Aspose.Slides 25.4 は JDK 16 以降をサポートします。以前の JDK を使用する場合は、Maven 依存関係で適切な classifier を指定する必要があります。

---

**最終更新日:** 2026-08-16  
**テスト環境:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**作者:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## 関連チュートリアル

- [Aspose.Slides for Java を使用して PowerPoint にチャートを追加する方法：ステップバイステップ ガイド](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides を使用した Java の円グラフの色カスタマイズ – 完全ガイド](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Aspose.Slides for Java で PowerPoint チャートのカテゴリをアニメーション化する方法 | ステップバイステップ ガイド](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}