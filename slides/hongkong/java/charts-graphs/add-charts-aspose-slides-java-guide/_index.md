---
date: '2026-02-06'
description: 學習 Aspose Slides 圖表教學，於 Java 簡報中新增與設定圖表，透過一步一步的程式碼範例，簡化您的工作流程。
keywords:
- Aspose.Slides for Java
- adding charts to presentations with Java
- configuring data labels in Aspose.Slides
title: Aspose Slides 圖表教學：使用 Java 添加圖表
url: /zh-hant/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides 圖表教學：使用 Java 在簡報中新增與設定圖表

## Introduction
在許多專業環境中，製作動態簡報是必備技能，無論是商業提案還是學術演講。手動插入圖表既繁瑣又容易出錯。**在本 Aspose Slides 圖表教學中，您將學會如何自動化新增與設定圖表**，使用 Aspose.Slides for Java 為簡報檔案節省時間並降低錯誤。

**您將學到的內容：**
- 設定 Aspose.Slides for Java
- 載入並準備簡報以進行修改
- 在投影片中加入氣泡圖 (Bubble Chart)
- 使用儲存格參照設定資料標籤
- 儲存已修改的簡報

現在就來了解如何透過將 Aspose.Slides 整合至 Java 應用程式，簡化此流程。

### Quick Answers
- **本教學涵蓋什麼內容？** 在 Java 簡報中新增與設定帶資料標籤的氣泡圖。  
- **使用哪個版本的函式庫？** Aspose.Slides for Java 25.4（相容於 JDK 16）。  
- **需要授權嗎？** 測試可使用免費試用版；正式上線需購買永久授權。  
- **可以修改既有圖表嗎？** 可以——您可以載入任何 PPTX，並以程式方式更新其圖表資料。  
- **哪種 IDE 最適合？** 任何支援 Maven 或 Gradle 的 Java IDE（IntelliJ IDEA、Eclipse、VS Code）。

## What is the Aspose Slides chart tutorial?
Aspose Slides 圖表教學示範如何以程式方式在 PowerPoint 檔案內建立、客製化與儲存圖表物件。透過本教學，您可完整掌控圖表類型、資料來源與視覺樣式，無需手動開啟 PowerPoint。

## Why use the Aspose Slides chart tutorial?
- **Automation:** 從資料庫或 API 即時產生圖表。  
- **Consistency:** 確保每份簡報遵循相同的品牌與格式規範。  
- **Cross‑platform:** 同一段 Java 程式碼可在 Windows、Linux 與 macOS 上執行。  
- **No Office dependency:** 伺服器上不必安裝 Microsoft PowerPoint。

## Prerequisites
- **Libraries and Dependencies:** Aspose.Slides for Java（版本 25.4）。  
- **Build Tool:** Maven 或 Gradle（依您偏好選擇）。  
- **Basic Knowledge:** 具備 Java 語法與 PPTX 檔案結構的基本認識。

## Setting Up Aspose.Slides for Java

### Installation Instructions
要將 Aspose.Slides 加入您的專案，可使用 Maven 或 Gradle。以下為設定方式：

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

若您偏好直接下載，請前往 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 頁面。

### License Acquisition
- **Free Trial:** 先使用免費試用版探索功能。  
- **Temporary License:** 若需更長時間且無限制，可申請臨時授權。  
- **Purchase:** 商業使用建議購買完整授權。

設定完成後，初始化 Aspose.Slides 非常簡單。您即可開始載入簡報檔案並為後續修改作好準備。

## Implementation Guide

### Feature 1: Setting Up Presentation

#### Overview
此功能示範如何載入既有簡報檔案，以便使用 Aspose.Slides 進行後續修改。

**Implementation Steps**

##### Step 1: Load the Presentation
```java
import com.aspose.slides.Presentation;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```

- **Why:** 載入簡報檔案是必要的第一步，才能存取並修改其內容。

### Feature 2: Adding a Chart to Slide

#### Overview
此功能示範在簡報的第一張投影片中加入氣泡圖。圖表是視覺化資料的重要工具。

**Implementation Steps**

##### Step 1: Initialize Presentation and Add Chart
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

- **Why:** 加入圖表可提升簡報的視覺吸引力與資訊傳遞效果。

### Feature 3: Configuring Data Labels for a Series

#### Overview
此功能說明如何使用儲存格參照為圖表系列設定資料標籤，提升資料的清晰度與細節呈現。

**Implementation Steps**

##### Step 1: Configure Data Labels
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```

- **Why:** 設定資料標籤能直接在圖表上提供具體洞見，讓觀眾更易理解。

### Feature 4: Saving Presentation

#### Overview
此功能示範如何將已修改的簡報儲存回檔案。

**Implementation Steps**

##### Step 1: Save Your Work
```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

- **Why:** 儲存簡報可確保所有修改被保留，供未來使用。

## Practical Applications
1. **Business Reports:** 自動產生與更新季報中的圖表。  
2. **Academic Presentations:** 使用即時資料視覺化提升課堂講解。  
3. **Sales Pitches:** 建立動態簡報，展示銷售趨勢與預測。  
4. **Project Management:** 可視化專案時間表與資源分配。  
5. **Marketing Analytics:** 將 Aspose.Slides 圖表整合至儀表板，追蹤行銷活動績效。

## Performance Considerations
- 使用高效的資料結構處理圖表的大量資料。  
- 透過 `try‑finally` 區塊正確釋放物件，以管理記憶體。  
- 在處理大型簡報時，優化 Java 記憶體管理技巧。

## Common Issues and Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| **OutOfMemoryError** | PPTX 或圖表資料過大 | 將資料分批處理；釋放物件後呼叫 `System.gc()`。 |
| **Chart not displaying data** | 資料標籤未正確連結 | 確認儲存格參照（`A10`、`A11`、`A12`）與實際工作表儲存格相符。 |
| **License not applied** | 授權檔案遺失或路徑錯誤 | 在建立 `Presentation` 物件前載入授權：`License license = new License(); license.setLicense("Aspose.Slides.lic");` |

## Frequently Asked Questions

**Q: What is Aspose.Slides for Java?**  
A: 一套功能強大的程式庫，可在 Java 應用程式中建立、編輯與轉換 PowerPoint 檔案。

**Q: Can I use Aspose.Slides without a purchase?**  
A: 可以，您可先使用免費試用版測試其功能。

**Q: How do I add different chart types?**  
A: 呼叫 `addChart` 時使用 `ChartType` 列舉（例如 `ChartType.Pie`、`ChartType.Column`）即可加入不同類型的圖表。

**Q: Is it possible to edit existing charts in a presentation?**  
A: 當然可以！載入 PPTX 後，透過 `slide.getShapes().get_Item(index)` 取得圖表，然後修改其屬性。

**Q: What are some common performance pitfalls?**  
A: 大型簡報可能佔用大量記憶體；務必在使用完畢後釋放 `Presentation` 物件，並在可能時重複使用圖表資料工作簿。

## Resources
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-02-06  
**測試環境：** Aspose.Slides for Java 25.4  
**作者：** Aspose