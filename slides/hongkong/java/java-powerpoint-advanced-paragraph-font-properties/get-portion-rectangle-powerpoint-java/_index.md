---
title: 使用 Java 在 PowerPoint 中取得部分矩形
linktitle: 使用 Java 在 PowerPoint 中取得部分矩形
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 透過這個詳細的逐步教學，了解如何使用 Aspose.Slides for Java 在 PowerPoint 中取得部分矩形。非常適合 Java 開發人員。
weight: 12
url: /zh-hant/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介紹
使用 Aspose.Slides for Java 在 Java 中建立動態簡報變得輕而易舉。在本教學中，我們將深入探討使用 Aspose.Slides 在 PowerPoint 中取得部分矩形的細節。我們將涵蓋從設定環境到逐步分解程式碼的所有內容。那麼，就讓我們開始吧！
## 先決條件
在我們進入程式碼之前，讓我們確保您擁有順利執行所需的一切：
1. Java 開發工具包 (JDK)：確保您的電腦上安裝了 JDK 8 或更高版本。
2.  Aspose.Slides for Java：從下列位置下載最新版本[這裡](https://releases.aspose.com/slides/java/).
3. 整合開發環境 (IDE)：Eclipse、IntelliJ IDEA 或您選擇的任何其他 Java IDE。
4. Java 基礎知識：了解 Java 程式設計至關重要。
## 導入包
首先，讓我們導入必要的套件。這將包括 Aspose.Slides 和其他一些用於有效處理我們的任務的工具。
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## 第 1 步：設定簡報
第一步是建立一個新的簡報。這將是我們工作的畫布。
```java
Presentation pres = new Presentation();
```
## 第 2 步：建立表
現在，讓我們為簡報的第一張投影片新增一個表格。該表將包含我們將在其中添加文本的單元格。
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## 步驟 3：在儲存格中新增段落
接下來，我們將建立段落並將它們新增至表格中的特定儲存格。這涉及清除任何現有文本，然後添加新段落。
```java
//創建段落
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
//將文字加入表格儲存格中
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## 步驟 4：將文字框架新增至自選圖形
為了使我們的簡報更加動態，我們將向自選圖形添加一個文字框架並設定其對齊方式。
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## 第5步：計算座標
我們需要取得表格單元格左上角的座標。這將幫助我們準確地放置形狀。
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## 步驟 6：為段落和部分添加框架
使用`IParagraph.getRect()`和`IPortion.getRect()`方法，我們可以為我們的段落和部分添加框架。這涉及迭代段落和部分、圍繞它們創建形狀以及自訂它們的外觀。
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## 步驟 7：為自選圖形段落新增框架
同樣，我們將向自選圖形中的段落添加框架，增強簡報的視覺吸引力。
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## 步驟 8：儲存簡報
最後，我們將簡報儲存到指定的路徑。
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## 第9步：清理
處理演示物件以釋放資源是一種很好的做法。
```java
if (pres != null) pres.dispose();
```
## 結論
恭喜！您已經成功學習如何使用 Aspose.Slides for Java 在 PowerPoint 中取得部分矩形。這個強大的函式庫為以程式設計方式創建動態且具有視覺吸引力的簡報開闢了可能性的世界。深入研究 Aspose.Slides 並探索更多功能以進一步增強您的簡報。
## 常見問題解答
### 什麼是 Java 版 Aspose.Slides？
Aspose.Slides for Java 是一個功能強大的函式庫，可讓開發人員以程式設計方式建立、修改和操作 PowerPoint 簡報。
### 我可以在商業專案中使用 Aspose.Slides for Java 嗎？
是的，Aspose.Slides for Java可以用於商業專案。您可以從以下位置購買許可證[這裡](https://purchase.aspose.com/buy).
### Aspose.Slides for Java 是否有免費試用版？
是的，您可以從以下位置下載免費試用版[這裡](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.Slides for Java 的文檔？
文件可用[這裡](https://reference.aspose.com/slides/java/).
### 我如何獲得 Aspose.Slides for Java 的支援？
您可以從 Aspose 論壇獲得支持[這裡](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
