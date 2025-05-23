---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides for Java 在 PowerPoint 中建立動態圓環圖。透過簡單易懂的步驟和程式碼範例增強您的簡報。"
"title": "使用 Aspose.Slides for Java 在 PowerPoint 中建立動態圓環圖"
"url": "/zh-hant/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 在 PowerPoint 中建立動態圓環圖

## 介紹
創建引人注目的簡報通常不僅僅需要文字和圖像；圖表可以透過有效地視覺化資料來顯著增強故事敘述效果。然而，許多開發人員難以以程式設計方式將動態圖表功能整合到 PowerPoint 文件中。本教學課程示範如何使用 Aspose.Slides for Java 在 PowerPoint 中建立環形圖——一種兼具靈活性和易用性的強大工具。

**您將學到什麼：**
- 如何使用 Aspose.Slides for Java 初始化簡報
- 在幻燈片中加入圓環圖的分步指南
- 配置資料點並自訂標籤屬性
- 高保真保存修改後的簡報

讓我們探索如何利用這些功能來增強您的簡報。在開始之前，請確保您熟悉基本的 Java 程式設計概念。

## 先決條件
為了有效地遵循本教程，請確保您已：
- Java 程式設計基礎知識。
- 整合開發環境 (IDE)，如 IntelliJ IDEA 或 Eclipse。
- 安裝 Maven 或 Gradle 進行依賴管理。
- 有效的 Aspose.Slides for Java 授權。您可以獲得免費試用版來測試其功能。

## 設定 Aspose.Slides for Java
首先將 Aspose.Slides 合併到您的專案中。根據您的喜好在 Maven 和 Gradle 之間進行選擇：

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

如果您希望直接下載，請訪問 [Aspose.Slides for Java 發布](https://releases.aspose.com/slides/java/) 頁。

### 許可證獲取
您可以從免費試用開始探索 Aspose.Slides 的功能。如需延長使用時間，請購買許可證或申請臨時許可證 [Aspose的網站](https://purchase.aspose.com/temporary-license/)。按照提供的說明設定您的環境並在應用程式中初始化 Aspose.Slides。

## 實施指南
讓我們分解一下使用 Aspose.Slides for Java 在 PowerPoint 中建立圓環圖所需的步驟。每個部分都專注於一個特定的功能，以確保清晰度和重點。

### 初始化演示
首先載入或建立一個新的 PowerPoint 文件。此步驟設定您的示範環境。

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// 透過儲存初始簡報來驗證載入是否成功
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### 新增圓環圖
在投影片中新增圓環圖，自訂其尺寸和外觀。

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// 配置系列屬性
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### 配置數據點和標籤
自訂每個資料點的外觀並配置標籤以增強可讀性。

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
        
        // 格式化資料點
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // 自訂每個類別中最後一個系列的標籤屬性
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

### 儲存簡報
配置圖表後，儲存簡報以保留您的變更。

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## 實際應用
環形圖可用於各種場景：
- **財務報告：** 可視化預算分配或財務指標。
- **市場分析：** 顯示競爭對手的市佔率分佈。
- **調查結果：** 有效地呈現調查回應的分類資料。

與資料庫和 Web 應用程式等其他系統的集成，可以基於即時數據生成動態圖表。

## 性能考慮
為了獲得最佳性能：
- 透過及時處置資源來管理記憶體使用情況。
- 如果沒有必要，請限制圖表或投影片的數量以節省處理能力。
- 使用高效的資料結構來處理大型資料集。

遵循最佳實務可確保您的應用程式順利運行，尤其是在處理複雜的簡報時。

## 結論
一旦了解了關鍵步驟，使用 Aspose.Slides for Java 在 PowerPoint 中建立動態圓環圖就是一個簡單的過程。透過本指南，您現在可以透過整合視覺上吸引人的圖表來有效傳達數據見解，從而增強您的簡報。

為了進一步探索 Aspose.Slides 的功能並深入了解其性能，請考慮嘗試不同的圖表類型或動畫和過渡等高級功能。

## 常見問題部分
**Q：我可以在商業應用程式中使用 Aspose.Slides for Java 嗎？**
答：是的，但是您需要取得許可證。您可以先免費試用來評估其功能。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}