---
date: '2026-03-07'
description: Aspose.Slides を使用して Java でドーナツ グラフを作成する方法を学びましょう。このステップバイステップ ガイドでは、Maven
  の Aspose Slides 依存関係の設定、チャートの構成、プレゼンテーションの保存について説明します。
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Aspose.Slides ガイドで Java のドーナツチャートを作成
url: /ja/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides を使用した Java のドーナツチャート作成ガイド

## はじめに

プログラムで **doughnut chart** を作成すると、生の数値を視覚的に魅力的なグラフに変換し、瞬時にストーリーを伝えることができます。Java では **Aspose.Slides** がこのプロセスをシンプルにし、PowerPoint を開くことなくプレゼンテーション用のチャートを生成できます。このチュートリアルでは、Maven の Aspose Slides 依存関係の設定からシリーズやカテゴリのカスタマイズ、最終的なプレゼンテーションの保存まで、**create doughnut chart java** をステップバイステップで学びます。

このガイドの最後までに、任意の PPTX ファイルに動的なドーナツチャートを埋め込むことができるようになります。レポート、ダッシュボード、または自動化されたスライドデッキに最適です。

### Quick Answers
- **What library is used?** 使用されているライブラリは？ Aspose.Slides for Java  
- **Primary task?** 主なタスクは？ Create doughnut chart java in a PPTX file  
- **How to add the library?** ライブラリの追加方法は？ Use the Maven Aspose Slides dependency (or Gradle)  
- **Minimum Java version?** 最低 Java バージョンは？ JDK 16 or higher  
- **Can I customize colors and labels?** 色やラベルをカスタマイズできますか？ Yes, the API provides full formatting control  

## ドーナツチャートとは何か、なぜ使用するのか

ドーナツチャートは、中心が空いている円グラフの変形で、複数のデータ系列を同心円状のリングで表示できます。これにより、複数のカテゴリにわたる全体の一部を比較するのに最適です。たとえば、複数四半期にわたる地域別売上や、部門別の予算配分などが挙げられます。

## なぜ Aspose.Slides for Java を使用するのか

- **No Office installation required** – 任意のサーバーで PPTX ファイルを生成できます。  
- **Rich API** – チャートタイプ、データポイント、スタイリングをフルコントロール。  
- **High performance** – 大規模なプレゼンテーションに最適化。  
- **Cross‑platform** – Windows、Linux、macOS で動作。

## 前提条件

- **Required Libraries:**  
  - Aspose.Slides for Java version 25.4 or later.  

- **Environment Setup:**  
  - JDK 16 or higher.  
  - お好みの IDE (IntelliJ IDEA、Eclipse、NetBeans など)。  

- **Knowledge Prerequisites:**  
  - 基本的な Java プログラミング。  
  - Maven または Gradle を用いた依存関係管理の知識。

## Maven Aspose Slides Dependency

`pom.xml` に以下の Maven 依存関係を追加してください。これはプロジェクトにライブラリを取り込むための **maven aspose slides dependency** です。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Gradle を使用する場合は、以下の同等スニペットを利用してください。

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

公式リリースページから JAR を直接ダウンロードすることもできます:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### ライセンスの取得

評価版の透かしを除去し、フル機能を利用するには以下のいずれかを行います。

- **Free trial** – 一時的なライセンスで開始。  
- **Temporary license** – [Aspose website](https://purchase.aspose.com/temporary-license/) から取得。  
- **Commercial license** – 本番環境での使用のために購入。

コード内でライセンスを適用します:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## 実装ガイド

### プレゼンテーションの初期化とドーナツチャートの追加

まず、プレゼンテーションを作成または読み込み、最初のスライドにドーナツチャートを追加します。

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### チャートデータワークブックの設定と既存データのクリア

次に、チャートの基になるワークブックを取得し、デフォルトのシリーズやカテゴリをすべてクリアします。

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### チャートへのシリーズ追加

ここでは最大 15 系列を追加します。各シリーズはカスタマイズ可能で、今回は爆発効果、ドーナツホールサイズ、最初のスライス角度を設定します。

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

### カテゴリとデータポイントの追加

15 個のカテゴリを作成し、各シリーズにデータポイントを設定します。最後のシリーズには特別なラベル書式を適用します。

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

### プレゼンテーションの保存

最終的に、更新されたプレゼンテーションをディスクに書き出します。

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## よくある問題と解決策

- **License not found** – `license.lic` のパスが正しく、ファイルが読み取り可能か確認してください。  
- **Chart appears blank** – 新しいシリーズ/カテゴリを追加する前に、既存のものをクリアしたことを確認してください。  
- **Incorrect colors** – `FillType.Solid` が塗りと線の書式の両方で設定されているか確認してください。  
- **Performance with many series** – 系列/カテゴリの数を制限するか、ワークブックのセルを再利用してください。

## FAQ

**Q: 既存の PPTX ファイルがなくてもドーナツチャートを生成できますか？**  
A: はい、`new Presentation()` をインスタンス化して空のスライドデッキから開始できます。

**Q: Aspose.Slides は PDF へのエクスポートをサポートしていますか？**  
A: もちろんです。チャート作成後に `pres.save("output.pdf", SaveFormat.Pdf);` を呼び出してください。

**Q: ドーナツホールのサイズはどう変更しますか？**  
A: `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` を使用し、value に 0‑100 の値を指定します。

**Q: 最後のシリーズだけでなく、すべてのシリーズにデータラベルを追加できますか？**  
A: はい、`if (i == ...)` 条件の外にラベル書式ブロックを移動し、各 `dataPoint` に適用してください。

**Q: サポートされている Java のバージョンは？**  
A: Aspose.Slides 25.4 は JDK 16 以降をサポートします。以前の JDK では適切な classifier が必要です。

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}