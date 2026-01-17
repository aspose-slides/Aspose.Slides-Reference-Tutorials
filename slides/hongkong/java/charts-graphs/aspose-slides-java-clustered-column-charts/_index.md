---
date: '2026-01-17'
description: 學習如何在 Java 中使用 Aspose.Slides 建立叢集柱狀圖。此逐步指南說明如何新增圖表、設定顏色以及儲存簡報。
keywords:
- create clustered column chart
- aspose slides java tutorial
- clustered column chart java
title: 如何在 Java 中使用 Aspose.Slides 建立叢集柱狀圖
url: /zh-hant/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Java 使用 Aspose.Slides 建立群組直條圖

## 介紹
在商務簡報中呈現視覺化的資料圖表相當重要，學會 **如何以程式方式建立群組直條圖** 能為您節省大量手動製作的時間。本步驟指南將說明如何使用 **Aspose.Slides for Java** 快速建立與樣式化群組直條圖，讓您的簡報輕鬆呈現專業視覺效果。

我們將從設定函式庫、加入圖表、客製化系列顏色，到最後儲存檔案，完整說明所需的每一步。

### 您將學會的內容
- 安裝與設定 Aspose.Slides for Java  
- 在全新簡報中 **建立群組直條圖**  
- 自動套用系列填色  
- 將簡報儲存至磁碟  

在開始建立圖表前，先確認先決條件！

## 快速答疑
- **主要類別是什麼？** `Presentation`（位於 `com.aspose.slides`）  
- **如何加入圖表？** 在投影片的 shape 集合上使用 `addChart(ChartType.ClusteredColumn, ...)`  
- **可以自動設定顏色嗎？** 可以，對每個系列呼叫 `setAutomaticSeriesColor(true)`  
- **儲存使用哪種格式？** `SaveFormat.Pptx`（PowerPoint）  
- **需要授權嗎？** 測試可使用試用版，正式環境需購買正式授權  

## 先決條件
在開始之前，請確保您具備以下工具與知識：

### 必要的函式庫與相依性
您需要 Aspose.Slides for Java 函式庫，建議使用支援 JDK16 的 25.4 版。

### 環境設定需求
開發環境須支援 Java（建議 JDK16），並能使用 Maven 或 Gradle 進行專案建置。

### 知識前置
具備基本的 Java 程式撰寫經驗、熟悉 Maven/Gradle 取得函式庫，以及了解 PowerPoint 簡報的概念，將有助於學習本教學。

## 設定 Aspose.Slides for Java
將 Aspose.Slides 整合至您的專案，請依照以下說明操作：

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

**直接下載**  
若偏好手動下載，請前往 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)。

### 取得授權步驟
- **免費試用**：先取得免費試用版以探索功能。  
- **臨時授權**：取得臨時授權以在無限制的情況下測試。  
- **購買授權**：長期使用請購買正式授權。

**基本初始化與設定**  
以下示範如何初始化 Aspose.Slides：  
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## 實作指南

### 功能 1：建立群組直條圖
使用 Aspose.Slides for Java 建立群組直條圖，讓您輕鬆在投影片中加入視覺化圖表。

#### 概觀
本節將說明如何建立新簡報，並在第一張投影片插入群組直條圖。

**步驟 1：初始化簡報**  
建立 `Presentation` 物件以開始操作 PowerPoint 檔案：  
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**步驟 2：加入群組直條圖**  
在座標 (100, 50) 並以尺寸 (600 × 400) 插入圖表：  
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

**步驟 3：清理資源**  
務必釋放資源以避免記憶體泄漏：  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

### 功能 2：設定自動系列填色
透過自動設定系列填色提升圖表的視覺一致性。

#### 概觀
自動為每個系列套用顏色，使圖表外觀更協調。

**步驟 1：取得圖表並遍歷系列**  
建立圖表後，存取圖表物件並遍歷其系列：  
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```

**步驟 2：資源管理**  
完成後釋放 `Presentation` 物件：  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

### 功能 3：將簡報儲存至磁碟
最後，使用 Aspose.Slides 輕鬆將編輯好的簡報儲存。

#### 概觀
將簡報以指定格式與路徑儲存。

**步驟 1：定義輸出路徑**  
指定要儲存檔案的位置：  
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**步驟 2：儲存簡報**  
呼叫 `Presentation` 物件的 `save` 方法：  
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## 實務應用
- **財務報表**：清晰呈現季報盈餘。  
- **行銷資料分析**：以吸睛圖表展示活動成效。  
- **專案管理**：在團隊會議中以圖形方式追蹤里程碑與進度。

## 效能考量
使用 Aspose.Slides 時，請留意以下最佳實踐：

- 及時釋放 `Presentation` 物件以管理記憶體。  
- 儲存簡報時優化檔案大小，節省磁碟空間。  
- 使用高效的資料結構儲存圖表系列，以提升效能。

## 結論
恭喜您！您已學會如何 **建立群組直條圖** 並使用 Aspose.Slides for Java 為其樣式化。此技能不僅能提升簡報品質，也能簡化資料視覺化的流程。

**後續步驟：**  
探索更多功能，例如自訂圖表元素、加入資料標籤，或與資料來源整合，進一步擴充專案能力。

## 常見問題
1. **如何在特定 JDK 版本上安裝 Aspose.Slides？**  
   - 在 Maven/Gradle 相依性中指定 `classifier`，如設定說明所示。  
2. **簡報無法正確儲存時該怎麼辦？**  
   - 確認輸出目錄具有寫入權限，且檔案路徑正確。  
3. **可以使用 Aspose.Slides for Java 建立其他類型的圖表嗎？**  
   - 當然可以！請參考 `ChartType` 中的 Pie、Bar、Line 等選項。  
4. **圖表資料量很大時該如何處理？**  
   - 優化資料結構，並在視覺化前先行前處理資料。  
5. **在哪裡可以找到更多 Aspose.Slides for Java 的範例？**  
   - 前往 [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) 瀏覽完整教學與程式碼範例。

## 資源
- **文件**： [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **下載**： [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **購買**： [Buy a License](https://purchase.aspose.com/buy)  
- **免費試用**： [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **臨時授權**： [Request Here](https://purchase.aspose.com/temporary-license/)  
- **支援**： [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**最後更新：** 2026-01-17  
**測試環境：** Aspose.Slides 25.4 (JDK16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}