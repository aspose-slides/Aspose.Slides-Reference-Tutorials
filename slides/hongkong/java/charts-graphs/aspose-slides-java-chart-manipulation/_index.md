---
date: '2026-01-17'
description: 學習如何使用 Aspose.Slides 在 Java 中建立圖表，新增叢集柱形圖，並將簡報儲存為 pptx。為 Java 開發者提供的逐步指南。
keywords:
- Aspose.Slides for Java
- chart manipulation in presentations
- Java presentation library
title: 如何在 Java 中使用 Aspose.Slides for Java 建立圖表
url: /zh-hant/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Java 中使用 Aspose.Slides for Java 建立圖表

## 介紹
建立一個看起來專業的 **create chart in java** 體驗不必令人頭疼。使用 **Aspose.Slides for Java**，您可以以程式方式在 PowerPoint 簡報中直接加入、樣式化及儲存圖表——例如叢集柱狀圖。在本教學中，我們將逐步說明設定函式庫、初始化簡報、插入叢集柱狀圖、微調繪圖區，最後將檔案儲存為 PPTX。完成後，您將擁有可在任何 Java 專案中使用的可重用程式碼片段。

**您將學習**
- 如何設定 Aspose.Slides 的 Maven 或 Gradle 相依性  
- 如何 **create chart in java** 並加入叢集柱狀圖  
- 如何設定繪圖區（位置、大小、版面配置）  
- 如何 **save presentation as pptx** 並正確處理資源  

準備好讓您的資料以視覺方式說話了嗎？讓我們開始吧！

## 快速解答
- **需要的函式庫是什麼？** Aspose.Slides for Java（Maven/Gradle）。  
- **示範的圖表類型是什麼？** 叢集柱狀圖。  
- **如何儲存檔案？** 使用 `presentation.save(..., SaveFormat.Pptx)`。  
- **需要授權嗎？** 免費試用可用於開發；正式環境需購買完整授權。  
- **可以變更繪圖區嗎？** 可以，您可以設定 X、Y、寬度、高度以及版面配置目標類型。

## 什麼是 create chart in java？
在 Java 中建立圖表是指使用函式庫產生圖表物件、填入資料，並將其嵌入文件——此處為 PowerPoint 投影片。Aspose.Slides 抽象化了低階的 Office Open XML 細節，讓您專注於視覺結果。

## 為何使用 Aspose.Slides 加入叢集柱狀圖？
叢集柱狀圖非常適合並排比較多個資料系列。它在商業報告、儀表板與簡報中廣泛使用。Aspose.Slides 讓您在不開啟 PowerPoint 的情況下，完整控制顏色、標記、座標軸與版面配置。

## 前置條件
- **Aspose.Slides for Java** 函式庫（版本 25.4 或更新）。  
- **JDK 16**（或更新版）已安裝。  
- 如 IntelliJ IDEA 或 Eclipse 等 IDE。  
- 具備基本的 Java 語法知識。

## 設定 Aspose.Slides for Java

### Maven
將相依性加入您的 `pom.xml`：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
在 `build.gradle` 中加入函式庫：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
或者，從 [Aspose 官方網站](https://releases.aspose.com/slides/java/) 下載最新版本。

#### 授權取得
測試時可使用免費試用或臨時授權。正式部署請購買完整授權。

### 基本初始化與設定
建立新的 Java 類別並匯入核心類別：

```java
import com.aspose.slides.Presentation;
```

## 實作指南
我們將逐步說明每個步驟並提供清晰說明。

### 簡報初始化與投影片操作

#### 概觀
首先，建立一個新的簡報，並取得圖表將放置的第一張投影片。

**1. 建立並初始化簡報**

```java
Presentation presentation = new Presentation();
```

**2. 取得第一張投影片**

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. 新增叢集柱狀圖**

```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

> **專業提示：** 請始終將簡報的使用包在 `try‑finally` 區塊中，並在 `finally` 內呼叫 `presentation.dispose()` 以釋放原生資源。

### 繪圖區設定

#### 概觀
微調圖表的繪圖區，以控制資料在投影片中的顯示位置。

**1. 設定位置與大小**

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
```

**2. 定義版面配置目標類型**

```java
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

### 儲存簡報

#### 概觀
自訂圖表後，將簡報保存為 PPTX 檔案。

**1. 儲存至檔案**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **警告：** 請確保輸出目錄已存在且應用程式具有寫入權限；否則儲存操作會失敗。

## 常見使用情境
- **商業報告：** 嵌入銷售趨勢與財務 KPI。  
- **教學投影片：** 可視化實驗結果或統計資料。  
- **專案提案：** 突顯里程碑與資源分配。  
- **行銷簡報：** 以鮮明圖表展示活動績效。  
- **活動規劃：** 顯示參與者人口統計或行程細分。

## 效能考量
- 及時釋放 `Presentation` 物件以避免記憶體洩漏。  
- 對於大型資料集，請逐步填充圖表系列，而非一次載入全部。  
- 使用 Java 內建的效能分析工具監控圖表產生過程中的堆積使用情況。

## 常見問與答

**問：如何加入其他圖表類型？**  
**答：** 呼叫 `addChart` 時使用 `ChartType` 列舉（例如 `ChartType.Pie`、`ChartType.Line`）。

**問：我可以自訂圖表顏色嗎？**  
**答：** 可以，透過 `IChart` API 修改系列的填充格式或圖表調色盤。

**問：我的簡報無法儲存——原因是什麼？**  
**答：** 請確認 `YOUR_OUTPUT_DIRECTORY` 正確、已存在且可寫入，同時檢查是否有檔案被鎖定。

**問：如何有效處理非常大的簡報？**  
**答：** 分批處理投影片，使用後釋放每個 `Presentation`，必要時考慮增大 JVM 堆積大小。

**問：Aspose.Slides 可免費用於商業專案嗎？**  
**答：** 可使用免費試用版進行評估，但商業部署需購買授權。

## 資源
- [Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides](https://releases.aspose.com/slides/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/slides/11)

立即使用 Aspose.Slides for Java 開始打造視覺驚豔的簡報吧！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

---