---
date: '2026-02-09'
description: 學習如何使用 Aspose.Slides for Java 建立圖表並將圖表匯出至 Excel。掌握資料視覺化、商業報告投影片與活頁簿產生。
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: 如何使用 Aspose.Slides Java 創建圖表
url: /zh-hant/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

I'll produce final markdown.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Java 建立圖表

**掌握使用 Aspose.Slides for Java 的資料視覺化技巧**

在當今資料驅動的環境中，*如何程式化建立圖表* 是一項能將原始數字轉化為引人入勝視覺故事的技能。無論您是要製作商業報告投影片還是互動式分析儀表板，Aspose.Slides for Java 都能讓您直接在程式碼中產生、客製化並匯出圖表。本教學將教您如何建立圖表物件、將圖表資料匯出至 Excel，並將圖表連結至外部活頁簿，以實現無縫的資料管理。

## 快速答覆
- **需要哪個函式庫？** Aspose.Slides for Java（v25.4 以上）。  
- **可以將圖表資料匯出至 Excel 嗎？** 可以 – 使用 `readWorkbookStream()` 並將位元組寫入 *.xlsx* 檔案。  
- **需要哪個 Java 版本？** JDK 16 或更新版本。  
- **需要授權嗎？** 免費試用可用於評估；正式環境需購買永久授權。  
- **示範的圖表類型是什麼？** 圓餅圖，其他如長條圖、折線圖等亦可使用相同方式。

## 什麼是 Aspose.Slides for Java？
Aspose.Slides for Java 是一套純 Java API，讓開發者在不安裝 Microsoft Office 的情況下建立、編輯與轉換 PowerPoint 簡報。它支援完整的圖表類型、資料繫結與匯出功能，是 **data visualization java** 專案的理想選擇。

## 為什麼使用 Aspose.Slides 來建立圖表並匯出至 Excel？
- **不需安裝 Office** – 可在任何伺服器或雲端環境執行。  
- **豐富的圖表庫** – 數十種圖表類型，提供完整樣式控制。  
- **直接匯出 Excel** – 產生外部活頁簿供後續分析使用。  
- **效能導向** – 低記憶體佔用，處理大型簡報快速高效。

## 前置條件
在開始之前，請確保您已具備以下條件：

### 必要的函式庫與版本
- **Aspose.Slides for Java** 版本 25.4 或更新

### 環境設定需求
- Java Development Kit (JDK) 16 或更新  
- 任一開發工具，例如 IntelliJ IDEA、Eclipse，或您慣用的文字編輯器

### 知識前置條件
- 基本的 Java 程式設計能力  
- 熟悉 Maven 或 Gradle 建置工具

## 設定 Aspose.Slides for Java
使用您偏好的建置系統將函式庫加入專案。

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

或者，您也可以直接[下載最新版本](https://releases.aspose.com/slides/java/)。

### 取得授權步驟
Aspose.Slides 提供免費試用授權，讓您探索完整功能。您亦可申請臨時授權或購買永久授權。請依下列步驟操作：

1. 前往 [Aspose 購買頁面](https://purchase.aspose.com/buy) 取得授權。  
2. 若要使用免費試用，請從 [Releases](https://releases.aspose.com/slides/java/) 下載。  
3. 前往[此處](https://purchase.aspose.com/temporary-license/) 申請臨時授權。

取得授權檔案後，於 Java 應用程式中初始化：

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## 步驟說明

### 如何建立圖表 – 載入簡報
在新增或修改圖表前，首先必須載入既有的 PowerPoint 檔案。

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

**說明：**  
- `Presentation` 代表 PowerPoint 檔案。  
- 請務必呼叫 `dispose()` 以釋放本機資源。

### 如何建立圖表 – 在投影片中加入圓餅圖
接下來，我們將插入一個圓餅圖，適合顯示比例資料。

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

**說明：**  
- `addChart` 會將圖表插入第一張投影片。  
- 參數分別代表圖表類型、X/Y 位置與尺寸。

### 如何匯出圖表至 Excel – 匯出圖表資料
將圖表資料匯出讓分析師能在 Excel 中進一步處理，發掘更深入的洞見。

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

**說明：**  
- `readWorkbookStream()` 會將圖表底層的 Excel 活頁簿以位元組陣列形式取出。  
- 再將此位元組陣列寫入 `externalWorkbook1.xlsx`，即可得到可直接使用的 Excel 檔案。

### 如何建立圖表 – 設定外部活頁簿以支援動態資料
將圖表連結至外部活頁簿，可透過編輯 Excel 檔案即更新圖表。

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

**說明：**  
- `setExternalWorkbook` 會將圖表綁定至指定的 Excel 檔案，讓資料變更時圖表自動更新，無需重新產生投影片。

## 實務應用
Aspose.Slides 提供多元解決方案，適用於各種真實情境：

1. **商業報告投影片**：自動從資料管線產生季報績效圖表。  
2. **學術簡報**：將研究數據轉換為清晰視覺化圖表，免除手動製圖。  
3. **財務分析**：將圖表資料匯出至 Excel，供稽核人員驗證數字。  
4. **行銷分析**：視覺化活動指標，並與利害關係人共享可編輯的活頁簿。

## 常見問題與除錯
- **`FileNotFoundException`** – 請確認 `dataDir` 指向有效資料夾，且輸出路徑具寫入權限。  
- **記憶體洩漏** – 請務必在 `finally` 區塊中呼叫 `pres.dispose()`，釋放本機資源。  
- **圖表未顯示** – 請確保 `get_Item(0)` 的投影片索引實際存在。

## FAQ

**Q: 可以使用其他圖表類型（例如長條圖、折線圖）嗎？**  
A: 可以。將 `ChartType.Pie` 替換為其他 `ChartType` 列舉值，如 `ChartType.Bar` 或 `ChartType.Line`。

**Q: 建立圖表後，能否更新外部活頁簿？**  
A: 完全可以。直接修改 Excel 檔案，下一次開啟簡報時連結的圖表即會反映變更。

**Q: 匯出 Excel 功能需要額外授權嗎？**  
A: 不需要。Excel 匯出功能已包含在標準的 Aspose.Slides for Java 授權中。

**Q: 支援哪些 Java 版本？**  
A: Aspose.Slides for Java 支援 JDK 16 及以上版本；較舊版本可能可運作，但未經官方測試。

**Q: 如何將產生的 Excel 活頁簿嵌入 PPTX 檔案內？**  
A: 使用 `chart.getChartData().setExternalWorkbook(null)` 即可將活頁簿嵌入，或保留外部連結以支援動態更新。

---

**最後更新日期：** 2026-02-09  
**測試環境：** Aspose.Slides for Java 25.4（jdk16 classifier）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}