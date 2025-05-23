---
"date": "2025-04-18"
"description": "了解如何透過掌握使用 Aspose.Slides for Java 的表格和框架操作來增強您的簡報。本指南涵蓋建立表格、新增文字方塊以及圍繞特定內容繪製框架。"
"title": "Aspose.Slides for Java&#58;掌握簡報中的表格和框架操作"
"url": "/zh-hant/java/animations-transitions/aspose-slides-java-enhance-presentations/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 掌握簡報中的表格和框架操作

## 介紹

在 PowerPoint 中有效地呈現資料可能具有挑戰性。無論您是軟體開發人員還是簡報設計師，使用視覺上吸引人的表格並添加文字方塊都可以使您的投影片更具吸引力。本教學探討如何使用 Aspose.Slides for Java 為表格單元格新增文字並在段落和包含特定字元（如「0」）的部分周圍繪製框架。透過掌握這些技巧，您將能夠提高演示的準確性和風格。

### 您將學到什麼：
- 在幻燈片中建立表格並用文字填充。
- 在自動形狀內對齊文字以獲得更好的呈現效果。
- 在段落和部分周圍繪製框架以強調內容。
- 這些功能在現實場景中的實際應用。

準備好改變您的簡報了嗎？讓我們開始吧！

## 先決條件

在深入研究程式碼之前，請確保您已具備以下條件：

### 所需庫
您需要適用於 Java 的 Aspose.Slides。以下是使用 Maven 或 Gradle 將其包含進去的方法：

**Maven：**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle：**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 環境設定
確保已安裝 Java 開發工具包 (JDK)，最好是 JDK 16 或更高版本，因為本範例使用 `jdk16` 分類器。

### 知識前提
- 對 Java 程式設計有基本的了解。
- 熟悉 PowerPoint 等簡報軟體。
- 具有使用整合開發環境 (IDE)（例如 IntelliJ IDEA 或 Eclipse）的經驗。

## 設定 Aspose.Slides for Java

若要開始使用 Aspose.Slides，請依照下列步驟操作：

1. **安裝庫**：使用 Maven 或 Gradle 管理依賴項，或直接從 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

2. **許可證獲取**：
   - 下載臨時許可證即可開始免費試用 [臨時執照](https://purchase。aspose.com/temporary-license/).
   - 如需完全存取權限，請考慮購買許可證 [購買 Aspose.Slides](https://purchase。aspose.com/buy).

3. **基本初始化**：
使用以下程式碼片段初始化您的演示環境：
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // 您的程式碼在這裡
} finally {
    if (pres != null) pres.dispose();
}
```

## 實施指南

本節介紹可以使用 Aspose.Slides for Java 實作的不同功能。

### 功能 1：建立表格並為單元格新增文本

#### 概述
此功能示範如何在第一張投影片上建立表格並用文字填入特定儲存格。 

##### 步驟：
**1.創建表**
首先，初始化您的簡報並在位置 (50, 50) 中新增一個具有指定列寬和行高的表格。
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2. 在單元格中加入文本**
建立包含部分文字的段落並將其新增至特定儲存格。
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
**3.儲存簡報**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### 功能 2：為自選圖形新增文字方塊並設定對齊方式

#### 概述
了解如何為自動形狀新增具有特定對齊方式的文字方塊。

##### 步驟：
**1. 新增自選圖形**
在位置 (400, 100) 處新增一個具有指定尺寸的矩形作為自選圖形。
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```
**2.設定文字對齊方式**
將文字設為“形狀中的文字”並將其左對齊。
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
**3.儲存簡報**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### 功能 3：在表格單元格中的段落和部分周圍繪製框架

#### 概述
此功能主要在表格單元格內的段落和包含“0”的部分周圍繪製框架。

##### 步驟：
**1.創建表**
重複使用「建立表格並向儲存格新增文字」中的程式碼進行初始設定。
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2.新增段落**
重複使用上一個功能中的段落建立程式碼。
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
**3. 繪製框架**
遍歷段落和部分以在它們周圍繪製框架。
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
**4.儲存簡報**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## 結論
透過遵循本指南，您可以使用 Aspose.Slides for Java 有效地增強您的簡報。掌握表格和框架操作可以讓您創建更具吸引力和視覺吸引力的幻燈片。為了進一步探索，請考慮深入了解 Aspose.Slides 的其他功能或將其與其他 Java 應用程式整合。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}