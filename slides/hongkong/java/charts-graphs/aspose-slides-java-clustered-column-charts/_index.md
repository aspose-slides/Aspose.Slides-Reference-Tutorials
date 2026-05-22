---
date: '2026-03-18'
description: 學習如何在 Java 中使用 Aspose.Slides 建立叢集柱狀圖、如何新增圖表、設定顏色，並將簡報儲存為 PPTX。一步一步的教學，附程式碼範例。
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
# 如何在 Java 中使用 Aspose.Slides 建立叢集柱狀圖

## 簡介
建立視覺上引人注目的資料呈現對於有衝擊力的商業簡報至關重要，而學習以程式方式 **建立叢集柱狀圖** 可以為您節省大量手動工作時間。在本教學中，您將看到 **如何加入圖表**、自動 **設定顏色**，以及最終使用 **Aspose.Slides for Java** **將簡報儲存為 PPTX**。我們將一步步說明所需的全部內容——從設定函式庫、加入圖表、客製化系列填色，到儲存檔案。

### 您將能完成的目標
- 安裝並設定 Aspose.Slides for Java  
- **在全新簡報中建立叢集柱狀圖**  
- 自動套用系列填色 (**how to set colors**)  
- **將簡報儲存為 PPTX** 至磁碟 (**how to save presentation**)  

在開始建立圖表之前，先先處理好先決條件。

## 快速答覆
- **主要類別是什麼？** `Presentation` 來自 `com.aspose.slides`  
- **如何加入圖表？** 在投影片的形狀集合上使用 `addChart(ChartType.ClusteredColumn, …)` (**how to add chart**)  
- **可以自動設定顏色嗎？** 可以，對每個系列呼叫 `setAutomaticSeriesColor(true)` (**how to set colors**)  
- **儲存使用哪種格式？** `SaveFormat.Pptx`（PowerPoint）(**save presentation as pptx**)  
- **需要授權嗎？** 試用版可用於測試；正式環境需購買完整授權  

## 先決條件
在開始之前，請確保您具備必要的工具與知識：

### 必要的函式庫與相依性
您需要 Aspose.Slides for Java 函式庫。請確保使用支援 JDK16 的 25.4 版。

### 環境設定需求
您的開發環境應支援 Java（建議使用 JDK16），且能以 Maven 或 Gradle 建置專案。

### 知識先決條件
熟悉基本的 Java 程式設計、透過 Maven/Gradle 使用函式庫，以及了解 PowerPoint 簡報將會很有幫助。

## 設定 Aspose.Slides for Java
要將 Aspose.Slides 整合至您的專案，請依照以下設定說明操作：

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

**Direct Download**  
若偏好直接下載，請前往 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)。

### 授權取得步驟
- **免費試用**：先使用免費試用版探索功能。  
- **臨時授權**：取得臨時授權以無限制測試。  
- **購買**：持續使用時，請購買完整授權。

**基本初始化與設定**  
依照以下方式初始化 Aspose.Slides：
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## 如何加入叢集柱狀圖
加入圖表是第一個功能步驟。本節說明如何使用 API **加入圖表**。

### 功能 1：建立叢集柱狀圖
讓我們使用 Aspose.Slides for Java 建立叢集柱狀圖。此功能讓您輕鬆在投影片中加入視覺吸引的圖表。

#### 概觀
在本節，我們將初始化新簡報，並在第一張投影片插入叢集柱狀圖。

**步驟 1：初始化 Presentation**  
建立 `Presentation` 物件以開始處理 PowerPoint 檔案：
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**步驟 2：加入叢集柱狀圖**  
在指定座標 (100, 50) 與尺寸 (600 × 400) 處加入圖表：
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

**步驟 3：清理資源**  
務必釋放資源以防止記憶體洩漏：
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## 如何為圖表設定顏色
透過自動套用系列填色 (**how to set colors**) 提升視覺效果。

### 功能 2：設定自動系列填色
自動為每個圖表的系列設定顏色，以獲得一致的外觀。

#### 概觀
自動為每個圖表的系列設定顏色，以獲得一致的外觀。

**步驟 1：存取圖表並遍歷系列**  
建立圖表後，存取圖表並遍歷其系列：
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```

**步驟 2：資源管理**  
完成後釋放 Presentation 物件：
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## 如何將簡報儲存為 PPTX
圖表完成後，您會想要將檔案永久保存 (**how to save presentation**)。

### 功能 3：將簡報儲存至磁碟
最後，使用 Aspose.Slides 輕鬆儲存您的工作。

#### 概觀
將編輯好的簡報儲存為所需格式與位置。

**步驟 1：定義輸出路徑**  
指定要儲存檔案的位置：
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**步驟 2：儲存簡報**  
使用 `Presentation` 物件的 `save` 方法：
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## 實務應用
- **財務報告**：清晰呈現季營收。  
- **行銷資料分析**：以引人注目的視覺展示活動成果。  
- **專案管理**：在團隊會議中以視覺方式追蹤里程碑與進度。

## 效能考量
使用 Aspose.Slides 時，請考慮以下最佳實踐：

- 即時釋放 `Presentation` 物件，以有效管理記憶體。  
- 儲存簡報時優化檔案大小，以節省磁碟空間。  
- 使用高效的資料結構儲存圖表系列，以提升效能。

## 結論
恭喜！您已學會如何使用 Aspose.Slides for Java **建立叢集柱狀圖**、自動 **設定顏色**，以及 **將簡報儲存為 PPTX**。此技能不僅提升簡報品質，也簡化視覺化資料呈現的流程。

**下一步：**  
探索更多功能，例如自訂圖表元素、加入資料標籤，或與外部資料來源整合，以擴充專案能力。

## 常見問答
1. **如何為特定 JDK 版本安裝 Aspose.Slides？**  
   - 如設定說明所示，於 Maven/Gradle 相依性中指定 `classifier`。  
2. **如果簡報無法正確儲存該怎麼辦？**  
   - 確認您對輸出目錄具有寫入權限，且檔案路徑正確。  
3. **我可以使用 Aspose.Slides for Java 建立其他類型的圖表嗎？**  
   - 當然可以！探索 `ChartType` 的選項，如圓餅圖、長條圖或折線圖。  
4. **如何在圖表中處理大量資料集？**  
   - 優化資料結構，並考慮在視覺化前先行前處理資料。  
5. **在哪裡可以找到更多 Aspose.Slides for Java 的範例？**  
   - 前往 [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) 取得完整指南與程式碼範例。

## 資源
- **文件**： [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **下載**： [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **購買**： [Buy a License](https://purchase.aspose.com/buy)  
- **免費試用**： [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **臨時授權**： [Request Here](https://purchase.aspose.com/temporary-license/)  
- **支援**： [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-03-18  
**Tested With:** Aspose.Slides 25.4 (JDK16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}