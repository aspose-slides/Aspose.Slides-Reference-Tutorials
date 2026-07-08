---
date: '2026-07-08'
description: 了解如何使用 Aspose 於 PowerPoint 搭配 Java 建立 Doughnut Chart。此逐步指南說明如何以程式方式加入圖表資料點、客製化標籤，並以高保真度儲存
  PPTX。
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: 使用 Aspose 可在 PowerPoint 以 Java 建立 Doughnut Chart。請依照本教學加入資料點、客製化標籤，並以高保真度儲存
  PPTX。
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 如何使用 Aspose：在 PowerPoint (Java) 中建立 Doughnut Chart
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: 如何使用 Aspose 在 PowerPoint (Java) 中建立 Doughnut Chart
url: /zh-hant/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 PowerPoint (Java) 中使用 Aspose 建立環形圖表

## 快速回答
- **什麼函式庫可以建立 PowerPoint 環形圖表？** Aspose.Slides for Java  
- **我可以程式化新增圖表資料點嗎？** 是的，使用圖表 API  
- **在正式環境需要授權嗎？** 需要有效的 Aspose.Slides 授權  
- **支援哪個版本的 Java？** Java 8 及以上（示範使用 JDK 16 classifier）  
- **我可以加入多少個系列？** 範例最多加入 15 個系列，您可依需求自行調整  

## 什麼是 PowerPoint 中的環形圖表？
環形圖表是一種圓形圖表，類似於圓餅圖，但中心為空洞，允許同時顯示多個系列。它強調部分與整體的關係，同時保持版面緊湊且易於閱讀。

## 為何使用 Aspose.Slides for Java 來建立環形圖表？
Aspose.Slides for Java 支援超過 50 種輸入與輸出格式，且能在不將整個檔案載入記憶體的情況下產生最高達 500 MB 的簡報。它在任何 Java 平台上提供對圖表外觀、資料與版面的完整程式化控制，消除 COM 相容性問題，且在一般伺服器上可在兩秒內渲染 100 張含圖表的投影片。

## 前置條件
- 具備基本的 Java 程式設計知識。  
- 使用 IntelliJ IDEA 或 Eclipse 等 IDE。  
- 使用 Maven 或 Gradle 進行相依性管理。  
- 有效的 Aspose.Slides for Java 授權（提供免費試用）。

## 設定 Aspose.Slides for Java
選擇適合您專案的相依性管理工具。

**Maven**  
將以下相依性加入您的 `pom.xml`（將版本號替換為最新版本）：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
在您的 `build.gradle` 中加入此行：

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

如果您偏好直接下載，請前往 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 頁面。

### 取得授權
您可以先使用免費試用版來探索 Aspose.Slides 功能。若需長期使用，請購買授權或從 [Aspose 的網站](https://purchase.aspose.com/temporary-license/) 申請臨時授權。依照提供的說明設定環境並在應用程式中初始化 Aspose.Slides。

## 如何使用 Aspose.Slides for Java 建立 PowerPoint 環形圖表
要建立環形圖表，首先載入或建立 `Presentation`，加入類型為 `ChartType.Doughnut` 的圖表形狀，清除預設系列，設定環形孔大小，然後在圖表的工作簿中填入類別名稱與數值。最後，調整標籤格式並儲存 PPTX。

### 步驟 1：初始化簡報
建立全新的簡報或開啟既有檔案以取得投影片集合。

`Presentation` 是代表 PowerPoint 檔案的主要類別。  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 步驟 2：在投影片中加入環形圖表
插入圖表形狀，移除預設的系列/類別，並設定基本的視覺參數，例如環形孔大小。

`Chart`（或圖表形狀）代表放置於投影片上的圖表物件。  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 步驟 3：加入圖表資料點並自訂標籤
填入類別名稱，為每個系列加入資料點，並微調標籤格式（字型、顏色、位置）。此步驟示範「新增圖表資料點」的功能。

`Workbook` 提供存取圖表底層試算表資料的功能，可在其中填入儲存格。  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### 步驟 4：儲存更新後的簡報
將變更寫入磁碟上的新 PPTX 檔案。

`save` 會將簡報寫入指定格式的檔案。  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## 實務應用
- **財務報告：** 視覺化預算分配或費用明細。  
- **市場分析：** 顯示競爭者之間的市場佔有率分布。  
- **調查結果：** 以緊湊形式呈現分類調查資料。  
- **儀表板產生：** 結合資料庫查詢產生即時更新的投影片。

## 效能考量
- **釋放資源：** 儲存後呼叫 `pres.dispose()` 以釋放原生記憶體。  
- **限制圖表數量：** 新增數百張圖表會增加記憶體使用量，必要時請批次處理。  
- **使用串流：** 面對大量資料時，直接從串流填充工作簿，而非使用記憶體陣列。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|-------|-------|-----|
| **圖表顯示空白** | 資料儲存格未正確填入 | 確認 `workBook.getCell(...)` 參照了正確的列/欄索引。 |
| **標籤重疊** | 類別過多導致空間不足 | 增大 `DoughnutHoleSize` 或調整 `FirstSliceAngle`。 |
| **OutOfMemoryError** | 大型簡報未釋放資源 | 儲存後呼叫 `pres.dispose()`，並考慮增大 JVM 堆積大小。 |

## 常見問答

**Q: 我可以在商業應用中使用 Aspose.Slides for Java 嗎？**  
A: 是的，但您需要有效的商業授權。提供免費試用版供評估。

**Q: 如何加入超過 15 個系列？**  
A: 在「新增環形圖表」步驟中提升迴圈上限，並確保資料工作簿有足夠的列。

**Q: 建立後可以變更環形孔大小嗎？**  
A: 可以，在儲存前呼叫 `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`。

**Q: 我可以將圖表匯出為影像而非 PPTX 嗎？**  
A: 當然可以。使用 `chart.getImage()`，並將回傳的 `java.awt.image.BufferedImage` 以您偏好的格式儲存。

**Q: Aspose.Slides 支援動畫圖表嗎？**  
A: 可透過 `ISlide.getTimeline()` API 加入動畫，但此教學未涵蓋此部分。

## 結論
您現在已掌握使用 Aspose.Slides for Java 建立 **PowerPoint 環形圖表** 檔案的完整、可投入生產的方式，包含 **新增圖表資料點**、自訂標籤以及效能考量。請嘗試不同的顏色、資料來源與圖表類型，讓您的簡報真正脫穎而出。

---

**最後更新：** 2026-07-08  
**測試環境：** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**作者：** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## 相關教學

- [如何使用 Aspose.Slides for Java 在 PowerPoint 中新增圖表：逐步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [如何使用 Aspose.Slides for Java 編輯 PowerPoint 圖表資料：完整指南](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [使用 Aspose.Slides for Java 為 PowerPoint 圖表加入動畫 – 逐步指南](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}