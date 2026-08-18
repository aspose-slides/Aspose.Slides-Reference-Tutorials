---
date: '2026-06-13'
description: Aspose.Slides for Java を使用して動的な円グラフを作成し、Excel を PowerPoint に追加し、Excel
  から PowerPoint を生成する方法を学びます。
keywords:
- add excel to powerpoint
- generate powerpoint from excel
- import excel into powerpoint
- create pie chart java
- set chart data range
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  headline: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  type: TechArticle
- description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  name: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  steps:
  - name: Initialize Presentation
    text: '- **Purpose:** Creates an empty PowerPoint file in memory.'
  - name: Access First Slide
    text: '- **Explanation:** Retrieves the automatically created first slide.'
  - name: Add Pie Chart to Slide
    text: The `IChart` object represents a chart shape on a slide. - **Parameters:**
      Position (`x`, `y`) and size (`width`, `height`). - **Purpose:** Places a pie
      chart shape on the slide.
  - name: Define Document Directory
    text: '- Set this to the folder containing `book1.xlsx`.'
  - name: Open Workbook
    text: The `Workbook` class from Aspose.Cells loads an Excel file into memory.
      - **Purpose:** Reads the Excel file into memory.
  - name: Create ByteArrayOutputStream
    text: '`ByteArrayOutputStream` provides an in‑memory buffer for binary data. -
      **Purpose:** Provides an in‑memory stream for temporary storage.'
  - name: Save Workbook to Stream
    text: '- **Explanation:** Writes the workbook as an XLSX byte stream.'
  - name: Feed Data into Chart
    text: '- **Purpose:** Links the chart to the Excel data.'
  - name: Define Data Range
    text: The `setRange` method defines the Excel cells used as the chart’s data source.
      - **Explanation:** Points the chart to the exact range on *Sheet2*.
  - name: Configure Series Properties
    text: '- **Purpose:** Enables varied colors for each slice of the pie chart.'
  type: HowTo
- questions:
  - answer: Yes, but evaluation mode adds watermarks and limits some features. For
      production, obtain a temporary or full license.
    question: Can I use Aspose.Slides without a license?
  - answer: Use efficient resource management, split the presentation into smaller
      parts, and dispose of unused objects promptly.
    question: How do I handle large presentations in Aspose.Slides?
  - answer: PPTX, PDF, XPS, ODP, HTML, and image formats such as PNG, JPEG, and BMP.
    question: What file formats can Aspose.Slides export to?
  - answer: Absolutely. Load an existing file with `new Presentation("existing.pptx")`,
      modify slides/charts, then save.
    question: Is it possible to update an existing PowerPoint file instead of creating
      a new one?
  - answer: Yes – after retrieving the series, you can set `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);`
      and assign a `Color`.
    question: Does the library support setting custom colors for individual pie slices?
  type: FAQPage
title: 'Excel を PowerPoint に追加: Aspose.Slides for Java を使用した円グラフによる動的プレゼンテーション'
url: /ja/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Excel を PowerPoint に追加: Aspose.Slides for Java を使用したパイチャートによる動的プレゼンテーション

データ主導の現代環境において、**Excel を PowerPoint に追加** を迅速かつ確実に行い、視聴者が数値を視覚的に確認できるようにします。このチュートリアルでは、Excel から PowerPoint を生成し、Java でパイチャートを作成し、チャートのデータ範囲を設定する手順を Aspose.Slides for Java を使用して解説します。最後まで実行すれば、Excel ワークブックからライブデータを直接取得するプレゼンテーションが完成します。

