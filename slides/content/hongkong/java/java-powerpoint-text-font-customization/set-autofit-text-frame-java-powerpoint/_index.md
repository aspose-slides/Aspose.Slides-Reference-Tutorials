---
title: 在 Java PowerPoint 中設定文字框架的自動調整
linktitle: 在 Java PowerPoint 中設定文字框架的自動調整
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 Java PowerPoint 中設定文字框架的自動調整。輕鬆建立動態簡報。
type: docs
weight: 14
url: /zh-hant/java/java-powerpoint-text-font-customization/set-autofit-text-frame-java-powerpoint/
---
## 介紹
在 Java 應用程式開發中，以程式設計方式建立動態且具有視覺吸引力的 PowerPoint 簡報是一項常見要求。 Aspose.Slides for Java 提供了一組強大的 API 來輕鬆實現這一目標。一項基本功能是為文字框架設定自動調整，確保文字在形狀內整齊調整，無需手動調整。本教學將逐步引導您完成整個過程，並利用 Aspose.Slides for Java 自動調整 PowerPoint 投影片中的文字。
## 先決條件
在深入學習本教學之前，請確保您已設定以下先決條件：
- 系統上安裝的 Java 開發工具包 (JDK)
- Aspose.Slides for Java 程式庫下載並在您的 Java 專案中引用
- 整合開發環境 (IDE)，例如 IntelliJ IDEA 或 Eclipse
### 導入包
首先，請確保在您的 Java 專案中匯入必要的 Aspose.Slides 類別：
```java
import com.aspose.slides.*;
import java.awt.*;
```
## 第 1 步：建立新簡報
首先建立一個新的 PowerPoint 簡報實例，您將在其中新增投影片和形狀。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立Presentation類別的實例
Presentation presentation = new Presentation();
```
## 第 2 步：存取投影片以新增形狀
存取簡報的第一張投影片，在其中新增帶有自動調整文字的形狀。
```java
//存取第一張投影片
ISlide slide = presentation.getSlides().get_Item(0);
```
## 第 3 步：新增自選圖形（矩形）
將自選圖形（矩形）新增至投影片的特定座標和尺寸。
```java
//新增矩形類型的自選圖形
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## 第四步：將TextFrame加入矩形中
將文字方塊新增至矩形形狀。
```java
//將 TextFrame 加入矩形
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
```
## 第5步：設定文字方塊自動調整
設定文字框架的自動調整屬性以根據形狀大小調整文字。
```java
//存取文字框架
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## 第 6 步：將文字新增至文字框架
將文字內容新增至形狀內的文字框架。
```java
//為文字框架建立 Paragraph 對象
IParagraph para = txtFrame.getParagraphs().get_Item(0);
//為段落建立 Partion 對象
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## 第 7 步：儲存簡報
使用自動調整文字框架儲存修改後的簡報。
```java
//儲存簡報
presentation.save(dataDir + "formatText_out.pptx", SaveFormat.Pptx);
```

## 結論
在本教學中，您學習如何使用 Aspose.Slides for Java 在 Java PowerPoint 簡報中設定文字框架的自動調整。透過執行這些步驟，您可以自動在形狀中調整文本，從而以程式設計方式增強簡報的可讀性和美觀性。

## 常見問題解答
### 什麼是 Java 版 Aspose.Slides？
Aspose.Slides for Java 是一個強大的 Java API，可讓開發人員建立、閱讀、操作和轉換 PowerPoint 簡報。
### 如何下載 Java 版 Aspose.Slides？
您可以從以下位置下載 Aspose.Slides for Java：[這裡](https://releases.aspose.com/slides/java/).
### 我可以免費試用 Aspose.Slides for Java 嗎？
是的，您可以從以下位置取得 Aspose.Slides for Java 的免費試用版：[這裡](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.Slides for Java 的文檔？
您可以找到 Aspose.Slides for Java 的詳細文檔[這裡](https://reference.aspose.com/slides/java/).
### 我如何獲得 Aspose.Slides for Java 的支援？
您可以從以下位置取得 Aspose.Slides for Java 的社群和專業支援：[這裡](https://forum.aspose.com/c/slides/11).