---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides for Java 建立和自訂餅圖。本指南涵蓋設定、實施和實際應用。"
"title": "使用 Aspose.Slides 在 Java 中建立餅圖綜合指南"
"url": "/zh-hant/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 在 Java 中建立圓餅圖：綜合指南

## 圖表和圖形

### 介紹

在資料視覺化中，圓餅圖是表示資料集內比例的直觀方式。然而，當處理一些部分比其他部分小得多的複雜資料集時，傳統的餅圖會變得混亂且難以解釋。圓餅圖中的餅將小塊分割成輔助圖表來解決此問題，從而增強了可讀性。

在本教程中，您將學習如何使用 Aspose.Slides for Java 建立和操作餅圖。您將了解如何設定環境、建立圖表、自訂資料標籤和分割位置等屬性以及以 PPTX 格式儲存簡報。最後，您將透過實際應用和效能技巧來掌握這些功能。

**您將學到什麼：**
- 設定 Aspose.Slides for Java
- 創建餅狀圖
- 自訂圖表屬性，例如資料標籤和分割配置
- 將簡報儲存到磁碟

準備好開始了嗎？我們先來看看先決條件吧！

## 先決條件

在創建餅圖之前，請確保您已：

### 所需的函式庫、版本和相依性：
- **Aspose.Slides for Java**：對於以程式設計方式管理 PowerPoint 簡報至關重要。

### 環境設定要求：
- 您的機器上安裝了 Java 開發工具包 (JDK)。我們建議使用 JDK 16 或更高版本。
- 整合開發環境 (IDE)，如 IntelliJ IDEA、Eclipse 或 NetBeans。

### 知識前提：
- 對 Java 程式設計有基本的了解
- 熟悉 Maven 或 Gradle 的依賴管理

## 設定 Aspose.Slides for Java

### 安裝資訊：

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

**直接下載**：您可以從 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

### 許可證取得步驟：
- **免費試用**：從 30 天試用開始探索所有功能。
- **臨時執照**：申請臨時許可證以進行延長評估。
- **購買**：如果 Aspose.Slides 滿足您的需求，請考慮購買許可證。

### 基本初始化和設定

在專案中設定庫後，透過建立 `Presentation` 班級：

```java
Presentation presentation = new Presentation();
```

這為在幻燈片中添加各種圖表奠定了基礎。接下來，讓我們繼續實作圓餅圖中的圓餅圖。

## 實施指南

### 創建“餅狀圖”

#### 概述
我們首先創建一個 `Presentation` 並在第一張投影片上新增圓餅圖。此圖表透過將較小的部分分成二級餅圖來有效地視覺化數據，從而增強可讀性。

#### 步驟 1：建立表示類別的實例
```java
// 建立新簡報
ePresentation presentation = new Presentation();
```
此程式碼初始化您的演示文稿，我們將在其中添加圖表。

#### 步驟 2：在第一張投影片上新增“圓餅圖”
```java
// 在第一張投影片中，在位置 (50, 50) 處新增一個餅狀圖，大小為 (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
這裡我們指定圖表的類型（`PieOfPie`) 及其在投影片上的位置和尺寸。

#### 步驟 3：設定資料標籤以顯示系列的值
```java
// 配置資料標籤以顯示值
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
此步驟可確保圓餅圖的每個部分都顯示其對應的值，有助於快速解釋資料。

#### 步驟 4：配置第二個圓餅圖的大小並依百分比分割
```java
// 設定次級餅圖的大小
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// 以百分比分割圓餅圖
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// 設定分割位置
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
這些配置可讓您自訂圖表如何分割和顯示較小的部分，從而提高查看者的清晰度。

#### 步驟 5：將簡報以 PPTX 格式儲存到磁碟
```java
// 定義輸出目錄
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// 儲存簡報\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}