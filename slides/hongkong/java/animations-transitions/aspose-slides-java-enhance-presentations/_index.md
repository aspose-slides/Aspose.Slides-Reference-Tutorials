---
date: '2026-02-09'
description: 學習如何在 PowerPoint 中使用 Aspose.Slides for Java 為文字繪製框線並將文字加入表格儲存格。本教學涵蓋建立表格、設定文字對齊方式，以及將簡報儲存為
  pptx。
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: 使用 Aspose.Slides for Java 繪製框架並向表格添加文字
url: /zh-hant/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在使用 Aspose.Slides for Java 的簡報中繪製框架並向表格添加文字

## Introduction

在 PowerPoint 中清晰呈現資料可能是一大挑戰，尤其當你需要**向表格添加文字**並以視覺提示突顯重要數值時。本指南將教你**如何繪製框架**於特定段落、設定形狀內文字對齊，最後**將簡報另存為 pptx**——全部使用 Aspose.Slides for Java。完成後，你將擁有一套精緻的投影片，將觀眾的目光精準引導至你想要的位置。

準備好讓你的投影片脫穎而出嗎？讓我們一步一步完成整個流程。

## Quick Answers
- **「向表格添加文字」是什麼意思？** 這指的是以程式方式插入或更新單一表格儲存格的文字內容。  
- **哪個方法用於儲存檔案？** `pres.save("output.pptx", SaveFormat.Pptx)` —— 這個**將簡報另存為 pptx**的步驟會完成你的變更。  
- **如何在形狀內對齊文字？** 使用 `TextAlignment.Left`（或 Center/Right），透過 `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)` 設定。  
- **我可以在段落周圍繪製矩形嗎？** 可以——遍歷段落，取得其邊界矩形，然後加入一個無填充且線條為黑色的 `IAutoShape`。  
- **我需要授權嗎？** 臨時授權可用於評估；正式使用則需購買完整授權。  

## Why draw frames around text?

在段落或特定部分（例如，任何包含字元 **'0'** 的文字）周圍繪製框架（或矩形）可立即吸引注意。此技巧適用於：

- 在表格中突顯關鍵財務數字。  
- 在投影片中強調警告或重要說明。  
- 在不手動新增形狀的情況下建立視覺分隔。

## Prerequisites

在深入程式碼之前，請確保具備以下條件：

### Required Libraries
你需要 Aspose.Slides for Java。以下示範如何使用 Maven 或 Gradle 來加入它：

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

### Environment Setup
確保已安裝 Java Development Kit (JDK)，建議使用 JDK 16 或更新版本，因本範例使用 `jdk16` classifier。

### Knowledge Prerequisites
- 基本的 Java 程式設計概念。  
- 熟悉 PowerPoint 等簡報軟體。  
- 有使用 IntelliJ IDEA 或 Eclipse 等整合開發環境 (IDE) 的經驗。

## Setting Up Aspose.Slides for Java

要開始使用 Aspose.Slides，請依照以下步驟：

1. **安裝程式庫**：使用 Maven 或 Gradle 管理相依性，或直接從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載。

2. **License Acquisition**：
   - 先從 [Temporary License](https://purchase.aspose.com/temporary-license/) 下載臨時授權以取得免費試用。
   - 若需完整功能，請考慮於 [Purchase Aspose.Slides](https://purchase.aspose.com/buy) 購買授權。

3. **基本初始化**：使用以下程式碼片段初始化你的簡報環境：
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## How to Add Text to Table in Aspose.Slides for Java

### Feature 1: Create Table and Add Text to Cells

#### Overview
此功能示範如何**建立表格**，接著**向表格儲存格添加文字**，最後**將簡報另存為 pptx**。

#### Steps

**1. Create a Table**  
首先，初始化你的簡報，並在位置 (50, 50) 加入一個具有指定欄寬與列高的表格。
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
建立包含文字段落的 portions，並將其加入指定的儲存格。
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

### Feature 2: Add TextFrame to AutoShape and Set Alignment

#### Overview
學習如何向自動形狀 (AutoShape) 添加具有特定對齊方式的文字框——即 **set text alignment java** 的範例。

#### Steps

**1. Add an AutoShape**  
在位置 (400, 100) 加入一個矩形 AutoShape，並設定其尺寸。
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
將文字設定為 “Text in shape”，並左對齊。
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

### Feature 3: Draw Frames around Paragraphs and Portions in Table Cells

#### Overview
此功能聚焦於**在文字周圍繪製框架**，甚至對包含字元 ‘0’ 的 portions **在段落周圍繪製矩形**。

#### Steps

**1. Create a Table**  
重新使用「建立表格並向儲存格添加文字」的程式碼作為初始設定。
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
重新使用前一功能的段落建立程式碼。
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
遍歷段落與 portions，於其周圍繪製框架。
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

## Common Pitfalls & Tips

- **空值檢查** – 總是將 `Presentation` 的使用包在 try‑finally 區塊中，以確保 `pres.dispose()` 被呼叫，釋放原生資源。  
- **邊界矩形的準確性** – `para.getRect()` 回傳的矩形反映當前版面配置；若變更字型大小或邊距，請在繪製框架前重新計算矩形。  
- **效能** – 處理極大型表格時，考慮批次新增形狀，或重複使用單一 `IAutoShape` 實例並更新其幾何資訊，以降低記憶體負擔。

## Frequently Asked Questions

**Q: 我可以在較舊的 JDK 版本上使用這些 API 嗎？**  
A: 此程式庫支援 JDK 8 以上，但 `jdk16` classifier 在較新執行環境下提供最佳效能。

**Q: 如何變更框架顏色？**  
A: 修改線條格式的填色，例如 `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`。

**Q: 能否將最終投影片匯出為影像？**  
A: 可以——使用 `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`，然後儲存位元組陣列。

**Q: 若只想在儲存格內突顯「Total」一詞該怎麼做？**  
A: 遍歷 `cell.getTextFrame().getParagraphs()`，找到包含 “Total” 的 portion，並在該 portion 的邊界框周圍繪製矩形。

**Q: Aspose.Slides 能有效處理大型簡報嗎？**  
A: API 會以串流方式處理資料，並在呼叫 `pres.dispose()` 後釋放資源，有助於大型檔案的記憶體管理。

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-02-09  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}