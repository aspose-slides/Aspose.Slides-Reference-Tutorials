---
date: '2026-09-17'
description: 了解如何使用 Aspose.Slides for Java 建立 bubble chart PowerPoint。本指南示範如何將 chart
  加入 slide、設定 bubble size，以及有效率地儲存 PPTX。
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: 了解如何使用 Aspose.Slides for Java 建立 bubble chart PowerPoint。本教學說明如何將
  chart 加入 slide、調整 bubble size，並有效率地儲存 presentation。
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: 使用 Aspose.Slides for Java 建立 bubble chart PowerPoint
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: 使用 Aspose.Slides for Java 建立 bubble chart PowerPoint
url: /zh-hant/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Slides for Java 建立氣泡圖 PowerPoint

## 簡介
如果您需要以程式方式 **建立氣泡圖 PowerPoint** 簡報，Aspose.Slides for Java 為您提供一個乾淨的伺服器端 API，無需 Microsoft Office 即可運作。在本教學中，您將學習如何在投影片中加入圖表、控制氣泡大小，並在有效管理資源的同時儲存最終的 PPTX。步驟已拆解，您可以直接將程式碼複製貼上至任何 Java 專案，即時看到結果。

## 快速解答
- **需要哪個函式庫？** Aspose.Slides for Java
- **需要哪個 Java 版本？** JDK 16 or higher
- **如何新增氣泡圖？** Call `addChart(ChartType.Bubble, …)` on a slide
- **可以變更氣泡大小嗎？** Yes, via `setBubbleSizeScale()`
- **如何儲存檔案？** Use `pres.save("Result.pptx", SaveFormat.Pptx)`

## 什麼是建立氣泡圖 PowerPoint？
在 PowerPoint 中建立氣泡圖表示以程式方式產生圖表，每個資料點以氣泡表示，其 X 位置、Y 位置與大小分別編碼三個資料維度。Aspose.Slides for Java 會處理渲染，您無需安裝 PowerPoint。

## 為什麼使用 Aspose.Slides for Java？
Aspose.Slides 支援 **50+ 圖表類型**，可在不將整個檔案載入記憶體的情況下處理高達 **2 GB** 的簡報，且可在任何支援 Java 16+ 的平台上執行。這些具體的能力使其成為企業級報告的可靠選擇。

## 先決條件
- 已安裝 **Java Development Kit** 16 或更新版本。
- **Aspose.Slides for Java** 函式庫（透過 Maven、Gradle 或直接下載 JAR 加入）。
- 具備 Java 語法與物件導向程式設計的基本知識。

## 設定 Aspose.Slides for Java
要開始使用 Aspose.Slides，請將函式庫加入您的建置系統。