## Quick Answers
- **What library creates charts in Java?** Aspose.Slides for Java.  
- **Can I pull Excel data directly into a PowerPoint chart?** Yes – use Aspose.Cells to read the workbook and feed it to the chart.  
- **Which chart type is demonstrated?** A pie chart.  
- **How do I set the data range for the chart?** By calling `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.  
- **What is the primary benefit of this approach?** Automates the “add Excel to PowerPoint” workflow, eliminating manual copy‑paste.

## **add Excel to PowerPoint** とは？
Excel を PowerPoint に追加することは、スプレッドシートのデータをプログラムでインポートし、スライド内で可視化することを意味します。これにより、元データは Excel のネイティブ形式のまま保持しつつ、洗練されたチャートとして提示でき、ワークブックの更新がプレゼンテーションに即座に反映されます。

## Aspose.Slides for Java で Excel から PowerPoint を生成する理由
Aspose.Slides for Java を使用して Excel から PowerPoint を生成すると、手動のコピー＆ペーストなしでワークブックから直接データを取得し、数秒でスライドデッキを作成できます。ライブラリは 50 以上の入出力形式をサポートし、ファイル全体をメモリに読み込むことなく数百ページのワークブックを処理でき、チャートのスタイル、色、データ範囲をプログラムから完全に制御できます。

## Aspose.Slides for Java を使用して Excel から PowerPoint を生成する方法
Aspose.Cells で Excel ワークブックを読み込み、`Presentation` を新規作成し、スライドにパイチャート形状を追加して、チャートをワークブックのデータ範囲にバインドします。数行の Java コードで、最新のスプレッドシート値を反映した完全な `.pptx` ファイルを生成できます。

## Aspose.Slides で Excel を PowerPoint にインポートする方法
Excel を PowerPoint にインポートするには、Excel ファイルを `Workbook` オブジェクトに読み込み、ワークブックをバイト配列に変換し、そのバイト配列をチャートのデータソースに渡します。チャートは指定された範囲を自動的に読み取り、ビジュアルがスプレッドシートと同期した状態を保ちます。

## Aspose.Slides for Java でチャートのデータ範囲を設定する方法
`chart.getChartData().setRange("SheetName!$StartCell:$EndCell")` メソッドを使用して、カテゴリと値が含まれる正確なセル範囲をチャートに指示します。この一呼び出しでデータソースとレイアウトの両方が定義され、手動でシリーズを構築する必要がなくなります。

## Prerequisites

開始する前に、以下を用意してください：

- **Java Development Kit (JDK) 1.8+** がインストールされていること。
- **Aspose.Slides for Java** と **Aspose.Cells for Java** ライブラリ（Maven、Gradle、または直接 JAR ダウンロード）。
- 可視化したいデータを含む Excel ワークブック（`book1.xlsx`）。
- 有効な Aspose ライセンス（評価用の無料トライアルでも可）。

### Required Libraries
以下の依存関係管理ツールのいずれかを使用してください：

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

または、[Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) から直接 JAR をダウンロードしてください。

### License Acquisition
- **Free Trial:** [Aspose ダウンロードページ](https://releases.aspose.com/slides/java/) で入手可能。  
- **Temporary License:** 評価制限なしでテストしたい場合は、[Aspose の一時ライセンスページ](https://purchase.aspose.com/temporary-license/) から取得してください。  
- **Purchase License:** 本番環境で Aspose 製品を使用するには、フルライセンスを購入してください。

## Setting Up Aspose.Slides for Java

プロジェクトに Aspose.Slides の依存関係を追加し（上記の Maven/Gradle スニペット参照）、ビルドツールを使用しない場合は JAR ファイルをクラスパスに配置してください。

### Basic Initialization and Setup
PowerPoint ファイルを表すコアクラスをインポートします：  
```java
import com.aspose.slides.Presentation;
```  

## Implementation Guide

以下は **create pie chart java**、**set chart data range**、**add Excel to PowerPoint** を単一フローで実装するステップバイステップのガイドです。

### Create and Add Chart to Presentation

**概要:** 新しいプレゼンテーションを初期化し、最初のスライドを取得し、パイチャートを挿入します。

#### Step 1: Initialize Presentation  
```java
Presentation pres = new Presentation();
```  
- **Purpose:** メモリ上に空の PowerPoint ファイルを作成します。

#### Step 2: Access First Slide  
```java
ISlide slide = pres.getSlides().get_Item(0);
```  
- **Explanation:** 自動的に作成された最初のスライドを取得します。

#### Step 3: Add Pie Chart to Slide  
`IChart` オブジェクトはスライド上のチャート形状を表します。  
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```  
- **Parameters:** 位置 (`x`, `y`) とサイズ (`width`, `height`)。  
- **Purpose:** スライド上にパイチャート形状を配置します。

### Load Workbook from File

**概要:** チャートのデータ元となる Excel ワークブックをロードします。

