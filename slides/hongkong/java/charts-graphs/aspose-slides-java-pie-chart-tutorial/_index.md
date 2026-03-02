---
date: '2026-03-02'
description: 學習如何將 Excel 加入 PowerPoint，並透過使用 Aspose.Slides for Java 建立動態圓餅圖，從 Excel
  產生 PowerPoint。
keywords:
- Aspose.Slides for Java
- Java PowerPoint automation
- Excel data integration
title: 將 Excel 加入 PowerPoint：使用 Aspose.Slides for Java 的動態餅圖簡報
url: /zh-hant/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 將 Excel 加入 PowerPoint：使用 Aspose.Slides for Java 的動態餅圖簡報

在當今以數據為驅動的環境中，**add Excel to PowerPoint** 需要快速且可靠，讓觀眾能以視覺化方式看到數字。本教學將指導您如何從 Excel 產生 PowerPoint、使用 Java 建立餅圖，以及設定圖表資料範圍——全部使用 Aspose.Slides for Java。完成後，您將擁有一個即時從 Excel 活頁簿提取資料的可直接使用的簡報。

## Quick Answers
- **什麼函式庫在 Java 中建立圖表？** Aspose.Slides for Java.
- **我可以直接將 Excel 資料拉入 PowerPoint 圖表嗎？** Yes – use Aspose.Cells to read the workbook and feed it to the chart.
- **示範的圖表類型是什麼？** A pie chart.
- **如何設定圖表的資料範圍？** By calling `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.
- **此方法的主要好處是什麼？** Automates the “add Excel to PowerPoint” workflow, eliminating manual copy‑paste.

## 什麼是 **add Excel to PowerPoint**？
將 Excel 加入 PowerPoint 指的是以程式方式匯入試算表資料並在投影片中進行視覺化。透過 Aspose.Slides 與 Aspose.Cells，您可以讀取任何 Excel 檔案、將儲存格對應至圖表系列，並產生精緻的簡報，而無需手動開啟 PowerPoint。

## 為什麼要使用 Aspose.Slides for Java 從 Excel 產生 PowerPoint？
- **速度：** 在秒內建立報告，而非分鐘。
- **準確性：** 資料直接從來源活頁簿讀取，消除抄寫錯誤。
- **彈性：** 隨時自訂圖表顏色、樣式與資料範圍。
- **可擴充性：** 整合至批次工作、Web 服務或排程報告流程。

## 先決條件

在開始之前，請確保您已具備以下條件：

- **Java Development Kit (JDK) 1.8+** 已安裝。
- **Aspose.Slides for Java** 與 **Aspose.Cells for Java** 函式庫（Maven、Gradle，或直接下載 JAR）。
- 一個包含您想視覺化資料的 Excel 活頁簿（`book1.xlsx`）。
- 有效的 Aspose 授權（免費試用可用於評估）。

### 必要的函式庫
您需要 Aspose.Slides 與 Aspose.Cells。請使用以下其中一種相依性管理工具：

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

Alternatively, download the JARs directly from [Aspose.Slides for Java 版本](https://releases.aspose.com/slides/java/).

### 授權取得
- **免費試用：** 可於 [Aspose 下載頁面](https://releases.aspose.com/slides/java/) 取得。  
- **臨時授權：** 若需測試且不受評估限制，請於 [Aspose 臨時授權頁面](https://purchase.aspose.com/temporary-license/) 申請。  
- **購買授權：** 若要在正式環境使用 Aspose 產品，請購買完整授權。

## 設定 Aspose.Slides for Java

將 Aspose.Slides 相依性加入您的專案（請參考上方的 Maven/Gradle 範例），若未使用建置工具，請將 JAR 檔案放置於 classpath 中。

### 基本初始化與設定
匯入代表 PowerPoint 檔案的核心類別：

```java
import com.aspose.slides.Presentation;
```

## 實作指南

以下是一個逐步說明，涵蓋 **create pie chart java**、**set chart data range** 以及 **add Excel to PowerPoint** 的完整流程。

### 建立並加入圖表至簡報

**概述：** 初始化一個新的簡報，取得第一張投影片，並插入餅圖。

#### 步驟 1：初始化簡報
```java
Presentation pres = new Presentation();
```
- **目的：** 在記憶體中建立一個空的 PowerPoint 檔案。

#### 步驟 2：存取第一張投影片
```java
ISlide slide = pres.getSlides().get_Item(0);
```
- **說明：** 取得系統自動建立的第一張投影片。

#### 步驟 3：在投影片上加入餅圖
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```
- **參數：** 位置 (`x`, `y`) 與大小 (`width`, `height`)。  
- **目的：** 在投影片上放置餅圖形狀。

