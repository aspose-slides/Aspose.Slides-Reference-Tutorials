---
date: '2026-07-22'
description: Aspose Slides Maven Dependency を学び、Java で stacked column chart を作成し、data
  labels を追加し、vertical axis の数値形式を変更し、結果を PPTX ファイルとしてエクスポートします。
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency を使用すると、Java で stacked column chart
  を構築し、data labels をカスタマイズし、vertical axis の形式を調整して PPTX として保存できます。すべてが簡潔で本番環境向けのコードで実現します。
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Java における Stacked Column Chart'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Java における Stacked Column Chart'
url: /ja/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven 依存関係: Java の積み上げ縦棒グラフ

## はじめに

**Aspose.Slides for Java** の力で洞察に満ちたデータ可視化を組み込んで、プレゼンテーションを格上げしましょう。このガイドでは、ビジネスレポートの作成やプロジェクト統計の提示に最適な、**積み上げ縦棒グラフ**をプロフェッショナルに作成する方法を学びます。チュートリアルの最後までに以下ができるようになります。

- **Aspose Slides Maven 依存関係**で環境を設定する
- ゼロからプレゼンテーションを作成する
- **パーセンテージ積み上げチャート**を追加し、外観をカスタマイズする
- **チャートのデータラベルをフォーマット**し、**縦軸の数値形式を変更**する
- **1 行のコードでプレゼンテーションを PPTX として保存**する

## クイック回答
- **What library do I need?** Add the `aspose-slides` Maven/Gradle dependency (see “Aspose Slides Maven Dependency” below).  
- **Which chart type creates a stacked view?** Use `ChartType.PercentsStackedColumn` for a percentage‑stacked column chart.  
- **How can I change the axis number format?** Call `IAxis.setNumberFormat()` and set `setNumberFormatLinkedToSource(false)`.  
- **Can I customize data labels?** Yes – iterate through each `IChartDataPoint` and assign a custom `ITextFrame`.  
- **How do I save the file?** Invoke `presentation.save("output.pptx", SaveFormat.Pptx)`.

## 積み上げ縦棒グラフとは？
積み上げ縦棒グラフは、各カテゴリの列に複数のデータ系列を縦方向に積み重ねて表示し、**パーセンテージ積み上げ**バージョンでは各列を 100 % に正規化して比率比較を容易にします。この形式により、視聴者は各構成要素が全体に対してどの程度貢献しているかをカテゴリごとにすばやく把握でき、トレンドや相対的なサイズが瞬時に明らかになります。

## なぜ Aspose.Slides for Java を使用するのか？
Aspose.Slides for Java は **Microsoft Office を必要とせず** に PowerPoint ファイルの生成、編集、変換が可能で、Windows、Linux、macOS 上で **50 以上の出力形式** をサポートします。ライブラリは完全に JRE 上で動作し、サーバーサイドの自動化や高スループットのレポート作成に最適です。また、チャートオブジェクト、スライドレイアウト、ドキュメントプロパティに対する細かな制御を提供し、エンタープライズレベルのプレゼンテーション生成に理想的です。

## 前提条件
- **Java Development Kit (JDK):** 8 以上  
- **IDE:** IntelliJ IDEA、Eclipse、または任意の Java 対応エディタ  
- **Build Tool:** Maven または Gradle（任意だが推奨）  
- **Basic Java knowledge** – クラスやメソッドに慣れていることが望ましい  

## Aspose.Slides for Java の設定
まず、Aspose.Slides ライブラリをプロジェクトに追加します。

### Aspose Slides Maven 依存関係
`pom.xml` に以下を追加してください（これが必要な **aspose slides maven dependency** です）:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle の代替手段
Gradle を使用する場合は、`build.gradle` に次の行を追加します:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接ダウンロード
または、最新の JAR を [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) からダウンロードしてください。

### ライセンス取得
Aspose.Slides の機能を試すには無料トライアルから始められます。評価制限を解除するには、一時ライセンスまたは購入ライセンスの取得をご検討ください。

