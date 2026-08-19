---
date: '2026-07-17'
description: 學習如何使用 Aspose Slides for Java 在 PowerPoint 中添加 Sunburst 圖表。逐步指南涵蓋環境設定、圖表建立、客製化以及實務案例。
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: 如何在 PowerPoint 中使用 Aspose Slides for Java 添加 Sunburst 圖表。跟隨本教學設定函式庫、建立圖表、客製化資料點，並將其應用於實際專案。
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: 如何在 PowerPoint 中使用 Aspose (Java) 添加 Sunburst 圖表
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: 如何在 PowerPoint 中使用 Aspose (Java) 添加 Sunburst 圖表
url: /zh-hant/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 PowerPoint 中使用 Aspose (Java) 添加 Sunburst 圖表

## 介紹

在 PowerPoint 簡報中加入 Sunburst 圖表，即可瞬間將平面的資料表格轉換為引人入勝的視覺層次結構。  
在本教學中，您將學習如何使用 Aspose.Slides for Java 在 PowerPoint 中**添加 Sunburst** 圖表，涵蓋環境設定到細緻調整顏色與標籤的全過程。無論您是建立銷售儀表板、專案任務分解，或是教育簡報，以下步驟都能為您提供可直接投入生產的解決方案。

**您將學到**
- 如何在 Maven 或 Gradle 專案中配置 Aspose.Slides  
- 如何建立新簡報並插入 Sunburst 圖表  
- 如何自訂資料點、標籤與填色  
- Sunburst 圖表在實務情境中的最佳應用  

讓我們開始吧，看看將原始層次資料轉換為精緻 PowerPoint 視覺的簡易步驟。

## 快速解答
- **主要函式庫？** Aspose.Slides for Java  
- **支援的圖表類型？** Sunburst（徑向層次圖）  
- **最低 Java 版本？** JDK 16  
- **一般實作時間？** 基本圖表約 10‑15 分鐘  
- **生產環境是否需要授權？** 需要，有效的 Aspose 授權  

## 什麼是 Sunburst 圖表？
Sunburst 圖表是一種徑向圖示，透過從中心點向外延伸的環形層級，視覺化層次資料。它非常適合展示多層級關係，如組織結構、產品類別或檔案系統樹狀圖。每個同心環代表一個層級，而每個區段的大小則反映其數量值，讓觀眾能快速了解結構與規模。

## 為何選擇 Aspose.Slides for Java？
Aspose.Slides 支援 **50+ 種圖表類型**，且可在不將整個檔案載入記憶體的情況下操作 **多達 10,000 張投影片** 的簡報，為企業級報表提供高效能。它跨平台運作，提供完整的 API，且具備完善的授權方案，可移除評估限制，十分適合生產環境使用。

## 前置條件
- **Java Development Kit (JDK)** 16 或更新版本  
- **IDE** – IntelliJ IDEA、Eclipse 或任何支援 Java 的編輯器  
- 具備 Java 語法與 Maven/Gradle 建置工具的基本認識  

## 設定 Aspose.Slides for Java

### Maven 相依性
將 Aspose.Slides Maven 套件加入您的 `pom.xml`：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 相依性
如果您偏好 Gradle，請在 `build.gradle` 中加入以下行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
您亦可直接從官方發佈頁面下載最新的 JAR： [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)。

### 取得授權
若要在無評估限制的情況下執行，請取得授權：
- **免費試用** – 用於快速評估的臨時授權。  
- **臨時授權** – 可從 [Aspose 網站](https://purchase.aspose.com/temporary-license) 申請。  
- **正式購買** – 購買訂閱以獲得無限制的生產使用權。

### 基本初始化
`Presentation` 類別是建立或開啟 PowerPoint 檔案的入口點。

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## 實作指南

### 如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中加入 Sunburst 圖表？

載入新的 `Presentation`，新增投影片，插入類型為 `ChartType.Sunburst` 的 `IChart`，最後呼叫 `save`。此簡潔的三步驟即可建立完整功能的 Sunburst 圖表，供後續自訂使用。

#### 步驟 1：初始化 Presentation
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### 步驟 2：加入 Sunburst 圖表
`IChart` 介面定義了可放置於任何投影片上的圖表物件。此處我們在座標 (100, 100) 處加入一個大小為 450 × 400 點的 Sunburst 圖表。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### 步驟 3：儲存簡報
務必透過呼叫 `save` 來永久保存變更。您可以選擇 PPTX、PDF 或 50+ 種支援的輸出格式之一。

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### 修改圖表資料點

#### 概觀
您可以透過圖表的資料點集合，針對 Sunburst 的每個切片調整標籤、顏色與可見性。

#### 步驟 1：存取資料點集合
圖表的第一個系列包含一個 `IChartDataPoint` 物件集合，代表每個切片。

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### 步驟 2：顯示特定資料點的數值
將目標資料點的 `IsValueShown` 設為 `true`，即可在切片上直接顯示其數值。

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### 步驟 3：修改標籤格式
調整標籤的可見性、字體顏色與背景，以提升可讀性。

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### 步驟 4：設定資料點的填色
自訂各切片的填色，以符合品牌配色或突顯關鍵區段。

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### 步驟 5：儲存已修改的簡報
再次儲存簡報，以永久保存自訂的圖表。

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## 實務應用

1. **商業分析** – 以單一徑向視圖呈現區域 → 產品線 → SKU 的銷售情況。  
2. **專案管理** – 展示工作分解結構，從階段到任務再到子任務。  
3. **教育** – 繪製課程層級結構，例如系所 → 課程 → 單元。  

## 效能考量

- **記憶體效率：** Aspose.Slides 以串流方式處理資料，即使是包含多個圖表的 500 頁簡報，記憶體使用仍低於 200 MB。  
- **垃圾回收：** 當投影片物件不再使用時，呼叫 `slide.dispose()` 釋放，以避免記憶體洩漏。  

## 常見問題

**Q: 什麼是 Sunburst 圖表？**  
**A:** Sunburst 圖表以同心環方式視覺化層次資料，每個環代表一個層級。

**Q: 如何使用 Maven 安裝 Aspose.Slides for Java？**  
**A:** 在 `pom.xml` 中加入「Maven 相依性」段落所示的相依性，然後執行 `mvn clean install`。

**Q: 我可以自訂其他圖表類型嗎？**  
**A:** 可以，該函式庫支援超過 50 種圖表，包括柱狀圖、折線圖、圓餅圖與雷達圖等。

**Q: 我的簡報無法儲存——該檢查什麼？**  
**A:** 請確認檔案路徑正確、目錄存在且具寫入權限，同時確保已呼叫 `Presentation.save()` 方法。

**Q: 哪裡可以取得更多協助或範例？**  
**A:** 前往 [Aspose 論壇](https://forum.aspose.com/c/slides/11) 或參考官方的 [Aspose.Slides 參考文件](https://reference.aspose.com/slides/java/)。

## 資源
- **文件說明：** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **參考（小寫）：** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **社群論壇：** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **下載：** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**最後更新：** 2026-07-17  
**測試版本：** Aspose.Slides for Java 24.12  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Aspose.Slides for Java 在 PowerPoint 中添加圖表：逐步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [使用 Aspose.Slides for Java 為 PowerPoint 圖表添加動畫 – 逐步指南](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [在 Java 中使用 Aspose.Slides 建立圖表 – 添加與驗證圖表](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}