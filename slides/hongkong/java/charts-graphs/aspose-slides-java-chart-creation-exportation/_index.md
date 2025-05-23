---
"date": "2025-04-17"
"description": "學習使用 Java 中的 Aspose.Slides 建立和匯出圖表。透過逐步指南和程式碼範例掌握資料視覺化技術。"
"title": "Aspose.Slides Java&#58;建立和匯出資料視覺化圖表"
"url": "/zh-hant/java/charts-graphs/aspose-slides-java-chart-creation-exportation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides Java 建立和匯出圖表

**使用 Aspose.Slides for Java 掌握資料視覺化技術**

在當今數據驅動的環境中，有效的數據視覺化對於做出明智的決策至關重要。將圖表功能整合到您的 Java 應用程式中可以將原始資料轉換為引人入勝的視覺故事。本教學將指導您使用 Aspose.Slides for Java 建立和匯出圖表，確保您的簡報既資訊豐富又具有視覺吸引力。

**您將學到什麼：**
- 輕鬆載入和操作演示文件
- 在投影片中新增各種類型的圖表
- 將圖表資料無縫匯出到外部工作簿
- 設定外部工作簿路徑以實現高效率的資料管理

讓我們開始吧！

## 先決條件
在開始之前，請確保您已準備好以下設定：

### 所需的庫和版本
- **Aspose.Slides for Java** 版本 25.4 或更高版本

### 環境設定要求
- Java 開發工具包 (JDK) 16 或更高版本
- 程式碼編輯器或 IDE，例如 IntelliJ IDEA 或 Eclipse

### 知識前提
- 對 Java 程式設計有基本的了解
- 熟悉 Maven 或 Gradle 建置系統

## 設定 Aspose.Slides for Java
要開始使用 Aspose.Slides，您需要將其包含在您的專案中。方法如下：

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

或者，您可以 [直接下載最新版本](https://releases。aspose.com/slides/java/).

### 許可證取得步驟
Aspose.Slides 提供免費試用授權以探索其全部功能。您也可以申請臨時許可證或購買許可證以供延長使用。請依照以下步驟操作：
1. 訪問 [Aspose 購買頁面](https://purchase.aspose.com/buy) 獲得你的執照。
2. 如需免費試用，請從以下位置下載 [發布](https://releases。aspose.com/slides/java/).
3. 申請臨時執照 [這裡](https://purchase。aspose.com/temporary-license/).

取得許可證檔案後，請在 Java 應用程式中進行初始化：
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## 實施指南
### 功能 1：負載演示
載入簡報是任何操作任務的第一步。

#### 概述
此功能示範如何使用 Aspose.Slides for Java 載入現有的 PowerPoint 檔案。

#### 逐步實施
**將圖表新增至投影片**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // 設定文檔目錄的路徑
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // 載入現有簡報
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // 清理資源
        if (pres != null) pres.dispose();
    }
}
```
**解釋：**
- `Presentation` 使用你的路徑初始化 `.pptx` 文件。
- 始終丟棄 `Presentation` 反對免費資源。

### 功能 2：將圖表新增至投影片
新增圖表可以顯著增強資料呈現。

#### 概述
此功能顯示如何將圓餅圖新增至簡報的第一張投影片。

#### 逐步實施
**將圖表新增至投影片**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // 設定文檔目錄的路徑
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // 在位置 (50, 50) 增加一個圓餅圖，寬度為 400，高度為 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**解釋：**
- `addChart` 方法用於插入餅圖。
- 參數包括圖表的類型及其在投影片上的位置/大小。

### 功能 3：將圖表資料匯出到外部工作簿
匯出資料允許在 PowerPoint 之外進行進一步分析。

#### 概述
此功能示範如何將簡報中的圖表資料匯出到外部 Excel 工作簿。

#### 逐步實施
**匯出數據**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // 設定文檔目錄和輸出目錄的路徑
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // 存取第一張投影片的圖表
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // 定義外部工作簿的路徑
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // 將圖表資料匯出到 Excel 串流
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
**解釋：**
- `readWorkbookStream` 提取圖表數據。
- 使用以下方式將資料寫入 Excel 文件 `FileOutputStream`。

### 功能4：為圖表資料設定外部工作簿
將圖表連結到外部工作簿可以簡化資料管理。

#### 概述
此功能示範如何設定外部工作簿路徑來儲存圖表資料。

#### 逐步實施
**設定外部工作簿路徑**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // 設定文檔目錄的路徑
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // 存取第一張投影片的圖表
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // 定義並設定外部工作簿的路徑
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**解釋：**
- `setExternalWorkbook` 將圖表連結到 Excel 文件，允許動態資料更新。

## 實際應用
Aspose.Slides 為各種場景提供了多種解決方案：

1. **商業報告：** 直接從 Java 應用程式建立帶有圖表的詳細報告。
2. **學術報告：** 利用互動式圖表增強教育內容。
3. **財務分析：** 將財務資料匯出至 Excel 進行深入分析。
4. **行銷分析：** 使用動態圖表來直觀地展示活動效果。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}