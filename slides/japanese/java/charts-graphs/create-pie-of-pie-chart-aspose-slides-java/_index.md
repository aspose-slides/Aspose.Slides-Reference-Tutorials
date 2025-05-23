---
"date": "2025-04-17"
"description": "Aspose.Slides for Javaを使用して円グラフを作成およびカスタマイズする方法を学びます。このガイドでは、セットアップ、実装、そして実践的な応用例について説明します。"
"title": "Aspose.Slides を使って Java で円グラフを作成する - 総合ガイド"
"url": "/ja/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides を使って Java で円グラフを作成する: 包括的なガイド

## チャートとグラフ

### 導入

データビジュアライゼーションにおいて、円グラフはデータセット内の割合を表す直感的な方法です。しかし、一部のセグメントが他のセグメントよりも大幅に小さい複雑なデータセットを扱う場合、従来の円グラフは煩雑になり、解釈が困難になる可能性があります。Pie of Pieグラフは、小さなスライスを別のグラフに分割することでこの問題に対処し、読みやすさを向上させます。

このチュートリアルでは、Aspose.Slides for Java を使用して円グラフ（Pie of Pie Chart）を作成および操作する方法を学習します。環境設定、グラフの作成、データラベルや分割位置などのプロパティのカスタマイズ、そしてプレゼンテーションをPPTX形式で保存する方法を網羅しています。チュートリアルの最後には、実用的な応用方法とパフォーマンス向上のヒントを通して、これらの機能をマスターできます。

**学習内容:**
- Aspose.Slides for Java のセットアップ
- 円グラフの作成
- データラベルや分割設定などのグラフプロパティのカスタマイズ
- プレゼンテーションをディスクに保存する

始める準備はできましたか？まず前提条件を確認しましょう。

## 前提条件

円グラフを作成する前に、次のものを用意してください。

### 必要なライブラリ、バージョン、依存関係:
- **Aspose.Slides for Java**: PowerPoint プレゼンテーションをプログラムで管理するために不可欠です。

### 環境設定要件:
- お使いのマシンにJava開発キット（JDK）がインストールされていること。JDK 16以降の使用をお勧めします。
- IntelliJ IDEA、Eclipse、NetBeans などの統合開発環境 (IDE)。

### 知識の前提条件:
- Javaプログラミングの基本的な理解
- 依存関係管理のためのMavenまたはGradleの知識

## Aspose.Slides for Java のセットアップ

### インストール情報:

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

**直接ダウンロード**最新バージョンは以下からダウンロードできます [Aspose.Slides for Java リリース](https://releases。aspose.com/slides/java/).

### ライセンス取得手順:
- **無料トライアル**すべての機能を試すには、まず 30 日間のトライアルから始めてください。
- **一時ライセンス**拡張評価用の一時ライセンスをリクエストします。
- **購入**Aspose.Slides がニーズを満たす場合は、ライセンスの購入を検討してください。

### 基本的な初期化とセットアップ

プロジェクトにライブラリを設定したら、インスタンスを作成して初期化します。 `Presentation` クラス：

```java
Presentation presentation = new Presentation();
```

これで、スライドに様々なグラフを追加するための準備が整いました。次は、Pie of Pie Chart（円グラフの重ね合わせ）の実装に移りましょう。

## 実装ガイド

### 「円グラフの円グラフ」を作成する

#### 概要
まずインスタンスを作成します `Presentation` 最初のスライドに円グラフを追加します。このグラフは、小さなセグメントを2つ目の円グラフに分割することでデータを効果的に視覚化し、読みやすさを向上させます。

#### ステップ1: プレゼンテーションクラスのインスタンスを作成する
```java
// 新しいプレゼンテーションを作成する
ePresentation presentation = new Presentation();
```
このコードは、グラフを追加するプレゼンテーションを初期化します。

#### ステップ2: 最初のスライドに「円グラフ」を追加する
```java
// 最初のスライドに、位置 (50, 50)、サイズ (500x400) の円グラフを追加します。
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
ここでチャートの種類を指定します（`PieOfPie`) と、スライド上の位置および寸法を指定します。

#### ステップ3: データラベルを設定して系列の値を表示する
```java
// 値を表示するデータラベルを構成する
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
この手順により、円グラフの各セグメントに対応する値が表示されるようになり、データの迅速な解釈に役立ちます。

#### ステップ4: 2番目の円グラフのサイズと割合による分割を設定する
```java
// 二次円グラフのサイズを設定する
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// 円グラフをパーセンテージで分割する
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// 分割位置を設定する
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
これらの設定により、グラフを小さなセグメントに分割して表示する方法のカスタマイズが可能になり、閲覧者の明瞭性が向上します。

#### ステップ5: プレゼンテーションをPPTX形式でディスクに保存する
```java
// 出力ディレクトリを定義する
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// プレゼンテーションを保存します\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}