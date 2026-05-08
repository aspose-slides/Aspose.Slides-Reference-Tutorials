---
date: '2026-02-17'
description: 學習如何使用 Aspose.Slides for Java 在 PowerPoint 中建立環形圖，並以程式方式加入圖表資料點。跟隨簡易步驟與程式碼範例。
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: 使用 Aspose.Slides for Java 建立 PowerPoint 環形圖
url: /zh-hant/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 建立甜甜圈圖表 PowerPoint

## 介紹
製作引人入勝的簡報往往不只需要文字與圖片；圖表能透過有效的資料視覺化，大幅提升敘事效果。然而，許多開發者在程式化整合動態圖表功能至 PowerPoint 檔案時會遇到困難。本教學示範如何使用 **Aspose.Slides for Java** 來 **建立甜甜圈圖表 PowerPoint**，這是一套結合彈性與易用性的強大工具。

**您將學會：**
- 如何使用 Aspose.Slides for Java 初始化簡報
- 步驟式教學，將甜甜圈圖表加入投影片
- 設定資料點與自訂標籤屬性
- 以高保真度儲存修改後的簡報

讓我們一起探索如何善用這些功能，提升簡報品質。開始前，請確保您熟悉基本的 Java 程式概念。

## 快速問答
- **哪個函式庫可建立甜甜圈圖表 PowerPoint？** Aspose.Slides for Java  
- **可以程式化新增圖表資料點嗎？** 可以，使用 chart API  
- **正式環境需要授權嗎？** 需要有效的 Aspose.Slides 授權  
- **支援哪些 Java 版本？** Java 8 及以上（示範使用 JDK 16 classifier）  
- **最多可以加入多少系列？** 範例最多加入 15 系列，您可依需求自行調整  

## 什麼是 PowerPoint 中的甜甜圈圖表？
甜甜圈圖表是帶有中空中心的圓餅圖變形，可在緊湊且具視覺吸引力的版面中顯示多個資料系列。它非常適合呈現部分與整體的關係，同時保持設計的簡潔。

## 為什麼使用 Aspose.Slides for Java 來建立甜甜圈圖表？
- **完整控制** 圖表外觀、資料與版面配置，無需開啟 PowerPoint  
- **無 COM 相依** – 可在任何支援 Java 的平台上執行  
- **高效能**，適合產生大量簡報或整合至 Web 服務  
- **豐富客製化**，如爆炸效果、孔徑大小、切片角度與標籤格式  

## 前置條件
- 基本的 Java 程式知識  
- IntelliJ IDEA 或 Eclipse 等 IDE  
- Maven 或 Gradle 進行相依管理  
- 有效的 Aspose.Slides for Java 授權（提供免費試用版）

## 設定 Aspose.Slides for Java
選擇符合您專案的相依管理工具。

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

若想直接下載，請前往 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 頁面。

### 授權取得
您可以先使用免費試用版體驗 Aspose.Slides 功能。若需長期使用，請購買授權或從 [Aspose 官方網站](https://purchase.aspose.com/temporary-license/) 申請臨時授權。依照說明設定環境，並在應用程式中初始化 Aspose.Slides。

## 使用 Aspose.Slides for Java 建立甜甜圈圖表 PowerPoint 的步驟
以下提供完整的逐步教學。每段程式碼前都有說明，讓您清楚了解每一步的作用。

### 步驟 1：初始化簡報
先載入既有 PPTX 或建立新檔，為後續的投影片操作做好準備。

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### 步驟 2：在投影片上加入甜甜圈圖表
加入圖表形狀，清除預設的系列/類別，並設定基本的視覺屬性。

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

### 步驟 3：新增圖表資料點並自訂標籤
在此步驟中填入類別、為每個系列加入資料點，並微調標籤外觀。這正是 **add chart data points** 關鍵字的應用時機。

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

### 步驟 4：儲存更新後的簡報
最後，將變更寫入新的 PPTX 檔案。

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## 實務應用
甜甜圈圖表可應用於各種真實情境：
- **財務報告：** 視覺化預算分配或費用明細  
- **市場分析：** 顯示競爭者之市場佔有率分布  
- **調查結果：** 以緊湊方式呈現分類調查資料  
- **儀表板產生：** 結合資料庫查詢，產生即時更新的投影片  

## 效能考量
- **釋放資源**：完成後呼叫 `pres.dispose()` 以釋放原生記憶體  
- **限制圖表數量**：大量圖表會增加記憶體使用，必要時採取批次處理  
- **使用串流**：處理龐大資料集時，直接從串流填充工作簿，避免佔用過多記憶體  

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **圖表顯示空白** | 資料格未正確填入 | 確認 `workBook.getCell(...)` 使用正確的列/欄索引 |
| **標籤重疊** | 類別過多且空間不足 | 增大 `DoughnutHoleSize` 或調整 `FirstSliceAngle` |
| **OutOfMemoryError** | 大型簡報未釋放資源 | 儲存後呼叫 `pres.dispose()`，並考慮增大 JVM 堆積大小 |

## 常見問答

**Q: 可以在商業應用中使用 Aspose.Slides for Java 嗎？**  
A: 可以，但必須擁有有效的商業授權。提供免費試用版供評估使用。

**Q: 如何加入超過 15 個系列？**  
A: 在「新增甜甜圈圖表」步驟中調整迴圈上限，並確保工作簿有足夠的列數。

**Q: 建立後能變更甜甜圈的孔徑大小嗎？**  
A: 可以，在儲存前呼叫 `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` 進行設定。

**Q: 能將圖表匯出為影像而非 PPTX 嗎？**  
A: 完全可以。使用 `chart.getImage()`，將回傳的 `java.awt.image.BufferedImage` 依需求儲存為任意格式。

**Q: Aspose.Slides 支援動畫圖表嗎？**  
A: 可以透過 `ISlide.getTimeline()` API 加入動畫，但此範例未涵蓋此主題。

## 結論
現在您已掌握使用 Aspose.Slides for Java **建立甜甜圈圖表 PowerPoint** 的完整、生產環境可用方法，包含 **add chart data points**、自訂標籤以及效能最佳化技巧。請自行嘗試不同的配色、資料來源與圖表類型，讓您的簡報更具吸引力。

---

**最後更新：** 2026-02-17  
**測試環境：** Aspose.Slides for Java 25.4（JDK 16 classifier）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}