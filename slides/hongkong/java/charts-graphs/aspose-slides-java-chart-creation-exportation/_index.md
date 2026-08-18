---
date: '2026-06-03'
description: 了解如何使用 Aspose.Slides for Java 將圖表匯出至 Excel 並建立 Java 圖表。掌握資料視覺化、商業報告投影片以及活頁簿產生。
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
title: 將圖表匯出至 Excel 並使用 Aspose.Slides 建立圖表
url: /zh-hant/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 匯出圖表至 Excel 並使用 Aspose.Slides 建立圖表

**掌握使用 Aspose.Slides for Java 的資料視覺化技巧**

在當今資料驅動的環境中，程式化 *export chart to excel* 是一項能將原始數字轉化為引人入勝視覺故事的技能。無論您是要製作商業報告投影片還是互動式分析儀表板，Aspose.Slides for Java 都能讓您直接在程式碼中產生、客製化與匯出圖表。本教學將教您如何建立圖表物件、將圖表資料匯出至 Excel，並將圖表連結至外部活頁簿，以實現無縫的資料管理。

## 快速解答
- **需要哪個函式庫？** Aspose.Slides for Java（v25.4 以上）。  
- **可以將圖表資料匯出至 Excel 嗎？** 可以 – 使用 `readWorkbookStream()` 並將位元組寫入 *.xlsx* 檔案。  
- **需要哪個 Java 版本？** JDK 16 或更高。  
- **需要授權嗎？** 免費試用版可用於評估；正式環境需購買永久授權。  
- **示範的是哪種圖表類型？** 圓餅圖，但相同方法亦適用於長條圖、折線圖等其他圖表類型。

## 什麼是 Aspose.Slides for Java？
Aspose.Slides for Java 是一套純 Java API，讓開發者在不安裝 Microsoft Office 的情況下建立、編輯與轉換 PowerPoint 簡報。它提供完整的類別集合，用於投影片操作、圖表產生與格式轉換，支援自動化報表解決方案。它支援 **50+ 種圖表類型**、完整的資料繫結與直接的 Excel 匯出，是 **data visualization java** 專案的理想選擇。

## 為什麼使用 Aspose.Slides 來建立圖表並匯出圖表至 Excel？
快速且可靠地將圖表匯出至 Excel。Aspose.Slides 免除 Office 安裝需求，提供 **超過 50 種內建圖表樣式**，且在標準伺服器硬體上可在 **30 秒內處理高達 300 MB 的簡報**。此外，它還支援原生的 Excel 活頁簿產生，讓下游分析師可直接使用原始數字，無需手動複製貼上。

## 前置條件
在開始之前，請確保您具備以下條件：

### 必要的函式庫與版本
- **Aspose.Slides for Java** 版本 25.4 或更新（支援 JDK 16+）

### 環境設定需求
- Java Development Kit (JDK) 16 或更高  
- 任一 IDE，例如 IntelliJ IDEA 或 Eclipse（或您偏好的文字編輯器）

### 知識前置條件
- 基本的 Java 程式設計能力  
- 熟悉 Maven 或 Gradle 建置工具

## 設定 Aspose.Slides for Java
使用您喜愛的建置系統將函式庫加入專案。

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

