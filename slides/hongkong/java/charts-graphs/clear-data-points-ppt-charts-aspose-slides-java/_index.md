---
date: '2026-08-27'
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 中清除圖表資料點。本分步教學展示如何以程式方式清除圖表數值、最佳實踐以及有效的系列處理。
keywords:
- how to clear chart
- programmatically clear chart
- remove chart data points
- Aspose.Slides Java chart manipulation
- PowerPoint chart automation
lastmod: '2026-08-27'
og_description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 中清除圖表資料點。遵循分步說明，以程式方式有效重設圖表。
og_image_alt: Code example showing how to clear chart data points in a PowerPoint
  presentation using Aspose.Slides for Java
og_title: 如何使用 Aspose.Slides for Java 清除 PowerPoint 圖表資料點
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  headline: 'How to clear data points in PowerPoint charts using Aspose.Slides for
    Java: a comprehensive guide'
  type: TechArticle
- description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  name: 'How to clear data points in PowerPoint charts using Aspose.Slides for Java:
    a comprehensive guide'
  steps:
  - name: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
    text: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
  - name: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
    text: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
  - name: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
    text: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
  - name: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
    text: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
  - name: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
    text: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
  - name: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
    text: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
  - name: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
    text: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
  - name: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
    text: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
  type: HowTo
- questions:
  - answer: A free trial license is sufficient for development and testing. A commercial
      license is required for production deployments.
    question: Do I need a license for development builds?
  - answer: Yes, the library fully supports modern PPTX features, including advanced
      chart types and SmartArt.
    question: Does Aspose.Slides for Java support PowerPoint 2016/2019 features?
  - answer: Absolutely – just reference the series that belongs to the secondary axis
      and set its data points to `null` as described above.
    question: Can I clear data points in a chart that uses a secondary axis?
  - answer: Yes. Call `dataPoint.getYValue().setValue(null)` and leave the X cell
      untouched.
    question: Is it possible to clear only Y values while keeping X labels?
  - answer: Wrap the clearing code in a loop that iterates over a directory of PPTX
      files, applying the same logic to each file.
    question: How can I automate this for multiple presentations?
  type: FAQPage
tags:
- clear chart
- Aspose.Slides
- Java chart manipulation
- PowerPoint automation
- chart data points
title: 如何使用 Aspose.Slides for Java 清除 PowerPoint 圖表中的資料點：完整指南
url: /zh-hant/java/charts-graphs/clear-data-points-ppt-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Slides for Java 清除 PowerPoint 圖表中的資料點

## 簡介

在許多報告流程中，您需要 **重設圖表** 而無需重新建立其版面配置。無論您是刷新儀表板、發佈範本，或自動化夜間報告，了解 **如何清除圖表** 資料點都能節省時間並減少錯誤。本教學將示範如何使用 **Aspose.Slides for Java** 以程式方式清除特定資料點或整個系列，同時保留視覺樣式。

**您將學習**
- Aspose.Slides 如何讓您從 Java 操作 PowerPoint 圖表。  
- 逐步說明如何在系列中清除圖表資料點。  
- 效能與授權的最佳實踐技巧。

## 快速解答
- **需要的函式庫是什麼？** Aspose.Slides for Java (v25.4+)。  
- **哪個方法實際清除資料點？** Setting the X and Y cell values to `null`。  
- **生產環境需要授權嗎？** 是 – 商業授權可移除試用限制。  
- **支援 Java 16 嗎？** 絕對支援；此函式庫可在 JDK 16 及更新版本上運作。  
- **可以只針對單一系列嗎？** 可以 – 只遍歷您想要清除的特定系列。

## Aspose.Slides for Java 是什麼？

Aspose.Slides for Java 是一套功能完整的 API，讓您在沒有 Microsoft Office 的情況下建立、編輯與轉換 PowerPoint 檔案。它支援超過 70 種圖表類型、150+ 檔案格式，且可在不將整個檔案載入記憶體的情況下處理高達 500 MB 的簡報。

## 為什麼要清除圖表資料點？

清除圖表資料點可讓您保留現有的圖表版面配置——例如顏色、圖例、座標軸設定與標記——同時替換底層的數值。此方法在需要以新資料刷新圖表、提供帶有空白佔位的範本，或產生頻繁變更而不需重新構建視覺設計的動態儀表板時非常有用。

- 以新資料集刷新圖表，同時保留顏色、圖例與座標軸設定。  
- 發佈包含空白圖表的範本，供使用者輸入。  
- 建立資料頻繁變動的動態儀表板。

## 如何使用 Aspose.Slides for Java 在 PowerPoint 中清除圖表資料點

載入簡報，定位圖表，並將每個資料點的 X 與 Y 儲存格設為 `null`。此操作會移除數值，但保留系列、標記與格式設定不變。對於標準的 10 頁 PPTX，整個流程通常在一秒內完成。

