---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides 在 Java 簡報中建立和自訂圓環圖，包括設定環境和調整圖表美觀度。"
"title": "如何使用 Aspose.Slides 在 Java 中建立甜甜圈圖進行示範"
"url": "/zh-hant/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides 在 Java 中建立甜甜圈圖進行示範

## 介紹
創建具有視覺吸引力的簡報對於有效傳達訊息至關重要。圖表是增強對資料分佈理解的關鍵元素。本教學將指導您使用 Aspose.Slides for Java 創建可自訂的甜甜圈圖，從而輕鬆生成圖表並提供孔徑大小和定位等廣泛的自訂選項。

**您將學到什麼：**
- 設定 Aspose.Slides for Java
- 在簡報中建立和配置圓環圖
- 調整圖表美觀度，例如孔徑大小
- 使用新圖表儲存簡報

讓我們開始設定我們的環境！

## 先決條件
在開始之前，請確保您已滿足以下先決條件：

### 所需的庫和版本
若要使用 Aspose.Slides for Java，請透過 Maven 或 Gradle 將其包含在您的專案中，或直接下載。

#### 環境設定要求
- 可用的 Java 開發工具包 (JDK)，最好是版本 8 或更高版本。
- 整合開發環境 (IDE)，如 IntelliJ IDEA 或 Eclipse。

### 知識前提
熟悉 Java 和基本程式設計概念是有益的。 Maven 或 Gradle 的基本知識將有助於簡化設定過程。

## 設定 Aspose.Slides for Java
可以透過多種方式將 Aspose.Slides 合併到您的專案中：

**Maven：**
將此依賴項新增至您的 `pom.xml` 文件：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle：**
將其包含在您的 `build.gradle` 文件：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下載：**
或者，從下載最新版本 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

### 許可證獲取
- **免費試用**：先下載試用版來探索 Aspose.Slides 的功能。
- **臨時執照**：取得臨時許可證，以不受限制地擴展功能。
- **購買**：為了繼續使用，需要購買許可證。

一旦設定好庫並準備好環境，我們就可以繼續實現我們的圓環圖。

## 實施指南

### 建立圓環圖
使用 Aspose.Slides 建立帶有自訂圓環圖的簡報涉及幾個步驟。為了清楚起見，我們將其分解如下：

#### 初始化演示對象
首先創建一個 `Presentation` 類，代表您的 PowerPoint 文件。
```java
// 建立 Presentation 類別的實例來表示 PPTX 文檔
Presentation presentation = new Presentation();
```
此步驟初始化您的簡報，您可以在其中新增幻燈片和圖表。

#### 將圓環圖加入投影片
存取第一張投影片（或根據需要建立一張）並新增一個圓環圖：
```java
// 存取簡報中的第一張投影片
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // 位置為 (50, 50)，尺寸為 400x400
```
此程式碼片段在第一張投影片中新增了一個圓環圖。這些參數定義了它在投影片上的位置和尺寸。

#### 配置甜甜圈孔尺寸
要使圓環圖具有獨特的外觀，請調整孔的大小：
```java
// 將圓環圖的孔徑設定為 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```
在這裡，我們將孔的大小設為 90%，使其幾乎成為一個完整的圓形。根據您的設計需要調整此值。

#### 儲存簡報
配置圖表後，儲存簡報：
```java
// 將簡報以 PPTX 格式儲存到磁碟的指定目錄
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```
這行程式碼將您的變更寫入名為 `DoughnutHoleSize_out.pptx` 在您指定的目錄中。

#### 清理資源
最後，確保您處理了演示對象：
```java
// 處置演示對像以釋放資源
if (presentation != null) presentation.dispose();
```
此步驟對於資源管理和避免記憶體洩漏至關重要。

### 實際應用
環形圖用途廣泛。以下是它們大放異彩的一些場景：
1. **預算分配**：顯示預算在各部門之間的分配情況。
2. **調查結果**：將多項選擇題的答案視覺化。
3. **網站流量來源**：顯示來自不同來源的流量百分比。

### 性能考慮
使用 Aspose.Slides 時，請考慮以下提示以獲得最佳效能：
- 當不再需要物件時，透過處置物件來管理記憶體。
- 對大型資料集使用串流以最大限度地減少記憶體使用。
- 盡可能透過重複使用實例來優化您的程式碼。

## 結論
恭喜！您已經學習如何使用 Aspose.Slides for Java 建立和自訂圓環圖。本教程涵蓋了設定庫、為簡報新增圖表以及調整其外觀。

若要繼續探索 Aspose.Slides 的功能，請考慮嘗試其他圖表類型或深入了解演示自動化功能。

**後續步驟：**
- 嘗試不同的圖表配置。
- 探索其他 Aspose.Slides 文件以了解更多進階功能。

準備好創建自己的圓環圖了嗎？嘗試在您的下一個專案中實施此解決方案！

## 常見問題部分
1. **我可以調整圓環圖各部分的顏色嗎？**
   是的，您可以使用以下方式自訂段顏色 `chart.getChartData().getSeries(i).getDataPointsForBarChart().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid);` 設定實心填滿類型並指定所需的顏色。

2. **如何為圖表新增數據標籤？**
   使用 `chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category"));` 以及類似的方法以程式設計方式添加數據點和標籤。

3. **是否可以將圖表儲存為 PPTX 以外的格式？**
   絕對地！ Aspose.Slides 支援各種輸出格式，如 PDF、XPS 和 PNG 或 JPEG 等影像格式。

4. **如果我在儲存簡報時遇到錯誤怎麼辦？**
   確保您的目錄路徑正確並且您對指定位置具有寫入權限。檢查您使用的 Aspose.Slides 版本是否支援您嘗試儲存的檔案格式。

5. **我可以使用即時資料來源自動更新圖表嗎？**
   是的，透過將 API 或資料庫整合到您的 Java 應用程式中，您可以根據需要動態更新圖表資料並刷新簡報。

## 資源
- **文件**：探索詳細的 API 參考 [Aspose.Slides for Java](https://reference。aspose.com/slides/java/).
- **下載**：從取得最新的庫版本 [Aspose.Slides 發布](https://releases。aspose.com/slides/java/).
- **購買**：如需完全存取權限，請購買許可證 [Aspose 購買](https://purchase。aspose.com/buy).
- **免費試用**：在下載頁面免費試用 Aspose.Slides。
- **臨時執照**：獲得臨時許可證，以進行不受限制的延長測試。
- **支援**：有疑問嗎？訪問 [Aspose 論壇](https://forum.aspose.com/c/slides/11) 尋求幫助。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}