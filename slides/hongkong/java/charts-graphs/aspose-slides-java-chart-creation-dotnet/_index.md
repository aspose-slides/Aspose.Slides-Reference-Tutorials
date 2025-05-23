---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides for Java 在 .NET 簡報中建立和自訂圖表。請按照本逐步指南來增強您的簡報資料視覺化。"
"title": "Aspose.Slides for Java&#58;在 .NET 簡報中建立圖表"
"url": "/zh-hant/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 在 .NET 簡報中建立圖表
## 介紹
創建引人注目的簡報通常涉及整合圖表等視覺數據表示，以增強觀眾的理解和參與。如果您是開發人員，希望使用 Aspose.Slides for Java 為您的 .NET 簡報新增動態、可自訂的圖表，那麼本教學就是為您量身打造的。我們將深入研究如何初始化簡報、新增各種圖表類型、管理圖表資料以及有效地格式化系列資料。
**您將學到什麼：**
- 如何在您的 .NET 環境中設定和使用 Aspose.Slides for Java。
- 使用 Aspose.Slides 初始化新的簡報。
- 在幻燈片中新增和自訂圖表。
- 管理圖表數據工作簿。
- 格式化系列數據，尤其是處理負值。
過渡到先決條件部分將確保您已做好輕鬆跟進的準備。
## 先決條件
在深入使用 Aspose.Slides for Java 建立圖表之前，讓我們先概述一下您的需求：
### 所需的庫和版本
確保您具有以下相依性：
- **Aspose.Slides for Java**：版本 25.4 或更高版本。
### 環境設定要求
- 支援.NET應用程式的開發環境。
- 對 Java 程式設計概念有基本的了解。
### 知識前提
- 熟悉在 .NET 應用程式環境中建立簡報。
- 了解 Java 依賴項及其管理（Maven/Gradle）。
## 設定 Aspose.Slides for Java
要開始使用 Aspose.Slides，您需要將其作為依賴項包含在您的專案中。您可以按照以下步驟操作：
### Maven
將以下相依性新增至您的 `pom.xml` 文件：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
將其包含在您的 `build.gradle` 文件：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### 直接下載
或者，您可以從 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).
#### 許可證取得步驟
- **免費試用**：從臨時許可證開始探索功能。
- **購買**：考慮購買許可證以供廣泛使用。
#### 基本初始化和設定
以下是在程式碼中初始化 Aspose.Slides 的方法：
```java
import com.aspose.slides.Presentation;
// 初始化新的 Presentation 對象
Presentation pres = new Presentation();
try {
    // 你的邏輯在這裡...
} finally {
    if (pres != null) pres.dispose();
}
```
此設定可確保資源管理得到有效處理。
## 實施指南
我們將指導您逐步實現這些功能。
### 初始化簡報
**概述：**
建立演示實例為所有後續操作奠定了基礎。此功能展示如何使用 Aspose.Slides 從頭開始。
#### 步驟1：導入必要的套件
```java
import com.aspose.slides.Presentation;
```
#### 步驟 2：建立新的演示對象
以下是操作方法：
```java
Presentation pres = new Presentation();
try {
    // 您的程式碼邏輯在這裡...
} finally {
    if (pres != null) pres.dispose(); // 確保資源被釋放
}
```
*這確保了展示對像在使用後被正確處置，從而防止記憶體洩漏。*
### 將圖表新增至投影片
**概述：**
在幻燈片中加入圖表可以使資料視覺化更有效、更吸引人。
#### 步驟1：導入必要的套件
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```
#### 步驟2：初始化簡報並新增圖表
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // 圖表自訂的附加邏輯...
} finally {
    if (pres != null) pres.dispose();
}
```
*在這裡，我們在第一張投影片中按指定的座標和尺寸添加了一個簇狀長條圖。*
### 管理圖表數據工作簿
**概述：**
有效地管理圖表的資料工作簿可讓您無縫地操作系列和類別。
#### 步驟1：導入必要的套件
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```
#### 第 2 步：存取和清除資料工作簿
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // 清除現有數據
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // 您的自訂邏輯在這裡...
} finally {
    if (pres != null) pres.dispose();
}
```
*在新增系列和類別時，清除工作簿對於從頭開始至關重要。*
### 在圖表中新增系列和類別
**概述：**
此功能顯示如何透過管理系列和類別新增有意義的資料點。
#### 步驟 1：新增系列和類別
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // 清除現有系列和類別
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // 新增系列和類別
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // 進一步自訂邏輯...
} finally {
    if (pres != null) pres.dispose();
}
```
*新增系列和類別可以使資料呈現更有條理。*
### 填滿系列資料和格式化
**概述：**
用資料點填滿圖表並格式化外觀以增強可讀性，尤其是在處理負值時。
#### 步驟 1：填入系列數據
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // 新增系列和類別（重複使用先前的邏輯）
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // 負值的格式系列
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // 儲存簡報
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*本節示範如何填入資料並套用顏色格式以實現更好的視覺化。*

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}