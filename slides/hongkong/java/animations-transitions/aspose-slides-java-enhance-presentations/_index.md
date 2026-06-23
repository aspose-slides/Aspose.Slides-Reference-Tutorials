---
date: '2026-06-23'
description: 了解如何在 PowerPoint 中建立表格、向表格儲存格加入文字、在文字周圍繪製框線，並使用 Aspose.Slides for Java
  將簡報儲存為 pptx。
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
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
title: 如何在 PowerPoint 中建立表格並使用 Aspose.Slides for Java 繪製框線
url: /zh-hant/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 PowerPoint 中建立表格並使用 Aspose.Slides for Java 繪製框線

## 介紹

以程式方式建立 **create table in PowerPoint** 可以為您節省大量手動格式設定的時間，特別是當您需要突顯關鍵數字或加入說明文字時。在本教學中，您將學會如何向表格儲存格加入文字、在特定段落周圍繪製框線、設定精確的文字對齊方式，最後 **save presentation as pptx** —— 全部透過功能強大的 Aspose.Slides for Java API 完成。完成後，您將擁有一張外觀精緻、易於閱讀，且能立即吸引觀眾注意最重要資料的投影片。

## 快速解答
- **What does “add text to table” mean?** 它指的是以程式方式插入或更新個別表格儲存格的文字內容。  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – 此 **save presentation as pptx** 步驟會完成您的變更。  
- **How can I align text inside a shape?** 使用 `TextAlignment.Left`（或 Center/Right）透過 `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`。  
- **Can I draw a rectangle around a paragraph?** 可以 – 迭代段落，取得其邊界矩形，並加入一個沒有填充且線條為黑色的 `IAutoShape`。  
- **Do I need a license?** 臨時授權可用於評估；正式使用則需要完整授權。  

## 為什麼要在文字周圍繪製框線？

在段落或特定文字區段（例如任何包含字元 **'0'** 的文字）周圍繪製框線（或矩形），能立即將觀眾的注意力聚焦於該內容。這提供了清晰的視覺提示，且不會改變底層文字，非常適合用來突顯關鍵數字、警示訊息，或在投影片中分隔不同區塊。

## 前置條件

在開始撰寫程式碼之前，請確保您具備以下條件：

### 必要的函式庫
您需要 Aspose.Slides for Java。以下示範如何使用 Maven 或 Gradle 來加入：

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

### 環境設定
請確保已安裝 Java Development Kit (JDK)，建議使用 JDK 16 以上，因為本範例使用 `jdk16` classifier。

### 知識前提
- 基本的 Java 程式設計知識。  
- 熟悉 PowerPoint 等簡報軟體。  
- 具備使用 IntelliJ IDEA 或 Eclipse 等整合開發環境 (IDE) 的經驗。

## 設定 Aspose.Slides for Java

`Presentation` 是 Aspose.Slides 的核心類別，代表記憶體中的 PowerPoint 檔案，並提供對投影片、形狀與表格的存取。開始使用 Aspose.Slides，請依照以下步驟：

1. **Install the Library**: 使用 Maven 或 Gradle 管理相依性，或直接從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載。  
2. **License Acquisition**:  
   - 先從 [Temporary License](https://purchase.aspose.com/temporary-license/) 下載臨時授權以進行試用。  
   - 若需完整功能，請於 [Purchase Aspose.Slides](https://purchase.aspose.com/buy) 購買正式授權。  
3. **Basic Initialization**:  
   使用以下程式碼片段初始化簡報環境：  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## 如何在 Aspose.Slides for Java 中向表格添加文字？

載入新的 `Presentation`，在指定座標建立表格，使用 `TextFrame` 物件填入儲存格文字，最後呼叫 `pres.save("output.pptx", SaveFormat.Pptx)`。此流程同時完成 **create table in PowerPoint**、向每個儲存格注入自訂文字，並將結果寫入 PPTX 檔案。

### 功能 1：建立表格並向儲存格添加文字

#### 概述
本功能示範如何 **create table**，接著 **add text to table** 儲存格，最後 **save presentation as pptx**。

#### 步驟

**1. Create a Table**  
先初始化簡報，並在座標 (50, 50) 位置建立表格，設定欄寬與列高。  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Text to Cells**  
建立段落與文字區段，並將它們加入指定儲存格。  
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

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### 功能 2：向 AutoShape 添加 TextFrame 並設定對齊方式

#### 概述
學習如何向 AutoShape 加入文字框並設定特定對齊方式——這是 **set text alignment java** 的範例。

#### 步驟

AutoShape 是一種可容納文字與圖形的形狀。

**1. Add an AutoShape**  
在座標 (400, 100) 位置加入一個矩形 AutoShape，並設定尺寸。  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` 列舉定義了形狀內文字的水平對齊選項。

**2. Set Text Alignment**  
設定文字為「Text in shape」並左對齊。  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### 功能 3：在表格儲存格的段落與文字區段周圍繪製框線

#### 概述
本功能聚焦於 **draw frames around text**，甚至 **draw rectangle around paragraph**，針對包含字元 ‘0’ 的區段繪製框線。

#### 步驟

`IAutoShape` 代表可在投影片上繪製的形狀物件，例如用作框線的矩形。

**1. Create a Table**  
重複「建立表格並向儲存格添加文字」的程式碼以完成初始設定。  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Paragraphs**  
重複前一功能中的段落建立程式碼。  
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

**3. Draw Frames**  
迭代段落與文字區段，為它們繪製框線。  
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

**4. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## 常見陷阱與技巧

- **Null checks** – 總是將 `Presentation` 的使用包在 try‑finally 區塊中，以確保 `pres.dispose()` 被呼叫並釋放本機資源。  
- **Bounding rectangle accuracy** – `para.getRect()` 回傳的矩形反映當前版面配置；若變更字型大小或邊距，請在繪製框線前重新計算矩形。  
- **Performance** – 處理非常大的表格時，考慮批次新增形狀或重複使用單一 `IAutoShape` 實例並更新其幾何形狀，以降低記憶體負擔。  

## 常見問答

**Q: Can I use these APIs with older JDK versions?**  
A: 此函式庫支援 JDK 8 以上，但 `jdk16` classifier 在較新執行環境下可提供最佳效能。

**Q: How do I change the frame color?**  
A: 修改線條格式的填色，例如 `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`。

**Q: Is it possible to export the final slide as an image?**  
A: 可以——使用 `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` 取得位元組陣列後再儲存。

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: 迭代 `cell.getTextFrame().getParagraphs()`，找到包含 “Total” 的文字區段，然後在該區段的邊界矩形上繪製矩形框線。

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: API 會以串流方式處理資料，並在呼叫 `pres.dispose()` 後釋放資源，有助於大型檔案的記憶體管理。

**最後更新：** 2026-06-23  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [Aspose.Slides for Java：掌握 PPTX 表格與文字操作於 PowerPoint 簡報](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [如何使用 Aspose.Slides for Java 在 PowerPoint 中建立動態文字框](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [使用 Aspose.Slides for Java 在文字框中新增欄位](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}