- **Free Trial:** すぐに費用がかからず、制限された機能にアクセスできる。  
- **Temporary License:** [Aspose のサイト](https://purchase.aspose.com/temporary-license/) からリクエスト。  
- **Purchase:** 完全なアクセスのために購入ページへ。

### 基本的な初期化
`Presentation` は Aspose.Slides のコアクラスで、メモリ上の PowerPoint ファイルを表します。以下の最小コードスニペットは `Presentation` オブジェクトの作成方法を示しています:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## 実装ガイド

### プレゼンテーションの作成とスライドの追加
**概要:**  
まず、空のプレゼンテーションを作成し、スライドが存在することを確認します。

#### 手順 1: Presentation オブジェクトの初期化
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### 手順 2: プレゼンテーションの保存
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### スライドへのパーセンテージ積み上げ縦棒グラフの追加
**概要:**  
次に、**パーセンテージ積み上げチャート**を最初のスライドに配置します。

`ChartType.PercentsStackedColumn` はパーセンテージ積み上げ縦棒グラフの種類を指定します。

#### 手順 1: スライドの初期化と取得
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### 手順 2: スライドにチャートを追加
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### チャート軸の数値形式のカスタマイズ
**概要:**  
可読性向上のため、**縦軸の形式をパーセンテージ表示に変更**します。

`IAxis` はチャート軸を表すインターフェイスで、形式やスケーリングの調整が可能です。

#### 手順 1: チャートの追加と取得
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### 手順 2: カスタム数値形式の設定
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### チャートへの系列とデータポイントの追加
**概要:**  
サンプルデータ系列でチャートを埋めます。

#### 手順 1: Presentation とチャートの初期化
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### 手順 2: データ系列の追加
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### 系列の塗りつぶし色の設定
**概要:**  
各系列に異なる色を付けて、チャートの視認性を向上させます。

#### 手順 1: チャートの初期化と取得
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### 手順 2: 塗りつぶし色の設定
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### データラベルのフォーマット
**概要:**  
**チャートのデータラベルをフォーマット**し、カスタムテキストを表示させます。

`IChartDataPoint` はチャート系列内の個々のデータポイントを表し、`ITextFrame` がラベルテキストを保持します。

#### 手順 1: チャート系列とデータポイントへのアクセス
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### 手順 2: データラベルのカスタマイズ
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## よくある問題と解決策
- **Chart appears empty:** 保存前に少なくとも1つのデータ系列とデータポイントを追加していることを確認してください。  
- **Axis numbers not showing percentages:** `verticalAxis.setNumberFormatLinkedToSource(false)` を設定することを忘れないでください。設定しないとカスタム形式が無視されます。  
- **License evaluation message:** `Presentation` オブジェクトを作成する前に有効なライセンスファイルを適用して、評価バナーを非表示にしてください。

## よくある質問

**Q: Can I use this code with Java 11 or newer?**  
A: Yes. The library supports JDK 8+; just use the appropriate classifier (e.g., `jdk16` for JDK 16 or later).  

**Q: How do I export the chart as an image instead of a PPTX?**  
A: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding the chart to the slide.  

**Q: Is it possible to add a legend to the stacked column chart?**  
A: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My Chart");` and configure `chart.getLegend()` as needed.  

**Q: What if I need to update data after the presentation is generated?**  
A: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();` to reflect changes.  

**Q: Does Aspose.Slides work on Linux servers?**  
A: Yes. The library is pure Java and runs on any OS with a compatible JRE.  

## 結論
このガイドに従って、**Aspose Slides Maven 依存関係**を使用した Java での**積み上げ縦棒グラフ**の作成方法を習得しました。環境設定から細かなビジュアル調整まで網羅しています。さまざまなデータセット、色、ラベル形式を試して、レポートを際立たせましょう。

---

**最終更新日:** 2026-07-22  
**テスト対象:** Aspose.Slides 25.4 (jdk16 classifier)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Java で Aspose.Slides を使用したクラスター縦棒グラフの作成方法](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Aspose.Slides for Java を使用したチャートデータポイントの数値形式設定方法](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Aspose.Slides for Java を使用したプレゼンテーションへのチャート追加と設定方法](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}