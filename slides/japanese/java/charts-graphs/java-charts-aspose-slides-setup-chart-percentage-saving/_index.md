---
"date": "2025-04-17"
"description": "Aspose.Slides を使って、Java プレゼンテーションでパーセンテージラベル付きのグラフを作成、カスタマイズ、保存する方法を学びましょう。今すぐプレゼンテーションスキルを磨きましょう！"
"title": "Aspose.Slides を使用して Java プレゼンテーションでグラフを作成およびカスタマイズする"
"url": "/ja/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides を使用して Java プレゼンテーションでグラフを作成およびカスタマイズする

## 導入
魅力的なプレゼンテーションを作成するには、テキストだけでは不十分な場合が多く、情報を効果的に伝える動的なグラフが不可欠です。JavaベースのプレゼンテーションにAspose.Slidesを使った高度なグラフ機能を追加して、より魅力的なプレゼンテーションを作成したいとお考えなら、このチュートリアルが最適です。プレゼンテーションの作成、グラフの追加と設定、合計の計算、パーセンテージラベルの表示、そして作業内容の保存まで、すべて簡単な手順で行えます。

**学習内容:**
- Aspose.Slides for Java を使用してグラフ付きのプレゼンテーションを作成し、カスタマイズする方法
- グラフでカテゴリの合計を計算する
- チャート上のパーセンテージラベルとしてデータを表示する
- 強化されたグラフ機能でプレゼンテーションを保存する

始める前に必要な前提条件について詳しく見ていきましょう。

## 前提条件
このチュートリアルを実行するには、次のものを用意してください。

- **Java開発キット（JDK）**: バージョン 8 以上。
- **IDE**: IntelliJ IDEA、Eclipse、または Java をサポートする任意の IDE など。
- **Aspose.Slides for Java ライブラリ**これはプレゼンテーション機能の処理に重要です。

### 必要なライブラリとバージョン
Aspose.Slides for Javaが必要です。プロジェクトに組み込む方法は次のとおりです。

**メイヴン:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**グレード:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

または、最新バージョンを直接ダウンロードすることもできます。 [Aspose.Slides for Java リリース](https://releases。aspose.com/slides/java/).

### 環境設定
開発環境が JDK 8 以降を使用するように構成されており、IDE が Maven または Gradle を使用して依存関係を管理するように設定されていることを確認します。

**ライセンス取得:**
- **無料トライアル**テスト目的で基本機能にアクセスします。
- **一時ライセンス**評価制限なしで高度な機能をテストします。
- **購入**長期の商用利用には、ライセンスの購入を検討してください。

## Aspose.Slides for Java のセットアップ
まず、JavaプロジェクトにAspose.Slidesライブラリを設定します。初期化と設定の手順は以下のとおりです。

1. 上記のように、Maven または Gradle 経由で依存関係を追加します。
2. 必要な Aspose.Slides パッケージをインポートします。
   ```java
   import com.aspose.slides.*;
   ```

3. 新しいものを初期化する `Presentation` 実例：
   ```java
   Presentation presentation = new Presentation();
   ```

このセットアップにより、プログラムによるプレゼンテーションの構築を開始できます。

## 実装ガイド

### プレゼンテーションでグラフを作成してカスタマイズする

#### 概要
グラフを作成するには、プレゼンテーションの初期化、スライドへのアクセス、タイプ、位置、サイズなどの特定の属性を持つグラフの追加が必要です。

**手順:**
1. **プレゼンテーションインスタンスの作成**まず、 `Presentation` クラス。
2. **アクセススライド**最初のスライドを取得するには `get_Item(0)`。
3. **チャートを追加**： 使用 `addChart()` 定義された寸法を持つ指定された座標に積み上げ縦棒グラフを追加します。

```java
// 機能: グラフを使ったプレゼンテーションを作成する
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### カテゴリの合計を計算する

#### 概要
カテゴリの合計を計算するには、グラフ内の各系列を反復処理して、カテゴリごとの値を合計する必要があります。

**手順:**
1. **配列の初期化**合計値を保持する配列を作成します。
2. **カテゴリとシリーズを反復処理する**ネストされたループを使用して、すべての系列から各カテゴリの合計を累積します。

```java
// 機能: グラフ内のカテゴリの合計を計算する
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### データをグラフ上のパーセンテージラベルとして表示する

#### 概要
この機能は、データ ラベルを構成して値をパーセンテージとして表示し、視覚化を明確にすることに重点を置いています。

**手順:**
1. **シリーズラベルの設定**フォント サイズや凡例キーの表示/非表示などのラベル プロパティを設定します。
2. **パーセンテージを計算する**カテゴリの合計値に基づいて各データ ポイントのパーセンテージを計算します。
3. **ラベルテキストの設定**ラベルを小数点 2 桁でパーセンテージを表示するようにフォーマットします。

```java
// 機能: チャート上にデータをパーセンテージラベルとして表示する
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### グラフ付きプレゼンテーションを保存

#### 概要
最後に、プレゼンテーションを PPTX 形式で指定したパスに保存します。

**手順:**
1. **保存方法**使用 `save()` 方法 `Presentation` 実例。
2. **リソースを処分する**保存後にリソースが解放されていることを確認します。

```java
// 機能: グラフ付きのプレゼンテーションを保存
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## 実用的な応用

1. **財務報告**グラフを使用して、部門全体の収益成長率を表示します。
2. **売上データ分析**パーセンテージ ラベルを使用して地域別の売上データを視覚化し、より明確な分析情報を提供します。
3. **教育プレゼンテーション**視覚的な統計を使用して学術的なプレゼンテーションを強化します。
4. **マーケティングキャンペーン**キャンペーンのパフォーマンス指標を魅力的なビジュアルとして表示します。
5. **ビジネス戦略会議**戦略計画の議論において複雑なデータをグラフを使用して伝えます。

## パフォーマンスに関する考慮事項
- **メモリ管理**：処分する `Presentation` オブジェクトをすぐに削除してリソースを解放します。
- **チャートの読み込みを最適化**可能な場合は、必須のグラフ要素のみをメモリに読み込みます。
- **バッチ処理**複数のプレゼンテーションを処理する場合は、リソースの消費を効率的に管理するために、それらをバッチで処理することを検討してください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}