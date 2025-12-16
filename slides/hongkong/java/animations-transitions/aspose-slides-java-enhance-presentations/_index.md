---
date: '2025-12-10'
description: 了解如何在 PowerPoint 中使用 Aspose.Slides for Java 向表格加入文字並為文字繪製框線。本指南涵蓋建立表格、設定文字對齊以及為內容加框。
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides for Java – 向表格添加文字與框架操作
url: /zh-hant/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 精通在簡報中使用 Aspose.Slides for Java 進行表格與框線操作

## 簡介

在 PowerPoint 中有效呈現資料可能相當具挑戰性。無論您是軟體開發人員或簡報設計師，**add text to table** 儲存格並在關鍵段落周圍繪製框線，都能讓投影片更具吸引力。在本教學中，您將會看到如何使用 Aspose.Slides for Java 來 **add text to table**、對齊文字，以及在文字周圍繪製框線——最終能製作出在適當時機突顯正確資訊的精緻簡報。

準備好改造您的簡報了嗎？讓我們開始吧！

## 快速解答
- **「add text to table」是什麼意思？** 它指的是以程式方式插入或更新單一表格儲存格的文字內容。  
- **哪個方法用於儲存檔案？** `pres.save("output.pptx", SaveFormat.Pptx)` —— 此 **save presentation as pptx** 步驟會完成您的變更。  
- **如何對齊圖形內的文字？** 使用 `TextAlignment.Left`（或 Center / Right），透過 `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`。  
- **我可以在段落周圍畫矩形嗎？** 可以——遍歷段落，取得其邊界矩形，然後加入一個無填色且線條為黑色的 `IAutoShape`。  
- **我需要授權嗎？** 臨時授權可用於評估；正式使用則需購買完整授權。

## 先決條件

在深入程式碼之前，請確保您具備以下條件：

### 必要的函式庫
您需要 Aspose.Slides for Java。以下說明如何使用 Maven 或 Gradle 來加入它：

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
請確保已安裝 Java Development Kit（JDK），建議使用 JDK 16 或更新版本，因為本範例使用 `jdk16` classifier。

### 知識先備
- 具備 Java 程式設計的基本概念。  
- 熟悉 PowerPoint 等簡報軟體。  
- 有使用 IntelliJ IDEA 或 Eclipse 等整合開發環境（IDE）的經驗。

## 設定 Aspose.Slides for Java

要開始使用 Aspose.Slides，請依照以下步驟：

1. **安裝函式庫**：使用 Maven 或 Gradle 管理相依性，或直接從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下載。  
2. **取得授權**：  
   - 先透過下載臨時授權的方式取得免費試用，網址為 [Temporary License](https://purchase.aspose.com/temporary-license/)。  
   - 若需完整功能，請於 [Purchase Aspose.Slides](https://purchase.aspose.com/buy) 購買授權。  
3. **基本初始化**：使用以下程式碼片段來初始化簡報環境：  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## 為何要 add text to table 並繪製框線？

在表格中 add text to table 能夠清晰呈現結構化資料，而在段落或特定文字片段（例如包含 **'0'** 的部分）繪製框線，則能吸引觀眾注意重要數值。此組合非常適合財務報告、儀表板，或任何需要在不雜亂的情況下突顯關鍵數字的投影片。

## 如何在 Aspose.Slides for Java 中 add text to table

### 功能 1：建立表格並在儲存格中 Add Text to Cells

#### 概觀
此功能示範如何 **how to create table**，接著 **add text to table** 儲存格，最後 **save presentation as pptx**。

#### 步驟

**1. 建立表格**  
首先，初始化您的簡報，並在位置 (50, 50) 加入一個具有指定欄寬與列高的表格。  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
建立包含文字片段的段落，並將其加入特定儲存格。  
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

**3. 儲存簡報**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### 功能 2：將 TextFrame 加入 AutoShape 並設定對齊方式

#### 概觀
學習如何將具有特定對齊方式的文字框加入自動圖形——即 **set text alignment java** 的範例。

#### 步驟

**1. 加入 AutoShape**  
在位置 (400, 100) 加入一個矩形 AutoShape，並設定指定尺寸。  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. 設定文字對齊**  
將文字設為 “Text in shape”，並左對齊。  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. 儲存簡報**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### 功能 3：在表格儲存格的段落與文字片段周圍繪製框線

#### 概觀
此功能著重於 **draw frames around text**，甚至對包含字元 ‘0’ 的文字片段 **draw rectangle around paragraph**。

#### 步驟

**1. 建立表格**  
重新使用「Create Table and Add Text to Cells」的程式碼作為初始設定。  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. 加入段落**  
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

**3. 繪製框線**  
遍歷段落與文字片段，為其繪製框線。  
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

**4. 儲存簡報**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## 結論
透過本指南，您可以 **add text to table**、在圖形內對齊文字，並 **draw frames around text** 以強調重要資訊。精通這些技巧後，您即可使用 Aspose.Slides for Java 製作高度精緻、以資料為導向的簡報。欲進一步探索，可嘗試將這些功能與圖表、動畫或匯出為 PDF 結合使用。

## 常見問題

**Q: 我可以在較舊的 JDK 版本上使用這些 API 嗎？**  
A: 此函式庫支援 JDK 8 以上，但 `jdk16` classifier 在較新執行環境下提供最佳效能。

**Q: 我要如何變更框線顏色？**  
A: 調整線條格式的填色，例如 `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`。

**Q: 能否將最終投影片匯出為影像？**  
A: 可以——使用 `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`，然後儲存其位元組陣列。

**Q: 若只需要在儲存格內突顯「Total」這個字該怎麼做？**  
A: 遍歷 `cell.getTextFrame().getParagraphs()`，找到包含 “Total” 的文字片段，並在該片段的邊界框上繪製矩形。

**Q: Aspose.Slides 能有效處理大型簡報嗎？**  
A: 此 API 會串流資料，並在呼叫 `pres.dispose()` 後釋放資源，有助於大型檔案的記憶體管理。

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}