或者，您也可以直接 [download the latest version directly](https://releases.aspose.com/slides/java/)。

### 取得授權步驟
Aspose.Slides 提供免費試用授權讓您探索完整功能。您亦可申請臨時授權或購買正式授權以供長期使用。請依照以下步驟操作：

1. 前往 [Aspose Purchase page](https://purchase.aspose.com/buy) 取得授權。  
2. 若要取得免費試用版，請從 [Releases](https://releases.aspose.com/slides/java/) 下載。  
3. 前往此處申請臨時授權 [here](https://purchase.aspose.com/temporary-license/)。

取得授權檔案後，於 Java 應用程式中初始化：

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## 步驟說明

### 如何建立圖表 – 載入簡報
在新增或修改圖表前，先載入既有的 PowerPoint 檔案。  
`Presentation` 類別代表記憶體中的 PowerPoint 檔案，提供投影片、形狀與圖表物件的存取。使用 `new Presentation("input.pptx")` 載入檔案，然後透過 `presentation.getSlides().get_Item(0)` 取得第一張投影片。務必在 `finally` 區塊中呼叫 `presentation.dispose()` 以釋放原生資源。

### 如何建立圖表 – 在投影片上加入圓餅圖
插入圓餅圖以呈現比例資料。  
`IChart` 介面是圖表操作的主要入口；`addChart` 會在目標投影片上建立新圖表。提供圖表類型 (`ChartType.Pie`)、X/Y 座標以及寬度/高度。建立後，可透過 `ChartData` 物件自訂標題、圖例與資料系列。

### 如何匯出圖表至 Excel – 匯出圖表資料
將圖表資料匯出讓分析師能在 Excel 中進一步探討，從而獲得更深入的見解。  
`readWorkbookStream()` 會回傳圖表底層的 Excel 活頁簿位元組陣列。呼叫 `chart.getChartData().readWorkbookStream()` 取得活頁簿，並使用標準 Java I/O 將此陣列寫入名為 `externalWorkbook1.xlsx` 的檔案。產生的 Excel 檔案即包含圖表使用的完整資料，可直接進行後續分析。

### 如何建立圖表 – 設定外部活頁簿以支援動態資料
將圖表連結至外部活頁簿，可在不重新建立投影片的情況下即時更新資料。  
`setExternalWorkbook()` 會將圖表繫結至外部 Excel 檔案，以支援動態資料更新。使用 `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` 進行繫結。當 Excel 活頁簿被編輯後，下次開啟簡報時圖表會自動反映變更，適用於動態報表情境。

## 實務應用
Aspose.Slides 為各種真實情境提供彈性解決方案：

1. **商業報告投影片**：自動從資料管道產生季報績效圖表。  
2. **學術簡報**：將研究資料轉換為清晰的視覺化圖表，免除手動製圖。  
3. **財務分析**：將圖表資料匯出至 Excel 供稽核人員驗證，降低人工錯誤。  
4. **行銷分析**：視覺化活動指標，並與利害關係人共享可編輯的活頁簿以促進協作決策。  
5. **自動化儀表板產生**：結合圖表產生 API 與排程工作，每天早上產出最新的投影片套件。

## 常見問題與除錯
- **`FileNotFoundException`** – 確認 `dataDir` 指向有效資料夾且輸出路徑具寫入權限。  
- **記憶體洩漏** – 必須在 `finally` 區塊中呼叫 `presentation.dispose()` 以釋放原生資源。  
- **圖表未顯示** – 確認投影片索引 (`get_Item(0)`) 存在，且圖表尺寸在投影片範圍內。  
- **Excel 匯出產生空檔案** – 在呼叫 `readWorkbookStream()` 前，先確認圖表確實包含資料系列。

## 常見問答

**Q: 可以使用其他圖表類型（例如長條圖、折線圖）嗎？**  
A: 可以。將 `ChartType.Pie` 替換為其他 `ChartType` 列舉值，如 `ChartType.Bar` 或 `ChartType.Line`。

**Q: 圖表建立後，能否更新外部活頁簿？**  
A: 完全可以。直接修改 Excel 檔案，下一次開啟簡報時連結的圖表會自動反映變更。

**Q: Excel 匯出功能需要額外授權嗎？**  
A: 不需要。Excel 匯出功能已包含在標準的 Aspose.Slides for Java 授權中。

**Q: 支援哪些 Java 版本？**  
A: Aspose.Slides for Java 支援 JDK 16 及以上版本；較舊版本可能可運作，但未經官方測試。

**Q: 如何將產生的 Excel 活頁簿嵌入 PPTX 檔案內？**  
A: 使用 `chart.getChartData().setExternalWorkbook(null)` 以嵌入活頁簿，或保留外部連結以支援動態更新。

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

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

## 相關教學

- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Recover Workbook Data from PowerPoint Charts Using Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [How to Update PowerPoint Chart Data Range Using Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}