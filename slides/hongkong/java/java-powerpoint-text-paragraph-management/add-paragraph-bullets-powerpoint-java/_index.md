---
title: 使用 Java 在 PowerPoint 中新增段落項目符號
linktitle: 使用 Java 在 PowerPoint 中新增段落項目符號
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 投影片中新增段落項目符號。本教學將透過程式碼範例逐步引導您完成操作。
weight: 15
url: /zh-hant/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介紹
新增段落項目符號可以增強 PowerPoint 簡報的可讀性和結構。 Aspose.Slides for Java 提供了強大的工具來以程式設計方式操作演示文稿，包括使用各種項目符號樣式格式化文字的能力。在本教學中，您將學習如何使用 Java 程式碼並利用 Aspose.Slides 將專案符號點整合到 PowerPoint 投影片中。
## 先決條件
在開始之前，請確保您具備以下條件：
- Java 程式設計的基礎知識。
- 系統上安裝了 JDK（Java 開發工具包）。
-  Java 函式庫的 Aspose.Slides。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/java/).

## 導入包
首先，將必要的 Aspose.Slides 套件匯入到您的 Java 專案中：
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## 第 1 步：設定您的項目
首先，建立一個新的 Java 專案並將 Aspose.Slides for Java 庫新增到專案的建置路徑中。
## 第 2 步：初始化簡報
初始化一個演示物件（`Presentation`) 開始使用幻燈片。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立演示實例
Presentation pres = new Presentation();
```
## 第 3 步：存取投影片和文字框架
存取幻燈片 (`ISlide`）及其文字方塊（`ITextFrame`) 要新增項目符號的位置。
```java
//存取第一張投影片
ISlide slide = pres.getSlides().get_Item(0);
//新增和存取自動形狀
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
//存取已建立的自選圖形的文字框架
ITextFrame txtFrm = aShp.getTextFrame();
```
## 第 4 步：使用項目符號建立段落並設定其格式
建立段落 (`Paragraph`）並設定其項目符號樣式、縮排和文字。
```java
//創建一個段落
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
//創建另一個段落
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## 第 5 步：儲存簡報
將修改後的簡報儲存到 PowerPoint 檔案 (`PPTX`）。
```java
//將簡報編寫為 PPTX 文件
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## 第 6 步：清理資源
處理演示物件以釋放資源。
```java
//處置演示對象
if (pres != null) {
    pres.dispose();
}
```

## 結論
透過提供的程式碼範例，使用 Aspose.Slides for Java 在 PowerPoint 中新增段落項目符號非常簡單。自訂項目符號樣式和格式以無縫滿足您的簡報需求。

## 常見問題解答
### 我可以自訂項目符號顏色嗎？
是的，您可以使用 Aspose.Slides API 設定項目符號的自訂顏色。
### 如何新增嵌套項目符號？
嵌套項目符號涉及在段落內添加段落，並相應地調整縮排。
### 我可以為不同的投影片建立不同的項目符號樣式嗎？
是的，您可以以程式設計方式將獨特的項目符號樣式套用至不同的投影片。
### Aspose.Slides 與 Java 11 相容嗎？
是的，Aspose.Slides 支援 Java 11 及更高版本。
### 在哪裡可以找到更多範例和文件？
訪問[Aspose.Slides Java 文檔](https://reference.aspose.com/slides/java/)取得全面的指南和範例。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
