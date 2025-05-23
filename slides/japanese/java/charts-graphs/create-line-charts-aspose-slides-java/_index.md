---
"date": "2025-04-17"
"description": "Aspose.Slidesを使って、Javaでマーカー付きの折れ線グラフを作成する方法を学びましょう。このチュートリアルでは、グラフの作成、系列の追加、プレゼンテーションの効率的な保存方法について解説します。"
"title": "Aspose.Slides for Java を使用して、デフォルトのマーカー付きの折れ線グラフを作成する"
"url": "/ja/java/charts-graphs/create-line-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java を使用して、デフォルトのマーカー付きの折れ線グラフを作成する
## 導入
プレゼンテーション、レポート、ダッシュボードには、視覚的に魅力的で情報豊富なグラフの作成が不可欠です。ソフトウェア開発においてこのプロセスを自動化することで、時間を節約し、ドキュメント間の一貫性を確保できます。このチュートリアルでは、Aspose.Slides for Javaを使用してマーカー付きの折れ線グラフを作成する方法を説明します。
**Aspose.Slides for Java** は、Microsoft Officeをインストールすることなく、開発者がPowerPointプレゼンテーションをプログラムで操作できるようにする強力なライブラリです。スライドの作成、編集、エクスポートなどのタスクを簡素化するため、ドキュメントの自動生成に不可欠なツールとなっています。
**学習内容:**
- Aspose.Slides for Java を初期化する方法
- マーカー付き折れ線グラフを作成する手順
- グラフにシリーズとカテゴリを追加する
- グラフの凡例の設定
- プレゼンテーションを保存する
準備はできましたか？まずはすべてが準備できていることを確認しましょう。
## 前提条件
始める前に、開発環境の準備ができていることを確認してください。
1. **ライブラリと依存関係:**
   - Aspose.Slides for Java ライブラリ (バージョン 25.4 を推奨)
   - Java 開発キット (JDK) バージョン 16 以上
2. **環境設定:**
   - IDE は Maven または Gradle ビルド ツールをサポートしている必要があります。
   - 必要に応じて、有効なライセンス ファイルがあることを確認してください。
3. **知識の前提条件:**
   - Javaプログラミングの基本的な理解
   - Maven または Gradle を使用してプロジェクトをビルドすることに精通していること
これらが整ったら、プロジェクト用に Aspose.Slides を設定しましょう。
## Aspose.Slides for Java のセットアップ
Aspose.Slides for Javaを使用するには、プロジェクトに依存関係として含める必要があります。MavenとGradleのどちらを使用しているかによって、設定が若干異なります。
### メイヴン
次の依存関係を `pom.xml` ファイル：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### グラドル
これをあなたの `build.gradle` ファイル：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### 直接ダウンロード
または、最新バージョンを以下からダウンロードすることもできます。 [Aspose.Slides for Java リリース](https://releases。aspose.com/slides/java/).
**ライセンス取得手順:**
- 無料トライアルについては、 [無料トライアルページ](https://releases。aspose.com/slides/java/).
- 一時ライセンスを取得するには、 [一時ライセンスページ](https://purchase。aspose.com/temporary-license/).
- フルライセンスを購入するには [購入ポータル](https://purchase。aspose.com/buy).
**基本的な初期化:**
Java アプリケーションで Aspose.Slides を初期化する方法は次のとおりです。
```java
import com.aspose.slides.Presentation;
// 新しいプレゼンテーションオブジェクトを初期化する
Presentation pres = new Presentation();
```
それでは、チャートの作成に進みましょう。
## 実装ガイド
### 機能1: デフォルトマーカーを使用したチャート作成
このセクションでは、マーカー付きの折れ線グラフを作成する方法を説明します。この機能は、データの傾向を効果的に視覚化するために不可欠です。
#### 折れ線グラフの追加
マーカー付きの折れ線グラフを追加するには:
```java
import com.aspose.slides.*;
// 最初のスライドにアクセス
ISlide slide = pres.getSlides().get_Item(0);
// スライドの位置 (10, 10)、サイズ (400, 400) にマーカー付きの折れ線グラフを追加します。
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```
#### クリアリングシリーズとカテゴリー
新しく始めるには:
```java
// 既存のシリーズとカテゴリをクリアして、白紙の状態に戻す
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// さらに操作するためにチャートのデータワークブックを取得します
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```
### 機能2: シリーズとカテゴリの追加
意味のあるデータをグラフに取り込むには、シリーズとカテゴリを追加することが重要です。
#### 新しいシリーズの作成
「シリーズ 1」という名前の新しいシリーズを追加するには:
```java
// グラフに新しいシリーズを追加する
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// データ入力の最初のシリーズにアクセスする
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```
#### カテゴリとデータポイントの入力
カテゴリと対応するデータ ポイントを追加するには:
```java
// カテゴリ名とそれぞれのデータポイントを追加します
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// ヌルデータポイントを適切に処理する
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```
### 機能3: 2番目のシリーズの追加とデータポイントの入力
追加のシリーズを追加すると、グラフの深みが増します。
#### 2番目のシリーズの作成と入力
「シリーズ 2」を追加するには:
```java
// 「シリーズ2」という名前の別のシリーズを追加します
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// データ入力のための第2シリーズにアクセスする
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// 「シリーズ 2」のデータポイントを追加する
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```
### 機能4: グラフの凡例の設定
凡例を設定すると、グラフの読みやすさが向上します。
#### 凡例設定の調整
設定するには:
```java
// 凡例を有効にし、データポイントに重ねて表示されないように設定します
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```
### 機能5: プレゼンテーションの保存
チャートが完成したら、プレゼンテーションをファイルに保存します。
```java
try {
    // 変更したプレゼンテーションを指定されたディレクトリに保存します
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```
## 実用的な応用
1. **ビジネスレポート:**
   - 財務レポートでグラフを使用して、時間の経過に伴う傾向を表します。
2. **データ分析:**
   - 分析フェーズ中にデータ パターンと相関関係を視覚化します。
3. **教育資料:**
   - 学術的な講義やプレゼンテーションに役立つスライドを作成します。
4. **プロジェクト管理：**
   - 視覚的なチャート要素を使用してプロジェクトのタイムラインを強化します。
5. **マーケティングプレゼンテーション:**
   - グラフを使用して、販売傾向とキャンペーンの結果を効果的に紹介します。
## 結論
Aspose.Slidesを使用してJavaでマーカー付きの折れ線グラフを作成し、系列とカテゴリを追加し、凡例を設定し、プレゼンテーションを保存する方法を学習しました。これらのスキルは、様々なプロフェッショナルアプリケーションで動的なビジュアルコンテンツを作成する際に役立ちます。
Aspose.Slidesの機能についてさらに詳しく知りたい場合やコミュニティサポートが必要な場合は、 [公式文書](https://docs.aspose.com/slides/java/) または、Stack Overflow などのフォーラムに参加してください。
楽しいコーディングを！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}