#### Step 1: Define Document Directory  
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```  
- `book1.xlsx` が格納されているフォルダーを指定してください。

#### Step 2: Open Workbook  
Aspose.Cells の `Workbook` クラスが Excel ファイルをメモリにロードします。  
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```  
- **Purpose:** Excel ファイルをメモリに読み込みます。

### Save Workbook to ByteArrayOutputStream

**概要:** ワークブックをバイト配列に変換し、Aspose.Slides が利用できるようにします。

#### Step 1: Create ByteArrayOutputStream  
`ByteArrayOutputStream` はバイナリデータ用のインメモリバッファを提供します。  
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```  
- **Purpose:** 一時的なストレージとしてインメモリストリームを提供します。

#### Step 2: Save Workbook to Stream  
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```  
- **Explanation:** ワークブックを XLSX バイトストリームとして書き出します。

### Write Workbook Data to Chart

**概要:** Excel のバイト配列をチャートのデータソースとして供給します。

#### Step 1: Feed Data into Chart  
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```  
- **Purpose:** チャートを Excel データにリンクします。

### Set Chart Data Range and Configure Series

**概要:** チャートが参照すべきセル範囲を定義し、視覚的なスタイリングを強化します。

#### Step 1: Define Data Range  
`setRange` メソッドはチャートのデータソースとして使用する Excel セルを指定します。  
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```  
- **Explanation:** *Sheet2* 上の正確な範囲をチャートに指示します。

#### Step 2: Configure Series Properties  
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```  
- **Purpose:** パイチャートの各スライスに異なる色を設定できるようにします。

### Save Presentation to File

**概要:** 完成したプレゼンテーションをディスクに永続化します。

#### Step 1: Define Output Path  
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```  
- 最終的な PowerPoint ファイルを保存したいフォルダーを選択してください。

#### Step 2: Save Presentation  
```java
pres.save(outPath, SaveFormat.Pptx);
```  
- **Explanation:** プレゼンテーションを `.pptx` ファイルとして書き出します。

## Practical Applications

1. **Business Reporting:** 月次売上スプレッドシートをワンクリックで洗練されたスライドデッキに変換。  
2. **Educational Tools:** 手動でチャートを作成する手間なく、教室での統計分布を提示。  
3. **Dashboard Integration:** Excel ワークブックからライブデータを取得するスライドベースのダッシュボードを自動生成。

## Performance Considerations

- **Memory Management:** `try‑with‑resources` を使用するか、`finally` ブロックでストリームを閉じてリークを防止してください。  
- **Large Datasets:** 必要な値を抽出した後は `Workbook.getWorksheets().clear()` などでデータを分割処理してください。  
- **Lazy Loading:** アプリ起動時にロードせず、チャートを埋めるときだけワークブックを読み込むようにします。

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| **Chart shows no data** | 範囲文字列がシート名とセルアドレス（`Sheet2!$A$1:$B$3`）と完全に一致しているか確認してください。 |
| **OutOfMemoryError** | `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` のようにストリームを速やかに解放してください。 |
| **License not applied** | 任意の Aspose クラスをインスタンス化する前にライセンスをロードします: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## Frequently Asked Questions

**Q: Can I use Aspose.Slides without a license?**  
A: Yes, but evaluation mode adds watermarks and limits some features. For production, obtain a temporary or full license.

**Q: How do I handle large presentations in Aspose.Slides?**  
A: Use efficient resource management, split the presentation into smaller parts, and dispose of unused objects promptly.

**Q: What file formats can Aspose.Slides export to?**  
A: PPTX, PDF, XPS, ODP, HTML, and image formats such as PNG, JPEG, and BMP.

**Q: Is it possible to update an existing PowerPoint file instead of creating a new one?**  
A: Absolutely. Load an existing file with `new Presentation("existing.pptx")`, modify slides/charts, then save.

**Q: Does the library support setting custom colors for individual pie slices?**  
A: Yes – after retrieving the series, you can set `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` and assign a `Color`.

## Resources
- **Documentation:** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **Download:** [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)
- **Purchase License:** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **Free Trial:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Temporary License:** [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**Last Updated:** 2026-06-13  
**Tested With:** Aspose.Slides 25.4 for Java (JDK 16) & Aspose.Cells 25.4  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [How to Update PowerPoint Chart Data Range Using Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)
- [How to add pie chart PowerPoint with Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}