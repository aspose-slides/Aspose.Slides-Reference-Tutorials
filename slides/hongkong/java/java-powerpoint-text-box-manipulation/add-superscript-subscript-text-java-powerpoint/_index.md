---
title: 在 Java PowerPoint 中新增上標和下標文本
linktitle: 在 Java PowerPoint 中新增上標和下標文本
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 Java PowerPoint 簡報中新增上標和下標文字。非常適合增強幻燈片效果。
weight: 13
url: /zh-hant/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介紹
創建引人入勝且內容豐富的 PowerPoint 簡報通常需要使用上標和下標文字等格式設定功能。本教學將引導您完成使用 Aspose.Slides for Java 將上標和下標文字合併到 Java PowerPoint 簡報中的過程。
## 先決條件
在開始之前，請確保您具備以下條件：
- 您的系統上安裝了 Java 開發工具包 (JDK)。
-  Java 函式庫的 Aspose.Slides。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/java/).
- 為 Java 開發設定的整合開發環境 (IDE)，例如 IntelliJ IDEA 或 Eclipse。
- 基本上熟悉 Java 程式設計和 PowerPoint 簡報。

## 導入包
首先，從 Aspose.Slides for Java 匯入必要的套件：
```java
import com.aspose.slides.*;
```
## 第 1 步：設定簡報
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## 第 2 步：存取投影片
```java
//取得第一張投影片
ISlide slide = presentation.getSlides().get_Item(0);
```
## 第 3 步：建立文字框
```java
//建立一個自選圖形作為文字框
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## 第 4 步：新增上標文本
```java
//為正文建立一個段落
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
//為上標文字建立一部分
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); //設定上標擒縱機構
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//將帶上標的主要段落新增至文字框
textFrame.getParagraphs().add(mainParagraph);
```
## 第 5 步：新增下標文本
```java
//為下標文字建立另一個段落
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
//為下標文字建立一部分
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); //設定下標擒縱機構
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
//將下標段落新增至文字框
textFrame.getParagraphs().add(subscriptParagraph);
```
## 第 6 步：儲存簡報
```java
//儲存簡報
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## 結論
在本教程中，我們探討如何使用 Aspose.Slides for Java 透過上標和下標文字增強 Java PowerPoint 簡報。透過執行這些步驟，您可以創建更具視覺吸引力和資訊量的幻燈片，從而有效地傳達您的內容。

## 常見問題解答
### 什麼是 Java 版 Aspose.Slides？
Aspose.Slides for Java 是一個強大的函式庫，可讓開發人員以程式設計方式建立、操作和轉換 PowerPoint 簡報。
### 在哪裡可以找到有關 Aspose.Slides for Java 的更多文件？
詳細文件可以找到[這裡](https://reference.aspose.com/slides/java/).
### 如何取得 Aspose.Slides for Java 的臨時授權？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 我可以免費試用 Aspose.Slides for Java 嗎？
是的，您可以從以下位置下載免費試用版[這裡](https://releases.aspose.com/).
### 在哪裡可以獲得 Aspose.Slides for Java 的支援？
如需支援和討論，請訪問[Aspose.Slides 論壇](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
