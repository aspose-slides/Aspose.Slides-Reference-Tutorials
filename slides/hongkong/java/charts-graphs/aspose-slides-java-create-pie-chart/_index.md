---
date: '2026-01-19'
description: 學習如何使用 Aspose.Slides for Java 在 PowerPoint 中建立餅圖、客製化顏色，並輕鬆儲存簡報。
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: 使用 Aspose.Slides for Java 建立餅圖 PowerPoint
url: /zh-hant/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 建立圓餅圖 PowerPoint

## 介紹

您是否在 PowerPoint 簡報中難以有效地視覺化資料？使用 Aspose.Slides for Java **建立圓餅圖 PowerPoint** 可讓這個過程變得輕鬆，讓您專注於資料背後的故事。本指南將帶您完整走過 **java 圓餅圖範例**，示範如何 **變更存 PowerPoint 簡報** 檔案方式。完成後ides for Java  
- **建議使用哪個 Java 版本？** JDK 16 或更新圓餅圖需要多少行程式碼？** 約 5 行  
- **可以自訂切片顏色嗎？** 可以，使用 Fill API  
- **簡報預設儲存為何種格式？** 預設為 PPTX  

### 您將學會
- 如何以程式方式 **建立圓餅圖 PowerPoint**更圓餅圖顏 簡報** 的步驟與注意事項  
- 管理 for Java本教學原本使用 25.4 版，任何較新版本皆可）  
- 相容的 Java Development Kit（JDK 16 或更新版本）  
- 基本的 Java 知識以及 Maven 或 Gradle 建置工具  

## 設定 Aspose.Slides for Java

要開始使用，請將 Aspose.Slides 函式庫加入您的專案。

### Maven
在 `pom.xml` 檔案中加入以下相依性：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
在 `build.gradle` 檔案中加入以下內容：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或者直接從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載最新版本。

### 授權
若要無限制使用 Aspose.Slides：
- 先使用免費試用版評估功能。  
- 若需線，請於 [Temporary License](https://purchase.aspose.com/temporary-license/) 申請臨時授權。  
- 透過 [Purchase page](https://purchase.aspose.com/buy) 購買訂閱，即可取得完整授權。

## 實作指南

### 建立圓餅圖
建立圓餅圖的流程包括初始化 `Presentation` 物件，並將圖表加入投影片。以下分步說明。

#### 步驟 1：初始化 Presentation
建立 `Presentation` 類別的實例。
```java
Presentation pres = new Presentation();
```

#### 步驟 2：加入圓餅圖
在第一張投影片上以指定的尺寸與位置加入圓餅圖：
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```
*說明：* 此程式碼會在座標 (50, 50) 處放置寬 600、高 400 的圓餅圖。

#### 步驟 3：儲存簡報
圖表設定完成後，將簡報儲存起來：
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```
*說明：* `save` 方法會將變更寫入指定目錄的檔案。

#### 資源清理
為防止記憶體洩漏，請務必釋放資源：
```java
if (pres != null) pres.dispose();
```

### 設定資料點的爆炸效果與顏色
自訂資料點可提升可讀性。以下示範如何修改特定資料點的外觀。

#### 步驟 1：開啟既有簡報
載入您想要自訂圖表的簡報檔案。
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

#### 步驟 2：存取並修改資料點
取得第一個系列中的資料點：
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```
*說明：* 此程式碼會存取第二個資料點以進行自訂。

#### 步驟 3：套用爆炸效果與顏色
設定爆炸以視覺上分離，並變更其顏色：
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```
*說明：* `setExplosion` 方法會產生視覺偏移，透過設定填滿類型與顏色即可客製化外觀。

#### 資源清理
完成修改後，請釋放資源：
```java
if (pres != null) pres.dispose();
```

## 如何變更圓餅圖顏色
Aspose.Slides 提供彈性的 Fill API。只要將 `FillType` 設為 `Solid`，並提供 `Color` 物件，即可將任意切片設定為符合品牌指引的顏色。此功能在需要 **變更圓餅圖顏色** 以強調或提升可及性時特別有用。

## 如何儲存 PowerPoint 簡報
`save` 方法支援多種格式（`Pptx`、`Pdf`、`Html` 等）。大多數情況下您會選擇以 PPTX 格式儲存，因為它保留所有圖表的互動性。記得指定正- **銷售報告：**點突顯關鍵指標。  
- **預算分析：** 使用不同顏色代表各部門。  
- **教學教材：** 透過視覺區分圖表元素，簡化複雜主題。

將這些圓餅圖整合至儀表板、報告與簡報中，讓各平台的受眾更易掌握洞見。

## 效能考量
使用 Aspose.Slides 時：
- 透過適時釋放物件來有效管理資源。  
- 在大型操作期間監控記憶體使用，以防止洩漏。  
- 遵循 Java 記憶體管理的最佳實踐，維持最佳效能。

這些技巧可確保您的應用程式執行順暢、資源使用得當。

## 結論
您現在已掌握完整的 **java 圓餅圖範例**，了解如何 **建立圓餅圖 PowerPoint**、**變更圓餅圖顏色**，以及 **儲存 PowerPoint 簡報**。請自行嘗試不同設定，以符合您的簡報需求，並探索其他圖表類型與進階客製化選項。

## FAQ 區段
1. **使用 Aspose.Slides for Java 的主要優勢是什麼？**  
   - 它讓您以程式方式簡化 PowerPoint 檔案的建立與操作，功能相當完整。  
2影片的圖表時？**  
   - 使用 `get_Item()` 方法依索引存取每張投影片，並在不同投影片上套用變更。  
該怎麼辦？**  
   - 請確認 `addChart()` 所使用的座標與尺寸是否適合投影片版面。  
5. ** Aspose.Slides 的進階功能說明？**  
   - 前往 [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) 探索更多，只要SaveFormat` 設為 `Pdf` 即可。

**Q` 與 `IAnimation` API 加入動畫效果。

**Q: 如何為整個簡報套用自訂主題？**  
A: 使用 `pres.getPresentation().getThemeManager().applyTheme(...)` 載入 `.thmx` 檔案即可。

**Q: 哪裡可以找到更多程式碼範例？**  
A: 官方的 Aspose.Slides GitHub 倉庫與文件網站皆提供大量範例。

## 資源
- **文件說明：** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **下載函式庫：** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **購買授權：** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **免費試用：** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **臨時授權：** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **支援論壇：** [Aspose Support](https://forum.aspose.com/c/slides/11)

現在您已具備所有必要知識，快去建立令人驚豔的品質吧！祝您開發愉快！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：4  
**