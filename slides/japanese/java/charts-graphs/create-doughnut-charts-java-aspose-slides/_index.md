---
"date": "2025-04-17"
"description": "Aspose.Slidesを使ってJavaで魅力的なドーナツグラフを作成する方法を学びましょう。この包括的なガイドでは、初期化、データ設定、プレゼンテーションの保存について解説します。"
"title": "Aspose.Slides を使用して Java でドーナツ チャートを作成する包括的なガイド"
"url": "/ja/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides を使用して Java でドーナツ グラフを作成する: ステップバイステップ ガイド

## 導入

今日のデータドリブンな環境において、情報を効果的に視覚化することは、理解とエンゲージメントを高める鍵となります。特にJavaでは、プログラムで本格的なグラフを作成するのは難しいように思えるかもしれませんが、このガイドでは、Aspose.Slides for Javaを使ってドーナツグラフを簡単に作成する方法を解説します。

これらの手順に従うことで、開発者はプレゼンテーション スライドを操作し、データ視覚化をシームレスに統合する実践的な経験を積むことができます。

**重要なポイント:**
- Aspose.Slides Java を使用してプレゼンテーション オブジェクトを初期化します。
- グラフ データを構成し、既存のシリーズまたはカテゴリを管理します。
- グラフのシリーズとカテゴリを追加してカスタマイズします。
- データ ポイントを効果的にフォーマットして表示します。
- プレゼンテーションをさまざまな形式で簡単に保存できます。

実装に取り掛かる前に、開始に必要なものがすべて揃っていることを確認してください。

## 前提条件

このチュートリアルを実行するには、次のものを用意してください。

- **必要なライブラリ:**
  - Aspose.Slides for Java バージョン 25.4 以降。
  
- **環境設定:**
  - システムに JDK 16 以降がインストールされていること。
  - IntelliJ IDEA、Eclipse、NetBeans などの IDE。

- **知識の前提条件:**
  - Java プログラミング概念の基本的な理解。
  - Maven または Gradle プロジェクトでの依存関係の管理に関する知識。

## Aspose.Slides for Java のセットアップ

Aspose.Slides をプロジェクトに統合するには、ビルド ツールに応じて次の手順に従います。

**Maven のセットアップ:**
次の依存関係を `pom.xml` ファイル：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle のセットアップ:**
以下の内容を `build.gradle` ファイル：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接ダウンロード:**
または、最新バージョンを直接ダウンロードしてください。 [Aspose.Slides for Java リリース](https://releases。aspose.com/slides/java/).

### ライセンスの取得

評価制限なしで Aspose.Slides を使用するには:
- **無料トライアル:** 完全な機能を試すには、一時ライセンスから始めてください。
- **一時ライセンス:** 入手するには [Aspose ウェブサイト](https://purchase。aspose.com/temporary-license/).
- **購入：** 継続使用のために購入を検討してください。

次を使用して、Java アプリケーションにライセンスを適用します。
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## 実装ガイド

### プレゼンテーションとチャートの初期化

#### 概要
まず、プレゼンテーション オブジェクトを初期化し、最初のスライドにドーナツ グラフを追加します。

**ステップ1: プレゼンテーションの初期化**
既存の PPTX ファイルを読み込むか、新しいファイルを作成します。
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**ステップ2: ドーナツグラフを追加する**
最初のスライドの指定された座標にグラフを作成します。
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### グラフデータワークブックの構成と既存のシリーズ/カテゴリのクリア

#### 概要
グラフ データ ワークブックを構成し、既存のシリーズまたはカテゴリを削除します。

**ステップ1: チャートデータワークブックにアクセスする**
チャートにリンクされたワークブックを取得します。
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**ステップ2: 既存のシリーズとカテゴリをクリアする**
残留データポイントがないことを確認します。
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### チャートにシリーズを追加する

#### 概要
外観と動作をそれぞれカスタマイズした複数のシリーズをチャートに追加します。

**ステップ1: シリーズを反復的に追加する**
インデックスをループしてシリーズを追加します。
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // シリーズをカスタマイズする
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### チャートにカテゴリとデータポイントを追加する

#### 概要
カテゴリを設定し、ラベルに特定の書式を使用してデータ ポイントを追加します。

**ステップ1: カテゴリを追加する**
各カテゴリのインデックスをループします。
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**ステップ2: 各シリーズにデータポイントを追加する**
現在のカテゴリの各シリーズを反復処理します。
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // データポイントの形式設定
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // 最後のシリーズのラベルの書式設定
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

        // 表示オプションを調整する
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // ラベルの位置を調整する
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### プレゼンテーションを保存する

#### 概要
チャートを設定したら、プレゼンテーションを指定されたディレクトリに保存します。

**ステップ1: プレゼンテーションを保存する**
使用 `save` 変更を書き込む方法:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## 結論

Aspose.Slidesを使用してJavaでドーナツグラフを作成およびカスタマイズする方法を学習しました。これらの手順は、洗練されたデータ視覚化をプレゼンテーションに統合するための基礎となります。

**次のステップ:**
- Aspose.Slides で利用できるさまざまなグラフ タイプを試してください。
- ブランドのニーズに合わせて、色、フォント、スタイルなどの追加のカスタマイズ オプションを調べてください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}