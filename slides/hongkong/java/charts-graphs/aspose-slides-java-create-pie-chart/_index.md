---
date: '2026-02-17'
description: 學習如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中加入圓餅圖。跟隨本一步一步的指南，打造並自訂專業的圓餅圖。
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: 如何使用 Aspose.Slides for Java 為 PowerPoint 添加圓餅圖
url: /zh-hant/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 PowerPoint 中使用 Aspose.Slides for Java 建立與自訂圓餅圖

## 簡介

您是否在 PowerPoint 簡報中難以有效地視覺化資料？**Adding a pie chart PowerPoint** 投影片能立即將原始數字轉化為清晰的視覺故事。使用 Aspose.Slides for Java，您可以以程式方式 **add pie chart PowerPoint** 檔案，完整掌控設計與資料，且無需手動開啟 PowerPoint。本教學將逐步說明整個流程——從設定函式庫到自訂單一資料點——讓您在數分鐘內交付精緻、資料驅動的投影片。

### 快速解答
- **What library do I need?** Aspose.Slides for Java (latest version)。  
- **Can I create a chart without PowerPoint installed?** Yes, the API works completely offline。  
- **Which Java version is required?** JDK 16 or later is recommended。  
- **How do I change a slice’s color?** Use the `setFillType` and `setSolidFillColor` methods on the data point。  
- **Is a license mandatory?** A trial works for development; a permanent license removes evaluation limits。

### 您將學習
- 如何使用 Java 程式化 **add pie chart PowerPoint**。  
- 自訂切片的爆炸效果、顏色及其他視覺屬性的方法。  
- 在處理大型簡報時，資源管理與效能的最佳實踐。

## 為什麼使用 Aspose.Slides for Java 加入 pie chart PowerPoint？
從程式碼直接嵌入圓餅圖，可即時產生最新報告、自動化每月儀表板，或即時建立個人化投影片。它消除手動複製貼上的錯誤，確保簡報的一致性，並能順利整合至現有的 Java 後端。

## 先決條件

在開始之前，請確保您已具備：

- **Aspose.Slides for Java library** – 本教學參考 25.4 版（撰寫時的最新版本）。  
- 相容的 **Java Development Kit (JDK)** – 建議使用 JDK 16 以上。  
- 具備 **Maven** 或 **Gradle** 依賴管理的基本知識。  

## 設定 Aspose.Slides for Java

要開始使用，請將 Aspose.Slides 函式庫加入您的專案。

### Maven
將以下相依性加入您的 `pom.xml` 檔案：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
在您的 `build.gradle` 檔案中加入以下內容：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或者直接從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

### 授權
若要無限制使用 Aspose.Slides：

- 先使用 **free trial** 評估 API。  
- 於 [Temporary License](https://purchase.aspose.com/temporary-license/) 頁面申請 **temporary license** 以進行延長測試。  
- 透過 [Purchase page](https://purchase.aspose.com/buy) 購買完整授權。

## 如何使用 Aspose.Slides for Java 加入 pie chart PowerPoint

以下是一個逐步指南，說明如何建立與自訂圓餅圖。

### 步驟 1：初始化簡報
首先，建立一個新的 `Presentation` 物件。它代表一個空的 PowerPoint 檔案。
```java
Presentation pres = new Presentation();
```

### 步驟 2：加入圓餅圖
在第一張投影片上插入圓餅圖。座標 (50, 50) 與尺寸 (600 × 400) 適用於標準 16:9 投影片。
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### 步驟 3：儲存簡報
將簡報寫入磁碟。將 `YOUR_OUTPUT_DIRECTORY` 替換為您想儲存檔案的資料夾路徑。
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### 步驟 4：清理資源
釋放 `Presentation` 物件以釋放原生資源。
```java
if (pres != null) pres.dispose();
```

## 自訂資料點的爆炸效果與顏色

自訂單一切片可讓圖表更易閱讀，特別是想突顯特定數值時。

### 步驟 1：載入現有簡報（或重複使用剛剛建立的簡報）
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### 步驟 2：存取圖表與目標資料點
此處我們從第一個系列取得第二個資料點（索引 1）。
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### 步驟 3：套用爆炸效果與顏色
將切片視覺上分離，並將填色改為藍色。
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### 步驟 4：儲存與釋放
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## 實務應用
- **Sales Reports:** 以爆炸切片突顯暢銷產品。  
- **Budget Analysis:** 為各部門分配不同顏色，以快速視覺比較。  
- **Educational Slides:** 將複雜概念拆解為易於理解的圖表區段。

## 效能考量
- 及時 **Dispose objects** 以避免記憶體洩漏，特別是在迴圈中產生大量投影片時。  
- 對大型簡報 **Monitor heap usage**；可考慮使用接受 `OutputStream` 的 `Save` 重載進行串流輸出。  
- 使用 **JDK 16+** 以獲得最新的垃圾回收改進。

## 結論
您現在已掌握使用 Aspose.Slides for Java **add pie chart PowerPoint** 檔案的完整、可投入生產的工作流程。可嘗試不同的爆炸距離、顏色與資料集，以符合品牌需求。準備好後，亦可探索其他圖表類型——長條圖、折線圖或散佈圖，打造完整的 PowerPoint 分析儀表板。

## 常見問題

1. **What is the primary advantage of using Aspose.Slides for Java?**  
   - 它簡化了以程式方式建立與操作 PowerPoint 檔案，提供豐富的功能。  
2. **Can I customize other chart types with Aspose.Slides?**  
   - 當然！Aspose.Slides 支援多種圖表類型，如長條圖、折線圖與散佈圖。  
3. **How do I handle multiple slides when creating charts?**  
   - 使用 `get_Item()` 方法依索引存取每張投影片，以在不同投影片上套用變更。  
4. **What if my pie chart doesn't display correctly after customization?**  
   - 請確認 `addChart()` 使用的座標與尺寸是否符合投影片版面配置。  
5. **Where can I find more advanced features for Aspose.Slides?**  
   - 可前往 [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) 了解更多功能與選項。

## 資源
- **Documentation:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Download Library:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Purchase License:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporary License:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}