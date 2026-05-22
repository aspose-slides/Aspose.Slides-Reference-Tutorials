---
date: '2026-03-20'
description: Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションにクラスター化された縦棒グラフを追加し、PowerPoint
  グラフをカスタマイズし、データ系列グラフを挿入する方法を学びましょう。
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Aspose.Slides for Java を使用して PowerPoint にクラスター化された縦棒グラフを追加する方法
url: /ja/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPointでAspose.Slides for Javaを使用してクラスター化された縦棒グラフを追加する方法

## Introduction

**クラスター化された縦棒グラフ**をPowerPointのスライドに追加する必要があるとき、明確なビジュアルは生データをすぐに理解できるストーリーに変換します。PowerPointで手動で作成すると時間がかかりますが、特に多数のスライドをプログラムで生成する場合はなおさらです。**Aspose.Slides for Java** を使用すれば、数行のコードで PowerPoint のチャートを作成・カスタマイズし、データ系列を挿入できます。

このチュートリアルで学べること:
- Aspose.Slides for Java で新しい PowerPoint プレゼンテーションを初期化する方法
- **スライドにチャートを追加**し、クラスター化された縦棒グラフとして設定する方法
- **グループ化された縦棒グラフ**を作成するためにカテゴリのグルーピングレベルを定義する方法
- **データ系列チャートを挿入**してデータを正しく表示させる方法
- 完成したプレゼンテーションを PPTX ファイルとして保存する方法

コードに入る前に、必要なものがすべて揃っているか確認しましょう。

## Quick Answers
- **主要クラスは何ですか？** `Presentation`（`com.aspose.slides` パッケージ）
- **使用するチャートタイプは？** `ChartType.ClusteredColumn`
- **テストにライセンスは必要ですか？** 無料トライアルで動作しますが、ライセンスを取得すると評価制限が解除されます
- **サポートされている Java バージョンは？** JDK 16 以降（サンプルは JDK 16 を使用）
- **サンプルの実行方法は？** Maven/Gradle の依存関係を追加し、コンパイル後に `main` メソッドを実行

## “add clustered column chart” とは？

*クラスター化された縦棒グラフ*（別名：グループ化された縦棒グラフ）は、各カテゴリごとに複数のデータ系列を横に並べて表示し、グループ間の比較を容易にします。PowerPoint では、四半期ごとの売上、アンケート結果、または同一カテゴリ内で複数のデータセットを対比させたいシナリオに最適です。

## なぜ Aspose.Slides でクラスター化された縦棒グラフを追加するのか？

- **完全自動化** – 手作業なしで多数のスライドを生成
- **細かいカスタマイズ** – 色、ラベル、グルーピングレベルなどを自由に設定
- **クロスプラットフォーム** – Java が動作するすべての OS で利用可能
- **Office のインストール不要** – サーバーや CI パイプライン上で PPTX を生成

## Prerequisites

- **Aspose.Slides for Java** ライブラリ（最新バージョン推奨）  
- JDK 16 以上  
- Maven または Gradle（または JAR を手動で追加）  
- Java コードを実行できる IDE またはテキストエディタ  

## Setting Up Aspose.Slides for Java

以下のビルドスクリプトのいずれかを使用してプロジェクトにライブラリを追加します。

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

あるいは、[Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) から直接最新リリースをダウンロードしてください。

### License Acquisition

本番環境へデプロイする前にライセンスを取得してください:
- **無料トライアル** – 購入せずにすべての機能を試用  
- **一時ライセンス** – 短期間の拡張機能評価に利用  
- **フルライセンス** – 無制限に使用可能。取得は [Aspose の購入ページ](https://purchase.aspose.com/buy) から

## Implementation Guide

各ステップを順に解説しながら、**チャートの追加方法** と **PowerPoint チャートのカスタマイズ** を学びます。

### Initialize Presentation

まず `Presentation` オブジェクトを作成し、デフォルトスライドを取得します。

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Add Chart to Slide

次に `ClusteredColumn` タイプを使用して **スライドにチャートを追加** し、既定のデータをクリアします。

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Prepare Chart Data Workbook

チャートは内部のワークブックにデータを保持します。新規作成のためにクリアします。

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Add Categories with Grouping Levels

カテゴリにグルーピングレベルを設定すると **グループ化された縦棒グラフ** の効果が得られます。各カテゴリは論理的なグループに属せます。

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Add Data Series to Chart

ここで **データ系列チャート** エントリを挿入し、個別の縦棒として可視化します。

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Save Presentation with Chart

最後に PPTX ファイルをディスクに書き出します。

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Practical Applications

- **ビジネスレポート** – 地域別の四半期売上を比較  
- **学術研究** – テスト条件別の実験結果を表示  
- **プロジェクト管理** – 複数チームのタスク完了率を単一スライドで可視化  

## Performance Considerations

- **メモリ管理** – 使用後は大きなワークブックを解放  
- **バッチ処理** – ループ内で頻繁にチャートを更新しない。データを先に収集し、まとめて適用  
- **組み込み最適化** – 大規模ファイル向けに `Presentation.optimize()` などのメソッドを活用  

## Common Pitfalls & Tips

- **落とし穴:** 既存の系列/カテゴリをクリアせずに追加すると重複データになる  
  **対策:** 新規データを投入する前に必ず `clear()` を呼び出す  
- **落とし穴:** セルアドレスを `"c2"` と誤記（正しくは `"C2"`）  
  **対策:** セル参照は大文字小文字を区別しませんが、可読性のため統一する  
- **ヒント:** `setGroupingItem` を使用して意味のあるグループラベルを作成すると、凡例に自動的に表示されます  

## Frequently Asked Questions

**Q1: 複数の系列をチャートに追加するには？**  
A1: `ch.getChartData().getSeries().add()` を繰り返し呼び出し、各系列に固有の名前とデータポイントを指定します。

**Q2: Aspose.Slides のチャートでよくある問題は？**  
A2: データ範囲の不一致やワークブックセルの欠落が原因になることが多いです。すべてのカテゴリとデータポイントに対応するセルがあるか確認してください。

**Q3: 他のプログラミング言語でも Aspose.Slides は使えますか？**  
A3: はい、.NET、C++、Python など向けに同等のライブラリが提供されています。

**Q4: 既存のプレゼンテーション内のチャートを更新するには？**  
A4: プレゼンテーションをロードし、`slide.getShapes().get_Item(index)` でチャートを取得、必要に応じて系列や書式を変更します。

**Q5: Aspose.Slides のチャートタイプに制限はありますか？**  
A5: 幅広いチャートタイプをサポートしていますが、最新のドキュメントで追加・非推奨のタイプを確認してください。

## Resources

- **Documentation**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Download**: [Latest Releases](https://releases.aspose.com/slides/java/)  
- **Purchase**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial**: [Start Your Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary License**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum**: [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose