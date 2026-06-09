---
date: '2026-02-27'
description: 學習如何使用 Aspose.Slides for Java 在 PowerPoint 中加入直方圖圖表，並自動化圖表建立，以快速載入及修改簡報。
keywords:
- automate histogram charts PowerPoint
- Aspose.Slides for Java tutorial
- add histogram chart in PowerPoint
title: 如何在 PowerPoint 中使用 Aspose.Slides 添加直方圖圖表
url: /zh-hant/java/charts-graphs/automate-histogram-charts-ppt-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 PowerPoint 中使用 Aspose.Slides 添加直方圖圖表

## 介紹
在當今以資料為驅動的世界中，製作視覺吸引力的簡報至關重要，而圖表是此過程的核心要素。**如何自動加入直方圖** 可以為您節省大量手動操作時間，並避免錯誤。在本教學中，您將學會如何載入 PowerPoint 檔案、修改投影片、加入直方圖圖表、設定水平軸，最後儲存 PowerPoint 檔案——全部使用 Aspose.Slides for Java。

### 快速回答
- **哪個函式庫最方便？** Aspose.Slides for Java  
- **使用哪種圖表類型？** 直方圖 (Histogram)  
- **可以載入既有 PPTX 嗎？** 可以 – 使用 `Presentation` 開啟任何檔案  
- **如何設定軸線？** `setAggregationType(AxisAggregationType.Automatic)`  
- **需要授權嗎？** 試用版可供評估；正式環境需購買完整授權  

## 什麼是直方圖？
直方圖透過將數值資料分組為區間（bins）來視覺化其分佈情形。它非常適合在 PowerPoint 投影片中直接顯示頻率、績效範圍或任何統計分布。

## 為什麼要自動化產生直方圖？
- **速度：** 只需數秒即可產生數十張圖表，而非數分鐘。  
- **一致性：** 每張圖表皆遵循相同的樣式與軸線設定。  
- **可擴充性：** 適合批次處理報告、儀表板或定期簡報。  

## 前置條件
- **Aspose.Slides for Java** – 版本 25.4 或更新。  
- **JDK** 16 或以上。  
- IntelliJ IDEA 或 Eclipse 等 IDE。  
- Maven 或 Gradle 以管理相依性。  

### 必要的函式庫、版本與相依性
- **Aspose.Slides for Java**：版本 25.4 或更新。  
- **JDK**：16+。  

### 環境設定需求
- 整合開發環境 (IDE) – IntelliJ IDEA 或 Eclipse。  
- 如需自動化相依性管理，請安裝 Maven 或 Gradle。  

### 知識前提
- 基本的 Java 程式設計。  
- 熟悉 PowerPoint 檔案結構與圖表概念。  

## 設定 Aspose.Slides for Java
使用您慣用的建置工具將 Aspose.Slides 整合至專案。

**Maven：**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle：**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

若偏好直接下載，請前往 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 頁面。

### 取得授權步驟
1. **免費試用** – 取得臨時授權以探索完整功能。  
2. **臨時授權** – 在 Aspose 官網申請短期金鑰。  
3. **購買** – 從 [Aspose purchase page](https://purchase.aspose.com/buy) 取得永久授權。  

**基本初始化：**

```java
// Import Aspose.Slides package
import com.aspose.slides.*;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides License
        License license = new License();
        license.setLicense("path/to/your/license/file.lic");
        
        System.out.println("Aspose.Slides for Java initialized successfully!");
    }
}
```

## 實作指南
以下提供逐步說明，涵蓋 **載入 PowerPoint 簡報**、**修改投影片**、**加入直方圖圖表**、**設定水平軸**，以及 **儲存 PowerPoint 檔案**。

### 載入與修改 PowerPoint 簡報
**如何載入 PowerPoint 檔案並存取第一張投影片：**

```java
// Import Aspose.Slides package
import com.aspose.slides.*;

public class LoadModifyPresentation {
    public static void main(String[] args) {
        // Load the presentation file
        Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
        try {
            // Access the first slide
            ISlide slide = pres.getSlides().get_Item(0);
            
            System.out.println("Loaded slide: " + slide.getSlideNumber());
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

*說明：* `Presentation` 物件會開啟 PPTX，`get_Item(0)` 取得第一張投影片。完成後務必呼叫 `dispose()` 釋放原生資源。

### 在投影片中加入直方圖圖表
**如何在已載入的投影片上加入直方圖圖表：**

```java
public class AddHistogramChart {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            
            // Add a histogram chart at specified position and size
            IChart chart = slide.getShapes().addChart(
                ChartType.Histogram, 50, 50, 500, 400);
            
            System.out.println("Histogram chart added to the slide.");
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

*說明：* `addChart` 會建立類型為 `ChartType.Histogram` 的新圖表。數值代表圖表在投影片上的 X‑Y 位置與寬高。

### 設定圖表資料工作簿並加入系列
**如何為直方圖填入資料點：**

```java
public class ConfigureChartData {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(
                ChartType.Histogram, 50, 50, 500, 400);
            
            // Access and clear the data workbook
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            
            // Add series with data points
            IChartSeries series = chart.getChartData().getSeries().add(
                ChartType.Histogram);

            series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
            series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
            // Add more data points as needed
            
            System.out.println("Data series configured and added.");
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

*說明：* `IChartDataWorkbook` 如同圖表背後的 Excel 工作表。我們先清除既有資料，然後新增系列並填入數值。

### 設定水平軸並儲存簡報
**如何為水平軸設定彙總類型，並將檔案寫入磁碟：**

```java
public class FinalizeAndSave {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(
                ChartType.Histogram, 50, 50, 500, 400);
            
            // Configure horizontal axis
            chart.getAxes().getHorizontalAxis().setAggregationType(
                AxisAggregationType.Automatic);
            
            // Save the presentation
            pres.save("YOUR_OUTPUT_DIRECTORY/Histogram.pptx", SaveFormat.Pptx);
            
            System.out.println("Presentation saved successfully!");
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

*說明：* 設定 `AggregationType.Automatic` 後，Aspose 會自動將資料分組為適當的區間，使直方圖更易閱讀。最後的 `save` 呼叫會將 PPTX 寫入磁碟。

## 實務應用
以下列出幾個 **自動化圖表產生** 發揮效益的真實情境：

1. **商業報告** – 為季報簡報產生銷售分佈直方圖。  
2. **學術研究** – 直接在教學投影片中視覺化實驗資料集。  
3. **資料分析會議** – 快速將原始 CSV 資料轉換為精緻的直方圖，供利害關係人審閱。  

## 常見問題與解決方案
- **缺少授權錯誤：** 確認 `.lic` 檔案路徑正確，且授權版本與 Aspose.Slides 函式庫相符。  
- **圖表未顯示：** 檢查投影片尺寸是否足夠，必要時調整 `addChart` 的大小參數。  
- **資料被覆寫：** 在填入新資料前務必呼叫 `wb.clear(0)`，避免遺留舊值。  

## 常見問答

**Q: 可以在同一份簡報中加入多個直方圖圖表嗎？**  
A: 可以。對任何投影片呼叫 `addChart` 多次，每次使用獨立的資料系列。

**Q: Aspose.Slides 支援除直方圖外的其他圖表類型嗎？**  
A: 當然支援。它支援折線圖、長條圖、圓餅圖、散佈圖等多種圖表類型。

**Q: 能否自訂直方圖的樣式（顏色、字型）？**  
A: 能。建立圖表後，可透過 `chart.getChartData().getSeries()` 取得系列，並修改填色、字型等格式屬性。

**Q: 若需要載入受密碼保護的 PPTX，該怎麼做？**  
A: 使用 `Presentation(String fileName, LoadOptions options)` 建構子，並在 `LoadOptions` 中設定密碼。

**Q: 這個方法能處理 .ppt（舊版）檔案嗎？**  
A: Aspose.Slides 能讀寫 `.ppt` 與 `.pptx` 兩種格式，只需在 `save` 方法中更改檔案副檔名即可。

---

**最後更新日期：** 2026-02-27  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}