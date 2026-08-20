---
date: '2026-08-06'
description: 了解如何使用 Aspose.Slides for Java 變更圖例字體顏色並修改圖表圖例文字。遵循一步一步的說明，快速自訂圖表圖例。
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: 了解如何使用 Aspose.Slides for Java 變更圖例字體顏色並修改圖表圖例文字。本指南會示範確切步驟與最佳實踐。
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: 如何在 Aspose.Slides for Java 中變更圖例字體顏色
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: 如何在 Aspose.Slides for Java 中變更圖例字體顏色
url: /zh-hant/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Aspose.Slides for Java 中更改圖例字體顏色

## 簡介
如果您需要在圖表中 **更改圖例字體顏色**，Aspose.Slides for Java 為您提供對每個圖例項目的完整控制。本教學將帶您逐步自訂圖例文字樣式、套用粗體或斜體字體，並設定實色，使您的圖表呈現出您想要的外觀。完成本指南後，您將能自信地修改圖表圖例文字，並將變更整合至任何現有簡報中。

**您將學習**
- 如何以程式方式 **更改圖例字體顏色**。
- 如何 **修改圖表圖例文字**，例如粗體、斜體與字體大小。
- 在同一簡報的多個圖表上套用變更的技巧。
- 如何將這些步驟整合至更大的自動化工作流程。

## 快速解答
- **我可以更改單一圖例項目的顏色嗎？** 是 – 透過其索引存取該項目，並將填充格式設定為實色。  
- **使用這些 API 需要授權嗎？** 需要臨時或付費授權才能在正式環境使用；免費試用可用於評估。  
- **支援哪個 Java 版本？** Aspose.Slides for Java 25.4+ 可在 JDK 16 及以上版本執行。  
- **變更會影響其他圖表元素嗎？** 不會，圖例格式與資料系列樣式是獨立的。  
- **可以批次處理嗎？** 當然可以 – 迴圈遍歷投影片與圖表，即可在整個簡報套用相同的圖例設定。

## 什麼是更改圖例字體顏色？
`change legend font color` 指的是使用 Aspose.Slides API 程式化設定圖表圖例項目文字顏色的操作。此操作會更新圖例的視覺外觀，而不會改變底層資料。

## 為什麼要自訂圖表圖例？
Aspose.Slides 支援 **50+ 輸入與輸出格式**，且可處理 **500+ 投影片** 的簡報，同時將記憶體使用量控制在 200 MB 以下。自訂圖例可提升可讀性、呼應品牌色彩，並確保關鍵資料點突出——在商業或教育簡報中，視覺清晰度直接影響決策。

## 先決條件
- **Aspose.Slides for Java** 函式庫（版本 25.4 或更新）。  
- Java Development Kit (JDK) 16 或以上。  
- IntelliJ IDEA、Eclipse 或 NetBeans 等 IDE。  
- Maven 或 Gradle 進行相依管理。  
- 基本的 Java 程式設計知識。

## 設定 Aspose.Slides for Java
要開始自訂圖表圖例，請使用以下任一方式將函式庫加入專案。

### Maven
在您的 `pom.xml` 檔案中加入以下相依性：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
在您的 `build.gradle` 檔案中加入此行：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
您也可以從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 取得最新的 JAR。

