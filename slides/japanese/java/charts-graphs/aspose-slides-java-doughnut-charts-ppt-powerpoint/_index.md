---
date: '2026-02-17'
description: Aspose.Slides for Java を使用してドーナツ グラフの PowerPoint を作成し、プログラムでチャート データ
  ポイントを追加する方法を学びます。簡単な手順とコード例に従ってください。
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Aspose.Slides for JavaでドーナツチャートのPowerPointを作成する
url: /ja/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java を使用したドーナツチャート PowerPoint の作成

## はじめに
魅力的なプレゼンテーションを作成するには、テキストや画像だけでなく、データを効果的に可視化するチャートが重要です。しかし、多くの開発者はプログラムで PowerPoint ファイルに動的なチャート機能を組み込むことに苦労しています。このチュートリアルでは、**Aspose.Slides for Java** を使用して **ドーナツチャート PowerPoint** を作成する方法を示します。柔軟性と使いやすさを兼ね備えた強力なツールです。

**学べること:**
- Aspose.Slides for Java でプレゼンテーションを初期化する方法
- スライドにドーナツチャートを追加する手順
- データポイントの設定とラベルプロパティのカスタマイズ
- 高忠実度でプレゼンテーションを保存する方法

これらの機能を活用してプレゼンテーションを強化しましょう。開始する前に、基本的な Java プログラミングの概念に慣れていることを確認してください。

## クイック回答
- **どのライブラリがドーナツチャート PowerPoint を作成しますか？** Aspose.Slides for Java
- **プログラムでチャートのデータポイントを追加できますか？** はい、chart API を使用します
- **本番環境でライセンスは必要ですか？** 有効な Aspose.Slides ライセンスが必要です
- **サポートされている Java バージョンは？** Java 8 以降（JDK 16 classifier が表示されています）
- **何シリーズまで追加できますか？** サンプルは最大 15 系列を追加しますが、必要に応じて調整可能です

## PowerPoint のドーナツチャートとは？
ドーナツチャートは、中心が空洞になった円グラフの変形で、コンパクトかつ視覚的に魅力的な形で複数のデータ系列を表示できます。全体と部分の関係を示すのに最適で、デザインもすっきりしています。

## Aspose.Slides for Java でドーナツチャートを作成する理由
- **チャートの外観、データ、レイアウトを PowerPoint を開かずに完全制御**
- **COM 相互運用なし** – Java をサポートする任意のプラットフォームで動作
- **大規模デッキや Web サービスとの統合に高性能**
- **爆発、ホールサイズ、スライス角度、ラベル書式設定など豊富なカスタマイズ**

## 前提条件
- Java プログラミングの基礎知識
- IntelliJ IDEA または Eclipse などの IDE
- Maven または Gradle による依存関係管理
- 有効な Aspose.Slides for Java ライセンス（無料トライアルあり）

## Aspose.Slides for Java の設定
プロジェクトに合わせた依存関係マネージャーを選択してください。

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

直接ダウンロードしたい場合は、[Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) ページをご覧ください。

### ライセンス取得
まずは無料トライアルで Aspose.Slides の機能を体験できます。長期利用の場合はライセンスを購入するか、[Aspose のウェブサイト](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得してください。環境設定と Aspose.Slides の初期化手順に従ってください。

## Aspose.Slides for Java を使用してドーナツチャート PowerPoint を作成する方法
以下に完全なステップバイステップガイドを示します。各コードブロックの前に説明があるので、何が行われているかが明確です。

### 手順 1: プレゼンテーションの初期化
既存の PPTX を読み込むか新規作成します。これによりスライドコレクションの操作が可能になります。

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### 手順 2: スライドにドーナツチャートを追加
チャートシェイプを追加し、デフォルトの系列/カテゴリをクリアし、基本的なビジュアルプロパティを設定します。

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### 手順 3: チャートデータポイントを追加しラベルをカスタマイズ
カテゴリを設定し、各系列のデータポイントを追加し、ラベルの外観を微調整します。ここで **add chart data points** キーワードが活躍します。

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### 手順 4: 更新したプレゼンテーションを保存
最後に変更を新しい PPTX ファイルに保存します。

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## 実用例
ドーナツチャートはさまざまな実務シナリオで活用できます:
- **財務レポート:** 予算配分や費用内訳の可視化
- **市場分析:** 競合他社間のシェア分布の表示
- **アンケート結果:** カテゴリ別調査データをコンパクトに提示
- **ダッシュボード生成:** データベースクエリと組み合わせてライブ更新スライドを作成

## パフォーマンス上の考慮点
- **リソースの解放**: 使用後は `pres.dispose()` を呼び出してネイティブメモリを解放
- **チャート数の制限**: 数百のチャートを追加するとメモリ使用量が増加するため、必要に応じてバッチ処理を検討
- **ストリーミングの活用**: 大規模データセットの場合、メモリ内配列ではなくストリームから直接ワークブックにデータを投入

## よくある問題と解決策
| Issue | Cause | Fix |
|-------|-------|-----|
| **Chart appears blank** | Data cells not populated correctly | Verify that `workBook.getCell(...)` references the correct row/column indices. |
| **Labels overlap** | Too many categories in limited space | Increase `DoughnutHoleSize` or adjust `FirstSliceAngle`. |
| **OutOfMemoryError** | Large presentations without disposing | Call `pres.dispose()` after saving and consider increasing JVM heap size. |

## FAQ

**Q: Aspose.Slides for Java を商用アプリケーションで使用できますか？**  
A: はい、ただし有効な商用ライセンスが必要です。評価用に無料トライアルがあります。

**Q: 15 系列以上を追加するにはどうすればよいですか？**  
A: 「Add Doughnut Chart」ステップのループ上限を増やし、データワークブックに十分な行があることを確認してください。

**Q: 作成後にドーナツの穴サイズを変更できますか？**  
A: はい、保存前であれば `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` を呼び出せます。

**Q: PPTX ではなく画像としてチャートをエクスポートできますか？**  
A: もちろんです。`chart.getImage()` を使用し、返された `java.awt.image.BufferedImage` を任意の形式で保存してください。

**Q: Aspose.Slides はアニメーション付きチャートをサポートしていますか？**  
A: アニメーションは `ISlide.getTimeline()` API で追加可能ですが、本チュートリアルの範囲外です。

## 結論
これで **Aspose.Slides for Java** を使用して **ドーナツチャート PowerPoint** ファイルを作成し、**チャートデータポイントを追加**、ラベルのカスタマイズ、パフォーマンス考慮事項の取り扱いまで網羅した、実践的で本番環境でも使える手法が身につきました。さまざまな色、データソース、チャートタイプを試して、プレゼンテーションをさらに際立たせてください。

---

**最終更新日:** 2026-02-17  
**テスト環境:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}