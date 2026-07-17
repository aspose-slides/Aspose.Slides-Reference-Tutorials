---
date: '2026-07-17'
description: Aspose.Slides for Java を使用して、Pie Chart の回転、色のカスタマイズ、スライドの PDF へのエクスポート方法を学べる、データ可視化の完全ガイドです。
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Aspose.Slides for Java を使用して Pie Chart を回転させ、色をカスタマイズします。スライドを PDF
  にエクスポートし、チャート データ ワークシートを操作する方法も学べます。
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Java で Pie Chart を回転させ、色をカスタマイズする – Aspose.Slides ガイド
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Java と Aspose.Slides を使用した Pie Chart の回転と色のカスタマイズ方法
url: /ja/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java を使用した円グラフの作成: 完全チュートリアル

## はじめに
このガイドでは、**円グラフ** 要素の回転、各スライスの色のカスタマイズ、最終スライドの PDF へのエクスポート方法を Aspose.Slides for Java で学びます。販売ダッシュボード、財務レポート、その他データ駆動型プレゼンテーションを作成する際に、Microsoft Office に依存せずに視覚的に魅力的なグラフを提供できるようになります。ツールを準備して、さっそく始めましょう。

## クイック回答
- **新しいプレゼンテーションを開始するクラスは何ですか？** `Presentation` from `com.aspose.slides`。
- **円グラフを追加する API 呼び出しはどれですか？** `slide.addChart(ChartType.Pie, …)`。
- **各スライスに固有の色を付けるにはどうすればよいですか？** `series.setColorVaried(true)` を呼び出し、データポイントごとに単色塗りつぶしを設定します。
- **チャートを回転させるメソッドは何ですか？** `chart.setRotationAngle(double)` – 0 から 360 の度数で指定します。
- **スライドを PDF にエクスポートできますか？** はい、`presentation.save("output.pdf", SaveFormat.Pdf)` を呼び出します。

## 「円グラフの色をカスタマイズする」とは何ですか？
円グラフの色をカスタマイズするとは、円の各スライスに異なる塗りつぶし色を割り当て、可読性と視覚的インパクトを向上させることです。Aspose.Slides では、`setColorVaried(true)` で多様な色を有効にし、個々のデータポイントに単色塗りつぶしを設定することで実現できます。この手法により、各データセグメントがプレゼンテーション内で明確に際立ちます。

## なぜ Aspose.Slides for Java を使用して円グラフを作成するのですか？
Aspose.Slides は **150 以上のチャートタイプ** をサポートし、典型的なサーバー上で **300 ページ** のプレゼンテーションを **5 秒未満** でレンダリングできます。Microsoft Office のインストールは不要です。ライブラリは Windows、Linux、macOS 上で動作し、Java ベースのデータ可視化プロジェクトに対してクロスプラットフォームの柔軟性を提供します。

## 前提条件
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 以上
- IntelliJ IDEA、Eclipse、NetBeans などの IDE
- 基本的な Java の知識と Maven または Gradle の使用経験

## Aspose.Slides for Java の設定
ビルド構成にライブラリを追加します。

**Maven**  
`pom.xml` ファイルに以下のスニペットを追加してください:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
`build.gradle` ファイルに以下を含めます:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接ダウンロード**  
手動で設定したい場合は、最新の JAR を [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) からダウンロードしてください。

### ライセンス取得手順
- **Free Trial** – コストなしで全機能を試用できます。  
- **Temporary License** – 短期間のトライアル制限を延長します。  
- **Purchase** – 本番環境で使用できる永続ライセンスを取得します。

**基本的な初期化と設定**  
`Presentation` クラスはメモリ内の PowerPoint ファイルを表し、スライド操作用のメソッドを提供します。  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## 実装ガイド
以下は、スライドの作成から最終円グラフの回転までを網羅したステップバイステップの手順です。