#### 取得授權步驟
- **免費試用：** 先使用免費試用版探索 Aspose.Slides 功能。  
- **臨時授權：** 申請臨時授權以延長評估時間。  
- **購買：** 若需完整功能，請從 [Aspose Purchase](https://purchase.aspose.com/buy) 購買授權。

#### 基本初始化與設定
將函式庫加入專案後：
1. 在 Java 應用程式中初始化 Aspose.Slides。  
2. 載入現有簡報或建立新簡報。

## 如何更改圖例字體顏色？
要更改圖例字體顏色，請載入簡報、取得圖表物件、取得其圖例，然後透過將填充類型設為實色並指定所需顏色，修改每個圖例項目的文字格式。此單一步驟即可即時更新圖例文字顏色，無需重新繪製整張投影片。例如：`legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` 此方法適用於任何圖表類型，且不需重新渲染整張投影片。

### 存取與修改圖例文字屬性

#### 定義錨點
`IChart` 介面代表投影片上的圖表物件，其 `getLegend()` 方法會回傳一個 `ILegend` 物件，該物件包含一系列 `ILegendEntry` 項目。

#### 將圖表加入簡報
1. **載入簡報：**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **新增叢集柱狀圖：**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### 自訂字體屬性
3. **存取圖例項目文字格式：**  
   此處的 `legendEntry` 為代表圖表圖例中單一項目的 `ILegendEntry` 物件。  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **設定粗體與斜體樣式並指定高度：**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **將填充類型改為實色以提升可見度：**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### 儲存簡報
6. **儲存變更：**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### 常見陷阱與疑難排解
- 確認圖例項目索引與圖表系列順序相符。  
- 確保使用的函式庫版本支援 `setSolidFillColor`（自 20.9 版起提供）。

## 實務應用
自訂圖例文字在許多真實情境中都很有用：

1. **商業簡報：** 讓圖例顏色與企業品牌色彩保持一致，提升專業感。  
2. **教育教材：** 以對比色突顯關鍵資料系列，幫助學習者快速抓住重點。  
3. **行銷簡報：** 使用粗體、彩色圖例強調績效指標，吸引利害關係人注意。  

您亦可透過從資料庫或設定檔讀取顏色值，自動化圖例更新。

## 效能考量
處理大型簡報時，請留意以下建議：

- **有效的記憶體管理：** 儲存後呼叫 `presentation.dispose()` 釋放本機資源。  
- **僅載入必要投影片：** 若只需部份投影片，可使用 `Presentation.load(String path, LoadOptions options)` 並搭配 `LoadOptions.setLoadOnlySlideIds()`。  
- **批次處理：** 將圖例更新按投影片分組，以減少 API 呼叫次數並提升吞吐量。

## 結論
您現在已掌握如何使用 Aspose.Slides for Java **更改圖例字體顏色** 以及 **修改圖表圖例文字**。這些自訂可提升視覺清晰度，協助您更有效地傳達資料。請嘗試不同的字體、大小與顏色，以符合簡報的風格指南，並探索其他圖表樣式功能，打造真正專業的簡報。

**下一步**
- 嘗試將相同的圖例樣式套用至圓餅圖與折線圖。  
- 結合圖例自訂與資料標籤格式設定，實現完整品牌化的圖表。  

準備好提升您的簡報了嗎？依照上述步驟執行，即可立刻看到差異！

## 常見問答
1. **如何更改圖例項目文字的顏色？**  
   在圖例項目的文字格式上使用 `getFillFormat().setFillType(FillType.Solid)`，然後呼叫 `setSolidFillColor(Color.YOUR_COLOR)`。

2. **我可以將這些變更套用到簡報中的所有圖例嗎？**  
   可以 – 迴圈遍歷每張投影片，定位每個圖表，並在迴圈內更新其圖例項目。

3. **能否根據文字長度動態調整字體大小？**  
   您可以使用 `TextFrame.getTextFrameFormat().getFontHeight()` 計算所需大小，然後透過 `setFontHeight(double)` 設定。

4. **如果遇到圖例項目索引問題該怎麼辦？**  
   請再次確認您使用的索引與系列順序相符；索引是從零開始計算的。

5. **在哪裡可以找到更多 Aspose.Slides 範例？**  
   探索 [Aspose Documentation](https://reference.aspose.com/slides/java/) 以取得完整指南與 API 參考。

**其他問答**

**Q: 更改圖例字體顏色會影響匯出的 PDF 檔案嗎？**  
A: 不會，顏色變更會在 Aspose.Slides 支援的所有匯出格式（包括 PDF 與 PPTX）中保留。

**Q: 我可以使用漸層而非實色嗎？**  
A: 可以 – 設定 `FillType.Gradient`，並透過 `getGradientStyle()` 配置漸層停點。

**Q: 圖表最多可以有多少個圖例項目？**  
A: 圖表最多可容納 256 個圖例項目，僅受您加入的資料系列數量限制。

## 資源
- **文件說明：** 使用 Aspose.Slides 功能的完整指南（[連結](https://reference.aspose.com/slides/java/)）。  
- **下載：** 取得最新版本的 Aspose.Slides for Java（[連結](https://releases.aspose.com/slides/java/)）。  
- **購買：** 購買授權以解鎖全部功能（[連結](https://purchase.aspose.com/buy)）。  
- **免費試用與臨時授權：** 先使用免費試用版，或申請臨時授權（[免費試用連結](https://releases.aspose.com/slides/java/)、[臨時授權連結](https://purchase.aspose.com/temporary-license/)）。  
- **支援：** 在 Aspose 社群論壇取得協助（[連結](https://forum.aspose.com/c/slides/11)）。

---

**最後更新：** 2026-08-06  
**測試於：** Aspose.Slides for Java 25.4  
**作者：** Aspose

## 相關教學

- [Enhancing PowerPoint Charts: Font & Axis Customization with Aspose.Slides for Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides for Java: Dynamic Text Frames & Font Customization Guide](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}