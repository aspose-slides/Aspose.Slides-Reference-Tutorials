---
date: '2026-01-14'
description: 學習如何使用 Aspose.Slides for Java 將圖表匯出至 Excel，並在簡報中新增圓餅圖投影片。一步一步的教學與程式碼。
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: 使用 Aspose.Slides Java 將圖表匯出至 Excel
url: /zh-hant/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export Chart to Excel Using Aspose.Slides for Java

**掌握使用 Aspose.Slides for Java 的資料視覺化技巧**

在當今以資料為驅動的環境中，能夠直接從 Java 應用程式 **export chart to excel**，可將靜態的 PowerPoint 視覺化圖表轉換為可重複使用、可分析的資料集。無論您是需要產生報告、供應分析管線，或只是讓業務使用者在 Excel 中編輯圖表資料，Aspose.Slides 都能讓這一切變得簡單。本教學將帶您一步步建立圖表、加入圓餅圖投影片，並將圖表資料匯出至 Excel 活頁簿。

**您將學會：**
- 輕鬆載入與操作簡報檔案
- **Add pie chart slide** 以及其他圖表類型的加入方式
- **Export chart to excel**（從圖表產生 Excel）以供後續分析
- 設定外部活頁簿路徑以 **embed chart in presentation**，保持資料同步

讓我們立即開始吧！

## Quick Answers
- **主要目的為何？** 從 PowerPoint 投影片匯出圖表資料至 Excel 檔案。  
- **需要哪個版本的函式庫？** Aspose.Slides for Java 25.4 或更新版本。  
- **需要授權嗎？** 可使用免費試用版進行評估；正式上線需購買商業授權。  
- **可以加入圓餅圖投影片嗎？** 可以 — 教學中示範了如何加入 Pie 圓餅圖。  
- **最低 Java 16？** 是的，建議使用 JDK 16 或更高版本。

## How to export chart to excel using Aspose.Slides?
將圖表資料匯出至 Excel 的流程非常簡單：載入簡報、建立圖表，然後將圖表的活頁簿串流寫入檔案。以下步驟將從專案設定說明到最終驗證，完整示範整個過程。

## Prerequisites
在開始之前，請先確認您已備妥以下項目：

### Required Libraries and Versions
- **Aspose.Slides for Java** 版本 25.4 或更新

### Environment Setup Requirements
- Java Development Kit (JDK) 16 或更高
- 任一程式碼編輯器或 IDE，如 IntelliJ IDEA 或 Eclipse

### Knowledge Prerequisites
- 基本的 Java 程式設計能力
- 熟悉 Maven 或 Gradle 建置系統

## Setting Up Aspose.Slides for Java
要開始使用 Aspose.Slides，請透過 Maven 或 Gradle 將其加入專案。

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

### License Acquisition Steps
Aspose.Slides 提供免費試用授權，讓您探索完整功能。您亦可申請臨時授權或購買正式授權以延長使用期限。請依照以下步驟操作：
1. 前往 [Aspose Purchase page](https://purchase.aspose.com/buy) 取得授權。  
2. 若要使用免費試用版，請從 [Releases](https://releases.aspose.com/slides/java/) 下載。  
3. 前往此處申請臨時授權 [here](https://purchase.aspose.com/temporary-license/)。

取得授權檔案後，於 Java 應用程式中初始化授權：
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Implementation Guide

### Feature 1: Load Presentation
載入簡報是任何操作的第一步。

#### Overview
本功能示範如何使用 Aspose.Slides for Java 載入既有的 PowerPoint 檔案。

#### Step‑by‑Step Implementation
**Load Presentation**
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
**Explanation:**  
- `Presentation` 以 `.pptx` 檔案路徑初始化。  
- 請務必在使用完畢後釋放 `Presentation` 物件，以釋放原生資源。

### Feature 2: Add Pie Chart Slide
加入圖表能顯著提升資料呈現效果，許多開發者也常問 **how to add chart slide** 在 Java 中的作法。

#### Overview
本功能展示如何在簡報的第一張投影片加入 **pie chart slide**（即「加入圓餅圖投影片」的典型情境）。

#### Step‑by‑Step Implementation
**Add Pie Chart**
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
**Explanation:**  
- `addChart` 會插入一個圓餅圖。  
- 參數定義圖表類型以及在投影片上的位置與大小。

### Feature 3: Generate Excel from Chart
將圖表資料匯出讓您能 **generate excel from chart**，以進行更深入的分析。

#### Overview
本功能示範如何將簡報中的圖表資料匯出至外部 Excel 活頁簿。

#### Step‑by‑Step Implementation
**Export Data**
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
**Explanation:**  
- `readWorkbookStream` 取得圖表的活頁簿資料。  
- 透過 `FileOutputStream` 將位元組陣列寫入 `.xlsx` 檔案。

### Feature 4: Embed Chart in Presentation with External Workbook
將圖表連結至外部活頁簿，可讓您 **embed chart in presentation**，並保持資料同步。

#### Overview
本功能示範如何設定外部活頁簿路徑，使圖表能直接讀寫 Excel 檔案。

#### Step‑by‑Step Implementation
**Set External Workbook Path**
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
**Explanation:**  
- `setExternalWorkbook` 連結圖表與 Excel 檔案，允許在不重新建構投影片的情況下動態更新資料。

## Practical Applications
Aspose.Slides 為各種情境提供彈性解決方案：

1. **Business Reports:** 直接從 Java 應用程式產生含圖表的詳細報告。  
2. **Academic Presentations:** 使用互動式圓餅圖投影片提升課堂講解。  
3. **Financial Analysis:** **Export chart to excel** 以進行深入的財務模型建置。  
4. **Marketing Analytics:** 可視化行銷活動績效，並 **generate excel from chart** 提供分析團隊使用。

## Frequently Asked Questions

**Q: Can I use this approach with other chart types (e.g., Bar, Line)?**  
A: Absolutely. Replace `ChartType.Pie` with any other `ChartType` enum value.

**Q: Do I need a separate Excel library to read the exported file?**  
A: No. The exported `.xlsx` file is a standard Excel workbook that can be opened with any spreadsheet application.

**Q: How does the external workbook affect slide size?**  
A: Linking to an external workbook does not increase the PPTX file size significantly; the chart references the workbook at runtime.

**Q: Is it possible to update the Excel data and have the slide reflect changes automatically?**  
A: Yes. After calling `setExternalWorkbook`, any changes saved to the workbook will be reflected the next time the presentation is opened.

**Q: What if I need to export multiple charts from the same presentation?**  
A: Iterate over each slide’s chart collection, call `readWorkbookStream()` for each, and write to separate workbook files.

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides 25.4 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}