---
date: '2026-07-08'
description: 了解如何使用 Aspose.Slides for Java 為 PowerPoint 簡報加入圓餅圖。遵循本步驟指南，建立並自訂專業的圓餅圖。
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: 使用 Aspose.Slides for Java 為 PowerPoint 加入圓餅圖。本教學示範如何以程式方式產生與自訂圓餅圖，適用於自動化報告。
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: 使用 Aspose.Slides for Java 在 PowerPoint 中加入圓餅圖 – 快速指南
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: 如何使用 Aspose.Slides for Java 在 PowerPoint 中加入圓餅圖
url: /zh-hant/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 新增圓餅圖 PowerPoint

## 介紹

如果您需要 **新增圓餅圖 PowerPoint** 投影片，而不必手動開啟 PowerPoint，本教學正適合您。本文將說明如何設定 Aspose.Slides for Java、建立圓餅圖，並自訂每一片——非常適合自動化報表、儀表板或個人化簡報。完成後，您將擁有一段可重複使用的 Java 程式碼，能在數秒內產生精緻的圓餅圖 PowerPoint 檔案。

### 快速答覆
- **哪個函式庫負責產生圖表？** Aspose.Slides for Java（最新發行版）。  
- **可以在無介面的環境下執行嗎？** 可以——不需要安裝 Office。  
- **哪個 Java 版本最佳？** JDK 16 以上，效能與 GC 改進最佳。  
- **如何將某片切片「爆炸」？** 在 `IDataPoint` 上呼叫 `setExplosion` 並設定像素偏移。  
- **正式環境需要授權嗎？** 開發可使用試用版；正式授權會移除所有評估限制。

## 為什麼要使用 Aspose.Slides for Java 新增圓餅圖 PowerPoint？

您可以直接從後端服務產生即時視覺報表，消除手動複製貼上的錯誤，並確保品牌樣式一致。Aspose.Slides 支援 **70+ 種圖表類型**，且可處理 **10,000+ 投影片** 的簡報而不必一次載入整個檔案，非常適合大規模自動化。

## 前置條件

- **Aspose.Slides for Java** – 本教學使用 25.4 版（撰寫時的最新版本）。  
- **Java Development Kit** – 建議使用 JDK 16 或更新版本。  
- **Maven** 或 **Gradle** 以管理相依性。  

## 設定 Aspose.Slides for Java

### Maven
在 `pom.xml` 中加入以下相依性：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
在 `build.gradle` 中加入以下內容：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或者直接從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

### 授權
若要無限制使用 Aspose.Slides：

- 先取得 **免費試用** 以評估 API。  
- 前往 [Temporary License](https://purchase.aspose.com/temporary-license/) 頁面申請 **臨時授權** 以延長測試。  
- 於 [Purchase page](https://purchase.aspose.com/buy) 購買完整授權。

## 使用 Aspose.Slides for Java 新增圓餅圖 PowerPoint 的步驟

載入新簡報、插入圓餅圖，最後儲存檔案——只需三個簡潔步驟。此模式適用於任何資料量，亦可放入迴圈自動產生多張投影片。程式碼輕量、僅需少數行且不依賴外部資源，適合小工具或大型批次作業。

### 步驟 1：初始化 Presentation
`Presentation` 類別代表記憶體中的單一 PowerPoint 檔案。建立實例即可取得全新的空白投影片集。
```java
Presentation pres = new Presentation();
```

### 步驟 2：新增圓餅圖
在第一張投影片上插入圓餅圖。座標 (50, 50) 與大小 (600 × 400) 符合標準 16:9 版面，並留有標題空間。
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### 步驟 3：儲存 Presentation
將簡報寫入磁碟。將 `YOUR_OUTPUT_DIRECTORY` 替換為您希望儲存檔案的資料夾路徑。
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### 步驟 4：清理資源
釋放 `Presentation` 物件以釋放原生資源，避免記憶體泄漏。
```java
if (pres != null) pres.dispose();
```

## 如何自訂資料點的爆炸效果與顏色？

載入圖表、定位目標資料點，然後套用爆炸偏移與實心填色。此方式可讓切片突顯，強調關鍵數值，提升圖表可讀性。

### 步驟 1：載入既有 Presentation（或使用剛建立的）
`Presentation` 物件會將既有 PowerPoint 檔案載入記憶體，讓您修改內容。
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### 步驟 2：取得圖表與目標資料點
`IDataPoint` 介面代表圖表系列中的單一資料點（切片）。
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### 步驟 3：套用爆炸與顏色
`setExplosion(int)` 設定切片相對於圖表中心的像素偏移距離。使用 `setExplosion(20)` 讓切片視覺上分離，並透過 `setFillType(FillType.Solid)` 與 `setSolidFillColor(Color.BLUE)` 將填色改為藍色。
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### 步驟 4：儲存並釋放
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## 實務應用
- **銷售報表：** 以爆炸切片突顯熱銷產品。  
- **預算分析：** 為各部門指派不同顏色，快速視覺比較。  
- **教學投影片：** 將複雜概念拆解為易懂的圖表片段。  

## 效能考量
- **即時釋放物件** 以避免記憶體泄漏，特別是在迴圈產生大量投影片時。  
- **監控堆積使用量**，對於大型簡報可使用接受 `OutputStream` 的 `Save` 重載，以串流方式寫入，降低記憶體占用。  
- 採用 **JDK 16+** 可受惠於最新的垃圾回收改進，對 1,000 張投影片的簡報處理時間可縮短約 30 %。  

## 結論
現在您已掌握使用 Aspose.Slides for Java **新增圓餅圖 PowerPoint** 檔案的完整、可投入生產的工作流程。可自行調整爆炸距離、顏色與資料集，以符合品牌需求。完成後，亦可探索其他圖表類型——長條圖、折線圖或散佈圖，打造完整的 PowerPoint 分析儀表板。

## 常見問答

**Q: 使用 Aspose.Slides for Java 最大的優勢是什麼？**  
A: 它讓您在不安裝 Microsoft Office 的情況下，以程式方式建立、編輯與轉譯 PowerPoint 檔案，支援超過 70 種圖表類型與 100 + 檔案格式。

**Q: 我可以從頭開始產生 PowerPoint 檔案嗎？**  
A: 可以，建立 `Presentation` 物件、加入投影片、圖表或圖形，最後呼叫 `save`——全程純 Java 程式碼。

**Q: 如何爆炸特定的圓餅切片？**  
A: 取得該切片的 `IDataPoint`，呼叫 `setExplosion(pixelOffset)`。偏移值決定切片向外移動的距離。

**Q: 能建立的投影片數量有限制嗎？**  
A: Aspose.Slides 可處理單一檔案內最多 **10,000 張投影片**，只要使用串流輸出避免一次載入全部內容即可。

**Q: 哪裡可以找到更進階的圖表自訂範例？**  
A: 請參考官方的 [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) 取得完整 API 說明與範例專案。

## 資源
- **文件說明：** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **下載函式庫：** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **購買授權：** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **免費試用：** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **臨時授權：** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **支援論壇：** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**最後更新：** 2026-07-08  
**測試環境：** Aspose.Slides for Java 25.4（JDK 16 classifier）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create and Validate Chart Layouts in PowerPoint Using Aspose.Slides for Java | SEO-Optimized Guide](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}