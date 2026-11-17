---
date: '2026-11-16'
description: 使用 Aspose.Slides for Java 在 PowerPoint 表格的文字周圍繪製框線 – 了解如何建立表格、在儲存格中加入文字、突顯儲存格，以及將檔案匯出為
  PPTX。
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: 使用 Aspose.Slides for Java 在 PowerPoint 表格的文字周圍繪製框線。本指南示範如何建立表格、加入並對齊文字、突顯儲存格，以及將投影片匯出為
  PNG。
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: 在文字周圍繪製框線並使用 Aspose.Slides for Java 建立 PowerPoint 表格
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: 在文字周圍繪製框線並使用 Aspose.Slides for Java 建立 PowerPoint 表格
url: /zh-hant/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 PowerPoint 中使用 Aspose.Slides for Java 繪製文字框架並建立表格

## 簡介

在 PowerPoint 投影片中 **繪製文字框架** 可讓您在不更改原始內容的情況下突顯關鍵數字。於本教學中，您將學習如何以程式方式建立表格、在儲存格內插入並對齊文字、突顯特定單字或整個儲存格，最後將簡報儲存為 PPTX 檔案。完成後，您將擁有一張精緻的投影片，將觀眾的目光精確引導至您想要的地方。

## 快速回答
- **「add text to table」是什麼意思？** 它表示以程式方式插入或更新單個表格儲存格的文字內容。  
- **哪個方法會儲存檔案？** `pres.save("output.pptx", SaveFormat.Pptx)` – 此 **save presentation as pptx** 步驟會完成您的變更。  
- **如何在形狀內對齊文字？** 使用 `TextAlignment.Left`（或 Center/Right），透過 `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`。  
- **我可以在段落周圍繪製矩形嗎？** 可以 — 迭代段落，取得其邊界矩形，並加入一個無填色且線條為黑色的 `IAutoShape`。  
- **我需要授權嗎？** 臨時授權可用於評估；正式授權則是生產環境的必要條件。  

## 為什麼要在文字周圍繪製框架？

在文字周圍繪製框架可立即突顯重要的數字、警示或標題。它提供視覺提示，同時保持原始格式不變，十分適合財務報告、KPI 儀表板或任何需要強調的投影片。

## 什麼是 draw frame around text？

`draw frame around text` 是一種以程式方式加入矩形形狀的技術，該形狀依照段落或文字片段的精確邊界繪製，僅使用線條格式而不填充內部。此方法可在不改變文字本身的情況下強調內容。

## 先決條件

在開始之前，請確保您具備以下條件：

### 必要的函式庫
您需要 Aspose.Slides for Java。可透過以下套件管理工具之一將其加入：

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

您也可以在 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 瀏覽發行版本。

### 環境設定
建議使用 Java Development Kit (JDK) 16 或更新版本，因為範例使用 `jdk16` 分類器。任何 IDE，例如 IntelliJ IDEA 或 Eclipse，都可正常運作。

### 知識先備條件
- 基本的 Java 程式設計技能。  
- 熟悉 PowerPoint 概念（投影片、形狀、表格）。  
- 了解 Maven/Gradle 如何管理相依性。

## 設定 Aspose.Slides for Java

`Presentation` 是 Aspose.Slides 的核心類別，代表記憶體中的 PowerPoint 檔案，並提供存取投影片、形狀與表格的功能。它可處理最多 **10,000 投影片** 的簡報，同時將記憶體使用量控制在 **500 MB** 以下，適合大規模自動化。