### 從檔案載入活頁簿

**概述：** 載入包含圖表資料的 Excel 活頁簿。

#### 步驟 1：定義文件目錄
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```
- 將此設定為放置 `book1.xlsx` 的資料夾。

#### 步驟 2：開啟活頁簿
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```
- **目的：** 將 Excel 檔案讀入記憶體。

### 將活頁簿儲存至 ByteArrayOutputStream

**概述：** 將活頁簿轉換為位元組陣列，以便 Aspose.Slides 使用。

#### 步驟 1：建立 ByteArrayOutputStream
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```
- **目的：** 提供一個用於暫存的記憶體內部串流。

#### 步驟 2：將活頁簿儲存至串流
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```
- **說明：** 將活頁簿寫入為 XLSX 位元組串流。

### 將活頁簿資料寫入圖表

**概述：** 將 Excel 位元組陣列作為資料來源餵入圖表。

#### 步驟 1：將資料餵入圖表
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```
- **目的：** 將圖表與 Excel 資料連結。

### 設定圖表資料範圍與配置系列

**概述：** 定義圖表要讀取的儲存格，並加強視覺樣式。

#### 步驟 1：定義資料範圍
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```
- **說明：** 將圖表指向 *Sheet2* 上的精確範圍。

#### 步驟 2：配置系列屬性
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```
- **目的：** 讓餅圖的每個切片使用不同顏色。

### 將簡報儲存至檔案

**概述：** 將完成的簡報寫入磁碟。

#### 步驟 1：定義輸出路徑
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```
- 選擇您希望最終 PowerPoint 檔案存放的資料夾。

#### 步驟 2：儲存簡報
```java
pres.save(outPath, SaveFormat.Pptx);
```
- **說明：** 將簡報寫入為 `.pptx` 檔案。

## 實務應用

1. **商業報告：** 只需一個指令即可將每月銷售試算表轉換為精緻的投影片。  
2. **教育工具：** 在課堂簡報中展示統計分解，無需手動建立圖表。  
3. **儀表板整合：** 自動產生以投影片為基礎的儀表板，從 Excel 活頁簿即時提取資料。

## 效能考量

- **記憶體管理：** 使用 try‑with‑resources 包裝串流，或在 `finally` 區塊中關閉，以避免記憶體洩漏。  
- **大型資料集：** 分批處理資料，或在取得所需值後使用 `Workbook.getWorksheets().clear()`。  
- **延遲載入：** 僅在需要填充圖表時才載入活頁簿，而非應用程式啟動時即載入。

## 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| **圖表未顯示資料** | 確認範圍字串與工作表名稱及儲存格位址完全相符 (`Sheet2!$A$1:$B$3`)。 |
| **OutOfMemoryError** | 使用 `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` 以確保及時釋放串流。 |
| **授權未套用** | 在實例化任何 Aspose 類別之前先載入授權：`License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## 常見問答

**問：我可以在沒有授權的情況下使用 Aspose.Slides 嗎？**  
**答：** 可以，但評估模式會加上浮水印並限制某些功能。正式環境請取得臨時或完整授權。

**問：如何在 Aspose.Slides 中處理大型簡報？**  
**答：** 使用有效的資源管理，將簡報拆分為較小的部分，並及時釋放未使用的物件。

**問：Aspose.Slides 可以匯出哪些檔案格式？**  
**答：** PPTX、PDF、XPS、ODP、HTML，以及 PNG、JPEG、BMP 等影像格式。

**問：是否可以更新現有的 PowerPoint 檔案，而不是建立新檔案？**  
**答：** 當然可以。使用 `new Presentation("existing.pptx")` 載入現有檔案，修改投影片/圖表後再儲存。

**問：此函式庫是否支援為單獨的餅圖切片設定自訂顏色？**  
**答：** 是的——取得系列後，您可以設定 `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` 並指派 `Color`。

## 資源
- **文件說明：** [Aspose.Slides Java API 參考文件](https://reference.aspose.com/slides/java/)
- **下載：** [Aspose.Slides for Java 版本](https://releases.aspose.com/slides/java/)
- **購買授權：** [購買 Aspose 產品](https://purchase.aspose.com/buy)
- **免費試用：** [免費試用 Aspose.Slides](https://releases.aspose.com/slides/java/)
- **臨時授權：** [取得臨時授權](https://purchase.aspose.com/temporary-license)

---

**最後更新：** 2026-03-02  
**測試環境：** Aspose.Slides 25.4 for Java (JDK 16) 與 Aspose.Cells 25.4  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}