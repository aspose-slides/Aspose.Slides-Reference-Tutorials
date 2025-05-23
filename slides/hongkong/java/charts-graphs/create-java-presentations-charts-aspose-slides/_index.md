---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides 在 Java 中建立和配置帶有圖表的動態簡報。掌握如何有效地新增、自訂和儲存簡報。"
"title": "使用 Aspose.Slides for Java 建立帶有圖表的 Java 簡報"
"url": "/zh-hant/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Java 建立和配置帶有圖表的簡報

## 介紹

在當今快節奏的商業環境中，創建能夠有效傳達數據的動態簡報至關重要。無論您是在準備財務報告還是展示專案指標，新增圖表都可以顯著增強簡報的影響力。本教學將指導您使用 Aspose.Slides for Java（一個旨在以程式設計方式處理簡報的強大函式庫）來建立和配置具有 3D 堆積長條圖的簡報。

**您將學到什麼：**
- 如何建立新的簡報
- 在投影片中新增和配置圖表
- 自訂圖表資料和外觀
- 有效保存您的簡報

準備好使用 Java 創建具有視覺吸引力的簡報了嗎？讓我們開始吧！

## 先決條件

在深入學習本教程之前，請確保您已滿足以下先決條件：

- **庫和依賴項**：必須安裝 Aspose.Slides for Java。
- **環境設定**：在 Java 環境中工作（建議使用 JDK 16 或更高版本）。
- **知識庫**：熟悉基本的 Java 程式設計概念將會很有幫助。

## 設定 Aspose.Slides for Java

### 安裝

若要將 Aspose.Slides 整合到您的專案中，請按照以下步驟操作：

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

**直接下載**：或者，從下載最新版本 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

### 許可證獲取
- **免費試用**：從免費試用開始探索功能。
- **臨時執照**：取得臨時許可證以進行延長測試。
- **購買**：獲得商業使用的完整許可。

安裝後，透過創建 `Presentation` 班級。這為在簡報中添加圖表和其他元素奠定了基礎。

## 實施指南

### 建立並配置帶有圖表的演示文稿

#### 概述
使用 Aspose.Slides 可以直接從頭開始建立簡報。在本節中，我們將在簡報的第一張投影片中新增 3D 堆積長條圖。

**步驟：**

1. **初始化演示對象**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // 初始化新的 Presentation 對象
           Presentation presentation = new Presentation();
           
           // 存取簡報中的第一張投影片
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // 在投影片的 (0,0) 位置增加一個 3D 堆積長條圖
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

2. **解釋參數**：
   - `ChartType.StackedColumn3D`：指定圖表類型。
   - 位置和大小 `(0, 0, 500, 500)`：確定圖表在投影片上出現的位置。

### 配置圖表數據

#### 概述
為了使您的圖表有意義，請配置其資料系列和類別。本節示範如何在圖表中新增特定資料點。

**步驟：**

1. **存取圖表的資料工作簿**

   ```java
   public static void configureChartData(IChart chart) {
       // 設定包含圖表資料的工作表的索引
       int defaultWorksheetIndex = 0;
       
       // 存取圖表的資料工作簿
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // 添加兩個帶有名稱的系列
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // 新增三個類別
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### 設定圖表的 Rotation3D 屬性

#### 概述
使用 3D 旋轉屬性增強圖表的視覺吸引力。此自訂可讓您調整視角和深度。

**步驟：**

1. **配置 3D 旋轉**

   ```java
   public static void setRotation3D(IChart chart) {
       // 啟用直角軸並配置 X、Y 方向的旋轉和深度百分比
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **解釋參數**：
   - `setRightAngleAxes(true)`：確保軸垂直。
   - 旋轉值：調整 3D 視圖的角度和深度。

### 在圖表中填入系列數據

#### 概述
用數據點填充圖表對於分析至關重要。在這裡，我們將向圖表中的一系列添加特定值。

**步驟：**

1. **新增數據點**

   ```java
   public static void populateSeriesData(IChart chart) {
       // 訪問第二個圖表系列
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // 為具有指定值的條形系列新增資料點
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

### 調整圖表中的系列重疊

#### 概述
微調圖表的外觀可以提高可讀性。本節介紹如何調整重疊屬性以實現更好的資料視覺化。

**步驟：**

1. **設定係列重疊**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // 從圖表中取得第二個系列並將其重疊設為 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### 儲存簡報

#### 概述
配置好簡報後，將其以所需的格式儲存到磁碟。此步驟確保所有變更都已儲存。

**步驟：**

1. **儲存簡報**

   ```java
   public static void savePresentation(Presentation presentation) {
       // 將修改後的簡報儲存到文件
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## 結論

現在您已經了解如何使用 Aspose.Slides for Java 建立和配置帶有圖表的簡報。本指南涵蓋初始化簡報、新增 3D 堆積長條圖、配置資料系列和類別、設定旋轉屬性、填入系列資料、調整系列重疊以及儲存最終簡報。

如需更多進階功能和自訂選項，請參閱 [Aspose.Slides for Java 文檔](https://docs。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}