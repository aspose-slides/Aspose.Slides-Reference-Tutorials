---
title: 在 Java PowerPoint 中建立多層項目符號
linktitle: 在 Java PowerPoint 中建立多層項目符號
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 中建立多層項目符號。包含程式碼範例和常見問題的逐步指南。
type: docs
weight: 14
url: /zh-hant/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/
---
## 介紹
在本教學中，我們將探討如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中建立多層項目符號。添加要點是在簡報中創建有組織且具有視覺吸引力的內容的常見要求。我們將逐步完成流程，確保在本指南結束時，您將能夠透過多個層級的結構化要點來增強您的簡報。
## 先決條件
在開始之前，請確保您已進行以下設定：
- Java 開發環境：確保您的系統上安裝了 Java 開發工具包 (JDK)。
-  Aspose.Slides for Java 函式庫：從下列位置下載並安裝 Aspose.Slides for Java[這裡](https://releases.aspose.com/slides/java/).
- IDE：使用您首選的 Java 整合開發環境 (IDE)，例如 IntelliJ IDEA、Eclipse 或其他。
- 基礎知識：熟悉 Java 程式設計和基本 PowerPoint 概念將會有所幫助。

## 導入包
在深入學習本教程之前，讓我們從 Aspose.Slides for Java 匯入我們將在整個教程中使用的必要套件。
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## 第 1 步：設定您的項目
首先，在 IDE 中建立一個新的 Java 項目，並將 Aspose.Slides for Java 加入專案的依賴項。確保專案的建置路徑中包含必要的 Aspose.Slides JAR 檔案。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
```
## 第 2 步：初始化表示對象
首先建立一個新的演示實例。這將作為您的 PowerPoint 文檔，您將在其中添加幻燈片和內容。
```java
Presentation pres = new Presentation();
```
## 第 3 步：存取投影片
接下來，存取要新增多層項目符號的投影片。對於本例，我們將使用第一張投影片（`Slide(0)`）。
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 步驟 4：新增帶有文字方塊的自選圖形
將自選圖形新增至投影片，您將在其中放置帶有多層級項目符號的文字。
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## 第 5 步：存取文字框架
存取自選圖形中的文字框架，您將在其中添加帶有項目符號點的段落。
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); //清除預設段落
```
## 第 6 步：新增帶有項目符號的段落
新增具有不同層級項目符號的段落。以下是添加多層次項目符號的方法：
```java
//第一級
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
//第二級
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
//第三級
IParagraph para3 = new Paragraph();
para3.setText("Third Level");
para3.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para3.getParagraphFormat().getBullet().setChar((char) 8226);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para3.getParagraphFormat().setDepth((short) 2);
text.getParagraphs().add(para3);
//第四級
IParagraph para4 = new Paragraph();
para4.setText("Fourth Level");
para4.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para4.getParagraphFormat().getBullet().setChar('-');
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para4.getParagraphFormat().setDepth((short) 3);
text.getParagraphs().add(para4);
```
## 第 7 步：儲存簡報
最後，將簡報儲存為 PPTX 檔案到您所需的目錄中。
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## 結論
在本教學中，我們介紹如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中建立多層項目符號。透過執行這些步驟，您可以在不同層級使用有組織的要點來有效地建立內容，從而增強簡報的清晰度和視覺吸引力。
## 常見問題解答
### 我可以進一步自訂項目符號嗎？
是的，您可以透過調整 Unicode 字元或使用不同的形狀來自訂項目符號。
### Aspose.Slides 是否支援其他項目符號類型？
是的，Aspose.Slides 支援各種項目符號類型，包括符號、數字和自訂圖像。
### Aspose.Slides 與所有版本的 PowerPoint 相容嗎？
Aspose.Slides 產生與 Microsoft PowerPoint 2007 及更高版本相容的簡報。
### 我可以使用 Aspose.Slides 自動產生投影片嗎？
是的，Aspose.Slides 提供了 API 來自動建立、修改和操作 PowerPoint 簡報。
### 在哪裡可以獲得 Aspose.Slides for Java 的支援？
您可以從 Aspose.Slides 社區和專家那裡獲得支持[Aspose.Slides 論壇](https://forum.aspose.com/c/slides/11).