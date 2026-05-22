---
date: '2026-03-20'
description: 學習如何使用 Aspose.Slides 為 Java 簡報添加圖表，並快速產生簡報圖表檔案。
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: 如何使用 Aspose.Slides 為 Java 簡報新增圖表
url: /zh-hant/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Java 在簡報中加入圖表

## 簡介

在當今節奏快速的商業環境中，製作能有效傳遞資料的動態簡報至關重要。無論您是在準備財務報告、行銷簡報，或是專案狀態更新，**了解如何在投影片中加入圖表** 都能顯著提升觀眾的參與度。本教學將一步步示範如何加入 3D 堆疊柱狀圖、設定其資料，並儲存最終檔案——全部使用 Aspose.Slides for Java。

### 快速回答
- **主要的程式庫是什麼？** Aspose.Slides for Java  
- **示範的圖表類型為何？** 3D 堆疊柱狀圖  
- **我可以以程式方式產生簡報圖表檔案嗎？** 可以，使用下方示範的 API 方法  
- **建議使用哪個 Java 版本？** JDK 16 或更新版本  
- **正式環境需要授權嗎？** 商業使用必須具備有效的 Aspose.Slides 授權  

## Aspose.Slides 中的「如何加入圖表」是什麼？

Aspose.Slides for Java 提供完整的物件集合，讓您在不需要 Microsoft Office 的情況下建立、編輯與匯出 PowerPoint 檔案。加入圖表只需要建立一個 `Presentation` 物件、插入圖表形狀，並透過內建的活頁簿填入資料即可。

## 為什麼要在 Java 簡報中加入圖表？

- **視覺衝擊力：** 圖表能將原始數字轉換為一目了然的視覺資訊。  
- **自動化：** 即時產生報表，適合排程郵件摘要或儀表板。  
- **一致性：** 所有產生的簡報均使用相同的樣式與品牌識別。  
- **可移植性：** 只需一行程式碼即可匯出為 PPTX、PDF 或影像。

## 前置條件

- **程式庫與相依性：** 必須安裝 Aspose.Slides for Java。  
- **環境設定：** 建議在 JDK 16 或更新的 Java 環境中開發。  
- **知識基礎：** 具備基本的 Java 程式設計概念會更有幫助。

## 設定 Aspose.Slides for Java

### 安裝

將 Aspose.Slides 整合至專案時，可依下列任一方式操作。

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

**直接下載**：亦可從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

### 取得授權
- **免費試用：** 先使用免費試用版探索功能。  
- **暫時授權：** 取得暫時授權以延長測試時間。  
- **購買授權：** 正式商業使用請購買完整授權。

安裝完成後，即可實例化 `Presentation` 類別，作為所有圖表相關操作的入口點。

## 實作指南

### 如何在簡報中加入 3D 堆疊柱狀圖

#### 概觀
使用 Aspose.Slides 從頭建立簡報相當簡單。本節將在簡報的第一張投影片加入 3D 堆疊柱狀圖。

**步驟：**

1. **初始化 Presentation 物件**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **說明參數**  
   - `ChartType.StackedColumn3D`：指定圖表類型。  
   - 位置與大小 `(0, 0, 500, 500)`：決定圖表在投影片上的顯示位置與尺寸。

### 設定圖表資料

#### 概觀
為了讓圖表具備意義，需要設定資料系列與類別。本節示範如何將特定資料點加入圖表。

**步驟：**

1. **存取圖表的資料活頁簿**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### 設定圖表的 Rotation3D 屬性

#### 概觀
透過 3D 旋轉屬性提升圖表的視覺效果。此客製化讓您調整觀點與深度。

**步驟：**

1. **配置 3D 旋轉**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **說明參數**  
   - `setRightAngleAxes(true)`：確保座標軸垂直。  
   - 旋轉值：調整 3D 觀景的角度與深度。

### 在圖表中填入系列資料

#### 概觀
為圖表加入資料點是分析的關鍵。本節將在圖表的某個系列中加入具體數值。

**步驟：**

1. **新增資料點**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### 調整圖表的系列重疊

#### 概觀
微調圖表外觀可提升可讀性。本節說明如何調整重疊屬性以獲得更佳的資料可視化。

**步驟：**

1. **設定系列重疊**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### 儲存簡報

#### 概觀
完成簡報設定後，將其儲存至磁碟的指定格式。此步驟確保所有變更皆被保留。

**步驟：**

1. **儲存簡報**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| **圖表呈現平面** | 未設定 3D 旋轉 | 呼叫 `setRotation3D` 並提供適當的 X/Y 參數。 |
| **資料未顯示** | 活頁簿儲存格未正確連結 | 確認 `fact.getCell` 參照正確的列/欄索引。 |
| **檔案未儲存** | 路徑錯誤或缺少權限 | 檢查 `outputFilePath` 是否可寫入且資料夾已存在。 |

## 常見問答

**Q: 我可以產生除 PPTX 之外的簡報圖表檔案格式嗎？**  
A: 可以，Aspose.Slides 透過 `SaveFormat` 列舉支援 PDF、ODP 以及各種影像格式。

**Q: 開發階段需要授權嗎？**  
A: 開發時可使用暫時或評估授權，但正式上線必須購買完整授權。

**Q: 可以在同一張投影片上加入多個圖表嗎？**  
A: 當然可以。對不同位置或尺寸多次呼叫 `slide.getShapes().addChart` 即可。

**Q: 要如何變更圖表的色彩調色盤？**  
A: 使用 `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)`，再設定 `SolidFillColor`。

**Q: 能否將圖表綁定至外部資料來源（如資料庫）？**  
A: 能。先以 JDBC 取得資料，然後在儲存前將資料寫入活頁簿儲存格即可。

## 結論

您現在已掌握 **如何在 Java 簡報中加入圖表**、設定資料、客製化 3D 旋轉、調整系列重疊，並將最終檔案儲存。此知識可協助您自動化報表產生、建立一致的品牌形象，並以資料驅動的方式呈現簡報，省去手動操作的時間。若需更深入的客製化（如圖例、座標軸樣式或主題套用），請參考官方文件的完整功能說明。

如需進一步的進階功能與客製化選項，請參閱 [Aspose.Slides for Java documentation](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-03-20  
**測試環境：** Aspose.Slides for Java 25.4 (JDK 16)  
**作者：** Aspose