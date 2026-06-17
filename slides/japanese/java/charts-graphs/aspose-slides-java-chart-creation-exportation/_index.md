---
date: '2026-06-03'
description: Aspose.Slides for Java を使用して、チャートをExcelにエクスポートし、Javaでチャートを作成する方法を学びます。data
  visualization、business report slides、workbook generation をマスターしましょう。
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: チャートをExcelにエクスポートし、Aspose.Slidesでチャートを作成する
url: /ja/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Excelへチャートをエクスポートし、Aspose.Slidesでチャートを作成する

**Aspose.Slides for Javaでデータ可視化技術をマスターする**

今日のデータ主導の環境では、プログラムで *export chart to excel* を行うことは、生の数値を魅力的なビジュアルストーリーに変えるスキルです。ビジネスレポートのスライドデッキやインタラクティブな分析ダッシュボードを構築する場合でも、Aspose.Slides for Java はコードから直接チャートを生成、カスタマイズ、エクスポートする機能を提供します。このチュートリアルでは、チャートオブジェクトの作成方法、チャートデータをExcelにエクスポートする方法、外部ワークブックにチャートをリンクしてシームレスにデータ管理する方法を学びます。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Slides for Java (v25.4+)。  
- **チャートデータをExcelにエクスポートできますか？** はい – `readWorkbookStream()` を使用し、バイト列を *.xlsx* ファイルに書き込みます。  
- **必要なJavaバージョンはどれですか？** JDK 16 以上。  
- **ライセンスは必要ですか？** 無料トライアルで評価は可能ですが、本番環境では永続ライセンスが必要です。  
- **デモされているチャートタイプは何ですか？** 円グラフですが、同じ手法で棒グラフ、折れ線グラフなど他のチャートタイプにも適用できます。

## Aspose.Slides for Javaとは？
Aspose.Slides for Java は、Microsoft Office を使用せずに PowerPoint プレゼンテーションの作成、編集、変換を可能にする純粋な Java API です。スライド操作、チャート生成、フォーマット変換のための包括的なクラスセットを提供し、レポート自動化ソリューションを実現します。**50 以上のチャートタイプ**、完全なデータバインディング、直接的な Excel エクスポートをサポートし、**データ可視化 java** プロジェクトに最適です。

## なぜAspose.Slidesを使用してチャートを作成し、Excelにエクスポートするのか？
Excelへチャートを迅速かつ確実にエクスポートできます。Aspose.Slides は Office のインストール不要で、**50 以上の組み込みチャートスタイル** を提供し、標準サーバーハードウェア上で **300 MB のプレゼンテーションを 30 秒未満で処理** します。また、ネイティブな Excel ワークブック生成を備えているため、下流のアナリストが手動のコピー＆ペーストなしで生データを扱えます。

## 前提条件

### 必要なライブラリとバージョン
- **Aspose.Slides for Java** バージョン 25.4 以上（JDK 16+ 対応）

### 環境設定要件
- Java Development Kit (JDK) 16 以上  
- IntelliJ IDEA や Eclipse などの IDE（または好みのテキストエディタ）

### 知識の前提条件
- 基本的な Java プログラミングスキル  
- Maven または Gradle ビルドツールの使用経験

## Aspose.Slides for Javaの設定
お気に入りのビルドシステムを使用してプロジェクトにライブラリを追加します。

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

