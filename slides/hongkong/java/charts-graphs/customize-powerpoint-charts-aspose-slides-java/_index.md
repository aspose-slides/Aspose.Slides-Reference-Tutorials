---
date: '2026-09-07'
description: 學習如何使用 Java 為 Aspose Slides 圖表新增自訂線條。一步一步的指南可增強 PowerPoint 圖表，使資料可視化更清晰。
keywords:
- aspose slides chart
- customize PowerPoint charts
- add custom lines to charts Java
lastmod: '2026-09-07'
og_description: 學習如何使用 Java 為 Aspose Slides 圖表新增自訂線條。本指南提供一步一步的自訂方法，讓資料可視化更清晰。
og_image_alt: Developer guide showing custom line addition to an Aspose Slides chart
  in Java
og_title: 如何在 Java 中為 Aspose Slides 圖表新增自訂線條
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to add custom lines to an Aspose Slides chart using Java.
    Step‑by‑step guide enhances PowerPoint charts for clearer data visualization.
  headline: How to add custom lines to an Aspose Slides chart in Java
  type: TechArticle
- description: Learn how to add custom lines to an Aspose Slides chart using Java.
    Step‑by‑step guide enhances PowerPoint charts for clearer data visualization.
  name: How to add custom lines to an Aspose Slides chart in Java
  steps:
  - name: create a presentation object
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a single PowerPoint file in memory.
  - name: add a clustered column chart
    text: Insert a clustered column chart on the first slide at coordinates (100,
      100) with a width of 500 px and a height of 400 px.
  - name: add an auto‑shape line to the chart
    text: Add a line shape to the chart’s `userShapes` collection, which stores custom
      drawing objects. `userShapes` is a collection that holds custom shapes drawn
      directly on a chart, allowing you to overlay lines, arrows, or other annotations.
  - name: customize line properties
    text: Set the line’s fill type to solid, change its color to red, and optionally
      adjust thickness or dash style.
  - name: save the presentation
    text: Persist the modified presentation to disk.
  type: HowTo
- questions:
  - answer: '`Presentation` represents a PowerPoint file in memory.'
    question: What is the main class for creating a presentation?
  - answer: '`slide.getShapes().addChart(...)` creates a chart object.'
    question: Which method adds a chart to a slide?
  - answer: Use `chart.getUserShapes().addAutoShape(ShapeType.Line, ...)`.
    question: How do you draw a line on a chart?
  - answer: Yes—set the line’s fill to a solid red `Color.RED`.
    question: Can I set the line color to red?
  - answer: A full license removes evaluation limits; a trial works for testing.
    question: Do I need a license for production use?
  type: FAQPage
tags:
- aspose slides
- chart customization
- java presentation
title: 如何在 Java 中為 Aspose Slides 圖表新增自訂線條
url: /zh-hant/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中為 Aspose Slides 圖表添加自訂線條

## 介紹

在本教學中，您將學習如何使用 Java 為 **aspose slides chart** 添加自訂線條。自訂線條可協助您突顯門檻、趨勢或關鍵資料點，將普通圖表轉變為有力的視覺敘事。完成本指南後，您將能將 Aspose.Slides 整合至專案中，在圖表上繪製線條，並微調其外觀以達到最佳效果。

**您將學習**
- 如何安裝與授權 Aspose.Slides for Java
- 在圖表上繪製自訂線條的具體步驟
- 線條樣式的設定方式（顏色、粗細、虛線樣式）
- 自訂線條提升資料傳達的實務情境

## 快速解答
- **建立簡報的主要類別是什麼？** `Presentation` 代表記憶體中的 PowerPoint 檔案。  
- **哪個方法可將圖表新增至投影片？** `slide.getShapes().addChart(...)` 會建立圖表物件。  
- **如何在圖表上繪製線條？** 使用 `chart.getUserShapes().addAutoShape(ShapeType.Line, ...)`。  
- **我可以將線條顏色設為紅色嗎？** 可以—將線條的填充設定為純紅色 `Color.RED`。  
- **生產環境是否需要授權？** 完整授權可移除評估限制；試用版可用於測試。  

`ShapeType.Line` 是一個列舉值，告訴 Aspose.Slides 建立線條形狀的自動圖形。

## 什麼是 Aspose Slides 圖表？

**Aspose Slides 圖表** 是一個可程式化的圖表物件，存在於 PowerPoint 投影片內，讓您能完全透過 Java 程式碼產生、修改與樣式化圖表。它支援多種圖表類型（柱狀、條形、折線、圓餅等），提供對系列、座標軸、圖例的完整控制，且可與圖片與自訂圖形等其他投影片元素結合，適合自動化報表與動態簡報。

## 為何要在 Aspose Slides 圖表中添加自訂線條？

自訂線條可為圖表加上精確的視覺提示。Aspose.Slides 支援 **50+ 輸入與輸出格式**，且能在典型開發機器上使用少於 **150 MB 記憶體** 處理 **數百張投影片**，非常適合大規模報表。

## 前置條件

- **Aspose.Slides for Java** – 版本 25.4（或更新）  
- **JDK 16+** – 任一近期的 Java 執行環境  
- IDE 如 IntelliJ IDEA 或 Eclipse  
- 基本的 Java 知識與 PowerPoint 概念  