### プレゼンテーションとスライドの初期化
新しい `Presentation` インスタンスを作成し、最初のスライドを取得してチャートのキャンバスとして使用します。  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### スライドに円グラフを追加
`addChart` は指定されたタイプのチャート シェイプを座標位置に追加します。  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### チャートタイトルの設定
`setTitle` はチャートにテキスト タイトルを割り当て、中央に配置します。  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### シリーズのデータ ラベルを構成
`setShowValue(true)` はシリーズの各データポイントに数値ラベルを表示します。  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### チャート データ ワークシートの準備
`ChartDataWorkbook` はチャートのシリーズとカテゴリに供給する基礎データテーブルを保持します。  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### チャートにカテゴリを追加
`addCategory` はチャート データシリーズ用の新しいカテゴリ ラベルを作成します。  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### シリーズを追加しデータ ポイントを入力
`addSeries` はデータシリーズを作成し、`addDataPointForBarSeries` が各カテゴリに数値を挿入します。  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### シリーズの色と枠線をカスタマイズ
`setColorVaried(true)` でスライスごとの色を有効にし、`setFillFormat` で各データポイントに単色塗りつぶしを割り当てます。  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### カスタム データ ラベルの構成
`setDataLabelFormat` はラベルの外観、位置、フォントをカスタマイズし、チャート注釈をより明瞭にします。  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### 回転角度の設定とプレゼンテーションの保存
`setRotationAngle` は円グラフ全体を回転させ、`save` はプレゼンテーションをファイルに書き出します。  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## 円グラフを回転させる方法は？
チャート オブジェクトを取得し、`chart.setRotationAngle(45.0)`（任意の度数）を呼び出してからプレゼンテーションを保存します。円グラフの回転は開始角度をシフトさせ、データを変更せずに特定のセグメントを強調できます。この単一メソッド呼び出しは Aspose.Slides のすべての `Chart` インスタンスで機能します。回転と多様なスライス色を組み合わせることで、最も重要なデータポイントに視線を誘導できます。

## 一般的な問題と解決策
| 問題 | 原因 | 対策 |
|------|------|------|
| **Slices all appear the same color** | `setColorVaried(true)` not called | Ensure you enable varied colors on the series group. |
| **Data labels not showing** | `showValue` flag disabled | Call `setShowValue(true)` on the label format. |
| **Rotation has no effect** | Using an older Aspose.Slides version | Upgrade to version 25.4 or later. |
| **License exception at runtime** | Missing or invalid license file | Load your license with `License license = new License(); license.setLicense("Aspose.Slides.lic");` before creating the `Presentation`. |

## よくある質問

**Q: How do I obtain an Aspose.Slides license for Java?**  
A: Aspose のウェブサイトから無料トライアルをリクエストし、永久ライセンスを購入してください。ランタイム時に、共通問題表に示したようにライセンスをロードします。

**Q: Can I use this code with older JDK versions?**  
A: この API は JDK 16 以上が必要です。古いバージョンはサポートされていません。

**Q: Is it possible to export the chart as an image instead of PPTX?**  
A: はい。レンダリング後に `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` を呼び出します。

**Q: What if I need more than one series in a pie chart?**  
A: 円グラフは単一データシリーズ向けに設計されています。複数シリーズが必要な場合は、ドーナツ グラフの使用を検討してください。

**Q: Does Aspose.Slides run on Linux servers?**  
A: 絶対に可能です。Aspose.Slides for Java はプラットフォームに依存せず、互換性のある JDK があれば任意の OS で動作します。

---

**最終更新日:** 2026-07-17  
**テスト環境:** Aspose.Slides for Java 25.4 (JDK 16)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Slides を使用した Java プレゼンテーションで円グラフを作成する方法: 包括的ガイド](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Aspose.Slides を使用した Java の円グラフマスター: 包括的ガイド](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Aspose.Slides を使用した Java のチャートテキスト回転: 包括的ガイド](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}