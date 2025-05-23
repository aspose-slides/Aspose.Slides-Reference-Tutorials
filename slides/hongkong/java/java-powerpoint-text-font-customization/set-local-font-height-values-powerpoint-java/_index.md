---
"description": "了解如何使用 Java 和 Aspose.Slides 調整 PowerPoint 簡報中的字體高度。輕鬆增強投影片中的文字格式。"
"linktitle": "使用 Java 在 PowerPoint 中設定本機字體高度值"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "使用 Java 在 PowerPoint 中設定本機字體高度值"
"url": "/zh-hant/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 PowerPoint 中設定本機字體高度值

## 介紹
在本教學中，您將學習如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中操縱不同層級的字體高度。控製字體大小對於創建具有視覺吸引力和結構化的簡報至關重要。我們將透過逐步的範例來說明如何為不同的文字元素設定字體高度。
## 先決條件
在開始之前，請確保您已準備好以下內容：
- 系統上安裝了 Java 開發工具包 (JDK)
- Aspose.Slides for Java 函式庫。你可以下載它 [這裡](https://releases。aspose.com/slides/java/).
- 對 Java 程式設計和 PowerPoint 簡報有基本的了解
## 導入包
確保在 Java 檔案中包含必要的 Aspose.Slides 套件：
```java
import com.aspose.slides.*;
```
## 步驟 1：初始化演示對象
首先，建立一個新的 PowerPoint 簡報物件：
```java
Presentation pres = new Presentation();
```
## 步驟 2：新增形狀和文字框
在第一張投影片中新增帶有文字方塊的自動形狀：
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## 步驟 3：建立文字部分
定義具有不同字體高度的文字部分：
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## 步驟4：設定字體高度
設定不同等級的字體高度：
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## 步驟 5：儲存簡報
將修改後的簡報儲存到文件：
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## 結論
本教學課程示範如何使用 Aspose.Slides for Java 以程式設計方式調整 PowerPoint 投影片中的字體高度。透過在不同層級（簡報範圍、段落和部分）操縱字體大小，您可以精確控制簡報中的文字格式。
## 常見問題解答
### 什麼是 Aspose.Slides for Java？
Aspose.Slides for Java 是一個功能強大的 API，用於以程式設計方式操作 PowerPoint 簡報。
### 在哪裡可以找到 Aspose.Slides for Java 的文檔？
您可以找到文檔 [這裡](https://reference。aspose.com/slides/java/).
### 我可以在購買之前試用 Aspose.Slides for Java 嗎？
是的，您可以免費試用 [這裡](https://releases。aspose.com/).
### 如何獲得 Aspose.Slides for Java 的支援？
如需支持，請訪問 [Aspose.Slides論壇](https://forum。aspose.com/c/slides/11).
### 我可以在哪裡購買 Aspose.Slides for Java 的授權？
您可以購買許可證 [這裡](https://purchase。aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}