### Maven
將以下相依性加入您的 `pom.xml`：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Include this in your `build.gradle`：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
您也可以從 [Aspose.Slides Documentation](https://releases.aspose.com/slides/java/) 取得最新的 JAR。

#### 取得授權
- **免費試用** – 無需費用即可探索所有功能。  
- **暫時授權** – 為較大型專案提供延長評估。  
- **完整授權** – 生產環境部署所必需。

### 基本初始化與設定
`Presentation` 類別是建立或載入 PowerPoint 檔案的入口點。  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## 實作指南
以下是建立氣泡圖並管理資源的逐步說明。

## 如何建立氣泡圖 PowerPoint
在本節中，您將學習產生氣泡圖、設定視覺屬性以及將結果保存為 PPTX 檔案所需的 API 呼叫順序。此方法適用於任何包含 Aspose.Slides 且遵循最佳資源處理慣例的 Java 專案。

載入簡報、加入氣泡圖、設定外觀，然後儲存檔案。

### 直接答案
建立新的 `Presentation`，在目標投影片上呼叫 `addChart(ChartType.Bubble, …)`，使用 `setBubbleSizeScale(150)` 調整氣泡大小比例，最後以 `pres.save("Result.pptx", SaveFormat.Pptx)` 儲存。此序列僅需幾行 Java 程式碼即可加入完整功能的氣泡圖。

- **`ChartType.Bubble`** 代表氣泡圖類型。  
- **`addChart`** 在投影片上插入指定類型的新圖表。  
- **`setBubbleSizeScale`** 調整圖表中氣泡的整體大小。  
- **`SaveFormat.Pptx`** 指定儲存為 PPTX 檔案格式。

#### 逐步實作
**1. 初始化簡報** – 建立 `Presentation` 物件的實例。  
```java
Presentation pres = new Presentation();
```

**2. 新增氣泡圖** – 在選定的座標插入圖表。  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` 告訴 Aspose.Slides 建立氣泡圖。  
- 數值參數定義以點 (points) 為單位的 X/Y 位置與寬度/高度。

**3. 設定氣泡大小比例** – 放大氣泡以獲得更佳視覺效果。  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- 將比例設定為 **150 %**，使每個氣泡比預設大 1.5 倍。

**4. 儲存簡報** – 將 PPTX 寫入磁碟。  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### 故障排除技巧
- 確認輸出資料夾具有寫入權限。  
- 確認 Aspose.Slides JAR 與您使用的 JDK 版本相符。

## 如何有效管理 PowerPoint 資源
有效的資源處理可防止記憶體洩漏並降低 JVM 的佔用，特別是在處理大型簡報或於伺服器環境執行時。遵循以下模式，即使發生例外，也能確保釋放本機資源。

有 效的資源處理可防止記憶體洩漏，尤其在處理大型簡報時。

### 直接答案
完成 `Presentation` 的使用後，務必在 `try‑finally` 區塊中呼叫 `pres.dispose()`；此舉會釋放本機資源，讓 JVM 立即回收記憶體。

- **`pres.dispose()`** 釋放簡報使用的本機資源。

**1. 建立與修改** – 按需求操作簡報。  
```java
Presentation pres = new Presentation();
```

**2. 釋放資源** – 處理完成後釋放記憶體。  
```java
if (pres != null) pres.dispose();
```

## 實務應用
氣泡圖在需要同時視覺化三個資料維度的情境中表現優異：

1. **市場分析** – 氣泡大小代表營收，X/Y 軸分別顯示成長與市場佔有率。  
2. **績效指標** – 比較員工生產力 (X)、滿意度 (Y) 與影響力 (size)。  
3. **地理資料** – 以氣泡大小編碼人口，繪製城市分布。  
4. **專案管理** – 在單一投影片上以 X 軸呈現時間線、Y 軸呈現成本，氣泡大小呈現風險。

## 效能考量
- **資源使用** – 及時釋放簡報以保持堆積記憶體使用量低。  
- **Java 記憶體管理** – 使用 `try‑finally` 包裹簡報操作，確保即使發生例外也能釋放。  
- **保持最新** – 升級至最新的 Aspose.Slides 版本，以獲得效能優化與錯誤修正。

## 常見問答

**Q: 什麼是 Aspose.Slides for Java？**  
A: Aspose.Slides for Java 是一個獨立的函式庫，讓您無需 Microsoft Office 即可建立、編輯與轉換 PowerPoint 檔案。

**Q: 如何將 Aspose.Slides 整合到現有的 Java 專案中？**  
A: 加入前述的 Maven 或 Gradle 相依性，或將 JAR 放入 classpath，然後匯入 `com.aspose.slides.*`。

**Q: 可以使用 Aspose.Slides 處理大型簡報嗎？**  
A: 可以，該函式庫能有效處理高達 **2 GB** 的簡報，並支援串流以避免將整個檔案載入記憶體。

**Q: 除了氣泡圖，還支援哪些圖表類型？**  
A: 支援超過 **50 種圖表類型**，包括長條圖、折線圖、圓餅圖、雷達圖與瀑布圖等。

**Q: 是否內建支援圖表元素的樣式設定？**  
A: 當然可以。您可透過圖表的 `ChartSeries` 與 `ChartTitle` 物件自訂顏色、字型、邊框與資料標籤。

## 資源
- **文件**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **下載**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **購買**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **免費試用**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **暫時授權**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **支援**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**最後更新：** 2026-09-17  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.Slides for Java 在 PowerPoint 中加入圖表：逐步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java 使用 Aspose.Slides 建立 PowerPoint 圖表](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [建立 PowerPoint 圖表 Java – 使用 Aspose.Slides 儲存含圖表的簡報](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}