あるいは、[最新バージョンを直接ダウンロード](https://releases.aspose.com/slides/java/) してください。

### ライセンス取得手順
Aspose.Slides はフリートライアルライセンスで機能をフルに体験できます。臨時ライセンスの取得や、長期利用のための購入も可能です。以下の手順に従ってください。

1. ライセンス取得のために[Aspose購入ページ](https://purchase.aspose.com/buy)にアクセスしてください。  
2. 無料トライアルの場合は[リリース](https://releases.aspose.com/slides/java/)からダウンロードしてください。  
3. 臨時ライセンスは[こちら](https://purchase.aspose.com/temporary-license/)から申請してください。

ライセンスファイルを取得したら、Java アプリケーションで次のように初期化します：

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## ステップバイステップガイド

### チャートの作成方法 – プレゼンテーションのロード
チャートを追加または変更する前に既存の PowerPoint ファイルをロードします。`Presentation` クラスはメモリ上の PowerPoint ファイルを表し、スライド、シェイプ、チャートオブジェクトにアクセスできます。`new Presentation("input.pptx")` でファイルをロードし、`presentation.getSlides().get_Item(0)` で最初のスライドを取得します。ネイティブリソースを解放するため、必ず `finally` ブロックで `presentation.dispose()` を呼び出してください。

### チャートの作成方法 – スライドに円グラフを追加
比例データの表示に最適な円グラフを挿入します。`IChart` インターフェイスはチャート操作の主要エントリポイントで、`addChart` により対象スライドに新しいチャートを作成します。チャートタイプ (`ChartType.Pie`)、X/Y 座標、幅/高さを指定します。作成後は `ChartData` オブジェクトを通じてタイトル、凡例、データ系列をカスタマイズできます。

### Excelへのチャートエクスポート – チャートデータのエクスポート
チャートデータをエクスポートすると、アナリストが Excel で数値を操作でき、より深い洞察が得られます。`readWorkbookStream()` はチャートの基になる Excel ワークブックをバイト配列として返します。`chart.getChartData().readWorkbookStream()` を呼び出してワークブックを取得し、標準の Java I/O で `externalWorkbook1.xlsx` という名前のファイルに書き込みます。生成された Excel ファイルにはチャートで使用された正確なデータが含まれ、さらなる分析に利用できます。

### チャートの作成方法 – 動的データ用に外部ワークブックを設定
チャートを外部ワークブックにリンクすると、スライドを再構築せずにライブデータ更新が可能になります。`setExternalWorkbook()` は動的データ更新のためにチャートを外部 Excel ファイルにバインドします。`chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` を使用して外部ファイルをリンクします。Excel ワークブックを編集すると、次回プレゼンテーションを開いた際にチャートが自動的に変更を反映し、動的レポートシナリオをサポートします。

## 実用的な応用例
Aspose.Slides はさまざまな実世界シナリオに柔軟に対応します。

1. **ビジネスレポートスライド:** データパイプラインから四半期のパフォーマンスチャートを自動生成します。  
2. **学術プレゼンテーション:** 手動でチャートを作成せずに、研究データを明確な可視化に変換します。  
3. **財務分析:** 監査人が数値を検証できるようにチャートデータを Excel にエクスポートし、手作業エラーを削減します。  
4. **マーケティング分析:** キャンペーン指標を可視化し、ステークホルダーと編集可能なワークブックを共有して協働的な意思決定を促進します。  
5. **自動ダッシュボード生成:** チャート作成 API とスケジュールジョブを組み合わせ、毎朝最新のスライドデッキを生成します。

## 一般的な問題とトラブルシューティング
- **`FileNotFoundException`** – `dataDir` が有効なフォルダーを指しているか、出力パスが書き込み可能か確認してください。  
- **Memory leaks** – ネイティブリソースを解放するため、`finally` ブロックで必ず `presentation.dispose()` を呼び出してください。  
- **Chart not appearing** – スライドインデックス (`get_Item(0)`) が実際に存在するスライドと一致しているか、チャートのサイズがスライド境界内に収まっているか確認してください。  
- **Excel export produces empty file** – `readWorkbookStream()` を呼び出す前に、チャートにデータ系列が実際に含まれていることを確認してください。

## よくある質問

**Q: 同じコードで別のチャートタイプ（例：棒グラフ、折れ線グラフ）を使用できますか？**  
A: はい。`ChartType.Pie` を他の `ChartType` 列挙値（例：`ChartType.Bar` や `ChartType.Line`）に置き換えるだけです。

**Q: チャート作成後に外部ワークブックを更新することは可能ですか？**  
A: もちろんです。Excel ファイルを直接編集すれば、次回プレゼンテーションを開いたときにリンクされたチャートが変更を反映します。

**Q: Excel エクスポート機能に別途ライセンスが必要ですか？**  
A: いいえ。Excel エクスポート機能は標準の Aspose.Slides for Java ライセンスに含まれています。

**Q: サポートされている Java バージョンはどれですか？**  
A: Aspose.Slides for Java は JDK 16 以降をサポートしています。以前のバージョンでも動作する可能性がありますが、公式にはテストされていません。

**Q: 生成された Excel ワークブックを PPTX ファイルに埋め込むにはどうすればよいですか？**  
A: `chart.getChartData().setExternalWorkbook(null)` を使用してワークブックを埋め込むか、動的更新のために外部リンクを保持します。

**最終更新日:** 2026-06-03  
**テスト環境:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**作者:** Aspose  

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [JavaでAspose.Slidesを使用してチャートを作成 – 追加と検証](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Aspose.Slides JavaでPowerPointチャートからワークブックデータを復元](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides for JavaでPowerPointチャートのデータ範囲を更新する方法](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}