### 必要的函式庫
- Aspose.Slides for Java (Version 25.4)

### 環境設定
- 安裝 JDK 16 或更新版本  
- 使用 Maven 或 Gradle 管理相依性（以下範例）  

## 設定 Aspose.Slides for Java

將函式庫加入專案，使用以下任一建置工具。

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

如需手動下載，請前往 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 取得最新套件。

### 授權取得
- **免費試用：** 在未購買的情況下開始測試。  
- **臨時授權：** 用於延長評估且不顯示浮水印。  
- **完整授權：** 解鎖所有功能以支援生產工作負載。  

在程式碼中如範例所示初始化授權：
```java
License license = new License();
license.setLicense("path_to_license.lic");
```  

`License` 是用來載入並套用 Aspose.Slides 授權檔案的類別。

## 如何在 Aspose Slides 圖表中添加自訂線條？

載入或建立簡報，插入圖表，然後將線條形狀加入圖表的 user‑shapes 集合。線條可定位、調整大小與樣式，以符合您的報表需求。此方法同樣適用於叢集柱狀圖、條形圖、折線圖與面積圖等。

## 實作指南

### 為圖表添加自訂線條

#### 概觀
自訂線條可將注意力聚焦於特定數值（如預算上限或目標線），提升圖表的洞察力。

#### 步驟 1：建立簡報物件
`Presentation` 類別是 Aspose.Slides 的最高層物件，代表記憶體中的單一 PowerPoint 檔案。  
```java
Presentation pres = new Presentation();
```  

#### 步驟 2：新增叢集柱狀圖
在第一張投影片的座標 (100, 100) 處插入寬度 500 px、高度 400 px 的叢集柱狀圖。  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 500, 400);
```  

#### 步驟 3：向圖表添加自動圖形線條
將線條形狀加入圖表的 `userShapes` 集合，該集合儲存自訂繪圖物件。  
```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(
    ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```  

`userShapes` 是一個集合，保存直接在圖表上繪製的自訂圖形，讓您可以覆蓋線條、箭頭或其他註解。

#### 步驟 4：自訂線條屬性
將線條的填充類型設為實色，顏色改為紅色，並可選擇調整粗細或虛線樣式。  
```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```  

#### 步驟 5：儲存簡報
將修改後的簡報寫入磁碟。  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/" + "AddCustomLines.pptx", SaveFormat.Pptx);
```  

### 使用 Presentation 類別
`Presentation` 類別提供載入、建立與儲存 PowerPoint 檔案的方法，並可存取各投影片與圖形。

### 疑難排解技巧
- 確認 `save` 使用的檔案路徑可寫入；為確保可靠性，請使用絕對路徑。  
- 若圖表未顯示，請再次檢查 X/Y 座標並確保投影片索引正確。  

## 實務應用

自訂線條在以下情境特別有用：
1. **財務報告** – 突顯預算上限或盈餘目標。  
2. **銷售儀表板** – 繪製季度銷售目標線。  
3. **醫療分析** – 標示患者生命徵象趨勢中的關鍵門檻。  

您也可以透過從資料庫或 API 取得門檻值，自動化線條位置的設定，實現即時報表。

## 效能考量

- 完成後使用 `presentation.dispose()` 釋放 `Presentation` 物件，以釋放原生記憶體。  
- 使用適度的影像與圖表解析度（例如 150 dpi）以控制檔案大小。  
- 開發期間，使用臨時授權可避免評估浮水印，同時仍提供完整 API 存取。

## 結論

您現在已掌握如何在 Java 中為 **aspose slides chart** 添加自訂線條，從而完全控制圖表註解與視覺強調。請嘗試不同的線條樣式、位置與圖表類型，打造即時傳遞資料的報表。

## 常見問答

**Q1：我可以變更自訂線條的顏色嗎？**  
A1：可以，透過設定 `SolidFillColor` 屬性為任意 `java.awt.Color` 來自訂線條顏色。

**Q2：Aspose.Slides 與所有 Java IDE 相容嗎？**  
A2：是，只要您的 IDE 支援 Maven 或 Gradle，即可順利整合 Aspose.Slides。

**Q3：支援哪些圖表類型可添加自訂線條？**  
A3：自訂線條可添加於叢集柱狀圖、條形圖、折線圖、面積圖以及圓餅圖等。

**Q4：如何排除儲存簡報時的問題？**  
A4：確保輸出目錄存在、檔案路徑正確，且應用程式具備寫入權限。

**Q5：使用試用授權有什麼限制嗎？**  
A5：試用版可能會加入浮水印並限制部分高級功能；臨時或完整授權可移除這些限制。

## 資源
- **文件說明**: [Aspose.Slides Java Documentation](https://reference.aspose.com/slides/java/)  
- **下載**: [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/java/)  
- **購買**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **免費試用**: [Get a Free Trial](https://releases.aspose.com/slides/java/)  
- **取得臨時授權**: [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)  
- **支援論壇**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**最後更新:** 2026-09-07  
**測試環境:** Aspose.Slides for Java 25.4  
**作者:** Aspose

## 相關教學

- [建立自訂圖表趨勢線 Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)
- [使用 Aspose.Slides for Java 編輯 PowerPoint 圖表資料：完整指南](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [使用 Aspose.Slides for Java 旋轉圖表軸標題：逐步指南](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}