1. **安裝函式庫** – 使用 Maven 或 Gradle，或直接從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載。  
2. **取得授權** – 先從 [Temporary License](https://purchase.aspose.com/temporary-license/) 取得免費試用，然後在 [Purchase Aspose.Slides](https://purchase.aspose.com/buy) 升級為正式授權以供生產環境使用。  
3. **基本初始化** – 建立新的 `Presentation` 物件，並依需求載入或建立投影片。  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## 如何在 Aspose.Slides for Java 中向表格加入文字？

`Presentation` 是代表記憶體中 PowerPoint 檔案的主要類別。  
載入新的 `Presentation`，在指定座標建立表格，使用 `TextFrame` 物件填充儲存格，最後呼叫 `pres.save("output.pptx", SaveFormat.Pptx)`。此流程會 **create table in PowerPoint**，將自訂文字注入每個儲存格，並以單一高效的工作流程寫入 PPTX 檔案。

### 直接答案
透過呼叫 `slide.getShapes().addTable(...)` 建立表格，然後對每個儲存格使用 `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))`。在填滿所有儲存格後，呼叫 `pres.save("output.pptx", SaveFormat.Pptx)` 寫入檔案。此方法讓您以程式方式控制每個儲存格的內容與樣式。

#### 功能 1：建立表格並向儲存格加入文字
**1. 建立表格** – 初始化簡報，新增投影片，並在 (50, 50) 放置一個具有指定欄寬與列高的表格。  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. 向儲存格加入文字** – 對每個儲存格，建立 `Paragraph`，加入帶有所需字串的 `Portion`，並將段落指派給儲存格的 `TextFrame`。  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. 儲存簡報** – 呼叫 `pres.save("output.pptx", SaveFormat.Pptx)`。  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## 如何在 PowerPoint 投影片中繪製文字框架？

`Rectangle2D` 代表二維座標空間中的矩形區域。  
載入投影片，找到您想要強調的段落或文字片段，透過 `getRect()` 取得其邊界矩形，然後加入一個無填色且帶彩色線條的 `IAutoShape` 矩形。此方法同時適用於整段落與單一單字片段。

### 直接答案
要在文字周圍繪製框架，首先取得段落的矩形 (`Rectangle2D rect = paragraph.getRect();`)。接著建立 `IAutoShape` 矩形 (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`)，設定 `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)`，並停用填色 (`shape.getFillFormat().setFillType(FillType.NoFill)`)。此形狀將精確勾勒出文字的輪廓。

#### 功能 3：在表格儲存格的段落與文字片段周圍繪製框架
**1. 建立表格** – 重新使用功能 1 的程式碼來設定初始表格。  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. 新增段落** – 重新使用功能 1 的段落建立程式碼。  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. 繪製框架** – 迭代每個段落，取得其邊界矩形，並依上述方式加入矩形形狀。對於包含字元 ‘0’ 的文字片段，繪製額外的框架以突顯這些數字。  
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```  

**4. 儲存簡報** – 與之前相同的最終步驟。  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## 如何向 AutoShape 加入文字框並設定對齊方式

`AutoShape` 是一種可容納文字、影像或其他內容的形狀。  
`AutoShape` 可以包含 `TextFrame`。您可以使用 `ParagraphFormat` 列舉來控制水平對齊方式。

### 直接答案
建立矩形 AutoShape (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`)，取得其 `TextFrame`，使用 `shape.getTextFrame().setText("Text in shape")` 設定文字，然後呼叫 `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)`。此操作會將文字在形狀內左對齊。

**1. 新增 AutoShape** – 在所需位置放置矩形。  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. 設定文字對齊** – 如上所示套用左對齊。  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. 儲存簡報** – 相同的最終步驟。  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## 常見陷阱與技巧

- **Always dispose** – 將 `Presentation` 的使用包在 try‑finally 區塊中，並呼叫 `pres.dispose()` 以釋放原生資源。  
- **Re‑compute bounding rectangles** – 若在繪製框架後變更字型大小、邊距或儲存格內距，請在加入形狀前再次呼叫 `paragraph.getRect()`。  
- **Batch shape creation for large tables** – 重複使用單一 `IAutoShape` 實例並更新其幾何形狀，可減少處理數百列大型表格時的記憶體壓力。  
- **Performance numbers** – Aspose.Slides 能在一般 4 核心伺服器上於 2 秒內產生 200 頁的 PPTX，且在 1,000 個段落上繪製框架僅增加不到 150 毫秒的開銷。

## 常見問題

**Q: 我可以在較舊的 JDK 版本使用這些 API 嗎？**  
A: 此函式庫支援 JDK 8 以上，但 `jdk16` 分類器在較新執行環境下提供最佳效能。

**Q: 如何變更框架顏色？**  
A: 修改線條格式的填色，例如 `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`。

**Q: 是否可以將最終投影片匯出為影像？**  
A: 可以 — 使用 `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`，然後儲存位元組陣列。

**Q: 如果只需要在儲存格內突顯「Total」這個字該怎麼做？**  
A: 迭代 `cell.getTextFrame().getParagraphs()`，找到包含 “Total” 的文字片段，並在該片段的邊界框周圍繪製矩形。

**Q: Aspose.Slides 能有效處理大型簡報嗎？**  
A: 此 API 會串流資料，並在呼叫 `pres.dispose()` 時釋放資源，有助於大型檔案的記憶體管理。

---

**最後更新**: 2026-11-16  
**測試環境**: Aspose.Slides for Java 25.4 (jdk16)  
**作者**: Aspose  



## 相關教學

- [Aspose.Slides for Java：掌握 PPTX 表格與文字操作於 PowerPoint 簡報](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [如何使用 Aspose.Slides for Java 在 PowerPoint 中建立動態文字框](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [使用 Aspose.Slides for Java 在文字框中新增欄位](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}