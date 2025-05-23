---
"description": "了解如何使用 Aspose.Slides for Java 在 PowerPoint 中建立多層項目符號。包含程式碼範例和常見問題的逐步指南。"
"linktitle": "在 Java PowerPoint 中建立多層項目符號"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java PowerPoint 中建立多層項目符號"
"url": "/zh-hant/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PowerPoint 中建立多層項目符號

## 介紹
在本教學中，我們將探討如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中建立多層項目符號。新增項目符號是在簡報中創建有組織且具有視覺吸引力的內容的常見要求。我們將逐步介紹整個過程，確保在本指南結束時，您能夠使用多個層級的結構化要點來增強您的簡報。
## 先決條件
在開始之前，請確保您已進行以下設定：
- Java 開發環境：確保您的系統上安裝了 Java 開發工具包 (JDK)。
- Aspose.Slides for Java 函式庫：從下列位置下載並安裝 Aspose.Slides for Java [這裡](https://releases。aspose.com/slides/java/).
- IDE：使用您喜歡的 Java 整合開發環境 (IDE)，例如 IntelliJ IDEA、Eclipse 或其他。
- 基礎知識：熟悉 Java 程式設計和基本的 PowerPoint 概念將會有所幫助。

## 導入包
在深入學習本教學之前，讓我們先從 Aspose.Slides for Java 中匯入在整個教程中將用到的必要套件。
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## 步驟 1：設定您的項目
首先，在您的 IDE 中建立一個新的 Java 項目，並將 Aspose.Slides for Java 新增到專案的依賴項。確保必要的 Aspose.Slides JAR 檔案包含在專案的建置路徑中。
```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
```
## 步驟2：初始化演示對象
首先建立一個新的演示實例。這將作為您的 PowerPoint 文檔，您可以在其中新增幻燈片和內容。
```java
Presentation pres = new Presentation();
```
## 步驟 3：存取投影片
接下來，造訪您想要新增多層項目符號的投影片。對於此範例，我們將使用第一張投影片（`Slide(0)`）。
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 步驟 4：新增帶有文字方塊的自選圖形
在投影片中新增一個自選圖形，在其中放置帶有多層級項目符號的文字。
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## 步驟 5：存取文字框架
存取自選圖形內的文字框，您可以在其中新增帶有項目符號的段落。
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); // 清除預設段落
```
## 步驟 6：新增帶有項目符號的段落
新增具有不同層級項目符號的段落。新增多層項目符號的方法如下：
```java
// 第一級
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
// 第二級
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
// 第三級
IParagraph para3 = new Paragraph();
para3.setText("Third Level");
para3.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para3.getParagraphFormat().getBullet().setChar((char) 8226);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para3.getParagraphFormat().setDepth((short) 2);
text.getParagraphs().add(para3);
// 第四級
IParagraph para4 = new Paragraph();
para4.setText("Fourth Level");
para4.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para4.getParagraphFormat().getBullet().setChar('-');
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para4.getParagraphFormat().setDepth((short) 3);
text.getParagraphs().add(para4);
```
## 步驟 7：儲存簡報
最後，將簡報作為 PPTX 檔案儲存到您想要的目錄中。
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## 結論
在本教學中，我們介紹如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中建立多層項目符號。透過遵循這些步驟，您可以有效地建立您的內容，並使用不同層級的組織要點，增強簡報的清晰度和視覺吸引力。
## 常見問題解答
### 我可以進一步自訂項目符號嗎？
是的，您可以透過調整 Unicode 字元或使用不同的形狀來自訂項目符號。
### Aspose.Slides 是否支援其他項目符號類型？
是的，Aspose.Slides 支援多種項目符號類型，包括符號、數字和自訂圖像。
### Aspose.Slides 是否與所有版本的 PowerPoint 相容？
Aspose.Slides 產生與 Microsoft PowerPoint 2007 及更高版本相容的簡報。
### 我可以使用 Aspose.Slides 自動產生投影片嗎？
是的，Aspose.Slides 提供 API 來自動建立、修改和操作 PowerPoint 簡報。
### 在哪裡可以獲得 Aspose.Slides for Java 的支援？
您可以從 Aspose.Slides 社區和專家處獲得支持 [Aspose.Slides 論壇](https://forum。aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}