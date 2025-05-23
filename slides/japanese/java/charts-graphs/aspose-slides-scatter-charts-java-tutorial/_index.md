---
"date": "2025-04-17"
"description": "Aspose.Slides for Javaを使用して動的な散布図を作成する方法を学びましょう。カスタマイズ可能なグラフ機能でプレゼンテーションを強化しましょう。"
"title": "Aspose.Slides を使用して Java で散布図を作成およびカスタマイズする"
"url": "/ja/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides を使用して Java で散布図を作成およびカスタマイズする

Aspose.SlidesとJavaを使って動的な散布図を追加し、プレゼンテーションの質を高めましょう。この包括的なチュートリアルでは、ディレクトリの設定、プレゼンテーションの初期化、散布図の作成、グラフデータの管理、系列の種類とマーカーのカスタマイズ、そして作業内容の保存まで、すべて簡単に行えます。

**学習内容:**
- プレゼンテーションファイルを保存するためのディレクトリの設定
- Aspose.Slides を使用してプレゼンテーションを初期化および操作する
- スライドに散布図を作成する
- チャートシリーズのデータの管理と追加
- グラフ系列の種類とマーカーのカスタマイズ
- プレゼンテーションを変更して保存する

まず、必要な前提条件が満たされていることを確認しましょう。

## 前提条件

このチュートリアルを実行するには、次のものを用意してください。
- **Aspose.Slides for Java**バージョン25.4以降が必要です。
- **Java開発キット（JDK）**: JDK 8 以上が必要です。
- Java プログラミングに関する基本的な知識と、Maven または Gradle ビルド ツールに精通していること。

## Aspose.Slides for Java のセットアップ

コーディングを始める前に、次のいずれかの方法で Aspose.Slides をプロジェクトに統合します。

### メイヴン
この依存関係を `pom.xml` ファイル：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### グラドル
この行をあなたの `build.gradle` ファイル：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

または、最新のAspose.Slides for Javaを以下からダウンロードしてください。 [Aspose リリース](https://releases。aspose.com/slides/java/).

#### ライセンス取得
- **無料トライアル**30 日間の無料トライアルで機能をご確認ください。
- **一時ライセンス**延長テスト用の一時ライセンスを取得します。
- **購入**フルアクセスとサポートを受けるにはライセンスを購入してください。

次に、以下に示すように必要なインポートを追加して、Java アプリケーションで Aspose.Slides を初期化します。

## 実装ガイド

### ディレクトリの設定
まず、プレゼンテーションファイルを保存するためのディレクトリが存在することを確認してください。この手順により、ファイルの保存時にエラーが発生するのを防ぐことができます。

#### ディレクトリが存在しない場合は作成する
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // ディレクトリを作成する
    new File(dataDir).mkdirs();
}
```
このスニペットは指定されたディレクトリをチェックし、存在しない場合は作成します。 `File.exists()` 存在を確認し、 `File.mkdirs()` ディレクトリを作成します。

### プレゼンテーションの初期化

次に、散布図を追加するプレゼンテーション オブジェクトを初期化します。

#### プレゼンテーションを初期化する
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
ここ、 `new Presentation()` 空白のプレゼンテーションを作成します。最初のスライドにアクセスして直接操作します。

### チャート作成
次に、初期化したスライドに散布図を作成します。

#### スライドに散布図を追加する
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
このコードスニペットは、最初のスライドに滑らかな線で描かれた散布図を追加します。パラメータは、グラフの位置とサイズを定義します。

### チャートデータ管理
次に、既存のシリーズをクリアし、新しいシリーズを追加して、チャート データを管理してみましょう。

#### チャートシリーズの管理
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// チャートに新しいシリーズを追加する
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
このセクションでは、既存のデータをクリアし、散布図に 2 つの新しいシリーズを追加します。

### 散布図シリーズのデータポイントの追加
データを視覚化するために、散布図の各系列にポイントを追加します。

#### データポイントを追加する
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
私たちは `addDataPointForScatterSeries()` 最初の系列にデータポイントを追加します。パラメータはX値とY値を定義します。

### シリーズタイプとマーカーの変更
各シリーズのマーカーの種類とスタイルを変更して、グラフの外観をカスタマイズします。

#### カスタマイズシリーズ
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// 第2シリーズの修正
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
これらの変更により、シリーズの種類が直線とマーカーを使用するように調整されます。また、視覚的な区別を容易にするために、マーカーのサイズとシンボルも設定しました。

### プレゼンテーションの保存
最後に、すべての変更を加えたプレゼンテーションを保存します。

#### プレゼンテーションを保存する
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
使用 `SaveFormat.Pptx` ファイルを保存するPowerPoint形式を指定します。この手順は、すべての変更内容を保持するために非常に重要です。

## 実用的な応用
実際の使用例をいくつか紹介します。
1. **財務分析**散布図を使用して、時間の経過に伴う株価の傾向を表示します。
2. **科学研究**分析のための実験データ ポイントを表します。
3. **プロジェクト管理**リソースの割り当てと進捗メトリックを視覚化します。

Aspose.Slides をシステムに統合すると、レポート生成を自動化し、生産性と精度を向上させることができます。

## パフォーマンスに関する考慮事項
最適なパフォーマンスを得るには:
- 保存後にプレゼンテーションを破棄することでメモリ使用量を管理します。
- 大規模なデータセットには効率的なデータ構造を使用します。
- ループ内のリソースを大量に消費する操作を最小限に抑えます。

ベスト プラクティスにより、複雑なチャート操作でもスムーズな実行が保証されます。

## 結論
このチュートリアルでは、ディレクトリの設定、Aspose.Slides プレゼンテーションの初期化、散布図の作成とカスタマイズ、系列データの管理、マーカーの変更、作業内容の保存方法を学習しました。Aspose.Slides の機能をさらに詳しく知りたい場合は、アニメーションやスライドの切り替えといった高度な機能もぜひお試しください。

**次のステップ**さまざまなチャート タイプを試したり、これらのテクニックを大規模な Java プロジェクトに統合したりします。

## よくある質問

### マーカーの色を変更するにはどうすればよいですか?
マーカーの色を変更するには、 `series.getMarker().getFillFormat().setFillColor(ColorObject)`、 どこ `ColorObject` ご希望の色です。

### 散布図に 2 つ以上の系列を追加できますか?
はい、新しいシリーズとデータ ポイントを追加するプロセスを繰り返すことで、必要な数のシリーズを追加できます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}