### 直接答案
要清除圖表資料點，先以 `new Presentation("input.pptx")` 開啟 PPTX，取得目標 `IChart` 物件，遍歷所需的 `IChartSeries`，並對每個點呼叫 `dataPoint.getXValue().setValue(null)` 與 `dataPoint.getYValue().setValue(null)`。最後，使用 `pres.save("output.pptx", SaveFormat.Pptx)` 儲存簡報。此方法以程式方式清除資料，同時保留圖表的視覺設計。

### 定義錨點
- `Presentation` 是 Aspose.Slides 的頂層物件，代表記憶體中的 PowerPoint 檔案。  
- `IChart` 是介面，可存取圖表形狀的系列、座標軸與格式設定。  
- `IChartSeries` 代表圖表中的單一系列，並包含一系列 `IDataPoint` 物件。  
- `IDataPoint` 保存圖表中某個點的個別 X 與 Y 值。

### 步驟實作

1. **載入簡報** – 建立指向來源檔案的 `Presentation` 實例。  
   ```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

2. **存取投影片與圖表** – 取得投影片（通常是索引 0），並將第一個形狀轉型為 `IChart`。  
   ```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

3. **遍歷目標系列** – 選取要清除的系列（例如 `chart.getChartData().getSeries().get_Item(0)`），並對其資料點迴圈，將 X 與 Y 儲存格值設為 `null`。  
   ```java
import com.aspose.slides.*;

public class ChartManipulation {
    public static void main(String[] args) {
        Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
        try {
            // Your code here
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

4. **儲存已修改的簡報** – 將變更寫入新檔案或覆寫原檔。  
   ```java
   Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
   ```

## 設定 Aspose.Slides for Java

### Maven 安裝

```java
   ISlide sl = pres.getSlides().get_Item(0);
   IChart chart = (IChart) sl.getShapes().get_Item(0);
   ```

### Gradle 安裝

```java
   for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
       dataPoint.getXValue().getAsCell().setValue(null);
       dataPoint.getYValue().getAsCell().setValue(null);
   }
   ```

### 直接下載

或者，從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

### 取得授權

若要在試用限制之外使用 Aspose.Slides：
- 取得 **免費試用** 授權。  
- 申請 **暫時授權** 以供評估。  
- 購買 **商業授權** 用於正式環境。

#### 基本初始化與設定

```java
   pres.save("YOUR_DOCUMENT_DIRECTORY/UpdatedTestChart.pptx", SaveFormat.Pptx);
   ```

## 實務應用

清除圖表資料點在許多實務情境中都很有用：

1. **資料刷新流程** – 在不重新建立圖表版面配置的情況下，用最新的分析取代過時的數字。  
2. **範本發佈** – 提供包含空白圖表、可供使用者輸入的 PowerPoint 範本。  
3. **動態儀表板** – 產生每晚從 API 抓取資料的簡報，先清除舊有數值。  
4. **自動化報告工作** – 將清除邏輯整合至 CI/CD 流程，以自動產生報告。

## 效能考量

- **釋放物件**：儲存後呼叫 `pres.dispose()` 以釋放本機資源。  
- **批次處理**：在多個檔案間重複使用單一 `License` 實例，以減少開銷。  
- **JVM 調校**：處理超過 200 MB 的簡報時，增加堆積大小（`-Xmx2g` 或更高）。  
- **記憶體效能模式**：Aspose.Slides 可串流大型 PPTX 檔案，允許在不完整載入記憶體的情況下處理多達 10 000 張投影片。

## 常見問題

**Q: 開發版需要授權嗎？**  
A: 免費試用授權足以用於開發與測試。正式部署則需商業授權。

**Q: Aspose.Slides for Java 是否支援 PowerPoint 2016/2019 功能？**  
A: 是，函式庫完整支援現代 PPTX 功能，包括進階圖表類型與 SmartArt。

**Q: 能否清除使用次要座標軸的圖表資料點？**  
A: 絕對可以 – 只要參照屬於次要座標軸的系列，並如上所述將其資料點設為 `null`。

**Q: 是否可以只清除 Y 值而保留 X 標籤？**  
A: 可以。呼叫 `dataPoint.getYValue().setValue(null)`，而不變動 X 儲存格。

**Q: 如何將此自動化應用於多個簡報？**  
A: 將清除程式碼包在迴圈中，遍歷 PPTX 檔案目錄，對每個檔案套用相同邏輯。

## 資源

- [Aspose.Slides 文件](https://reference.aspose.com/slides/java/)
- [下載 Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [購買授權](https://purchase.aspose.com/buy)
- [免費試用版](https://releases.aspose.com/slides/java/)
- [暫時授權申請](https://purchase.aspose.com/temporary-license/)
- [Aspose 社群論壇](https://forum.aspose.com/c/slides/11)

有了這些資源，您即可在 Java 應用程式中開始清除圖表資料點。祝開發愉快！

---

**最後更新：** 2026-08-27  
**測試環境：** Aspose.Slides for Java 25.4 (JDK 16)  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.Slides for Java 編輯 PowerPoint 圖表資料：完整指南](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [如何使用 Aspose.Slides for Java 為 PowerPoint 新增圖表：逐步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [在 Java Slides 中清除特定圖表系列資料點](/slides/java/java-slides-chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}