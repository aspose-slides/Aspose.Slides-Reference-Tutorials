---
title: 在 PowerPoint 中建立縮放框架
linktitle: 在 PowerPoint 中建立縮放框架
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 中建立引人入勝的縮放框架。按照我們的指南為您的簡報添加互動式元素。
weight: 17
url: /zh-hant/java/java-powerpoint-shape-thumbnail-creation/create-zoom-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 PowerPoint 中建立縮放框架

## 介紹
創建引人入勝的 PowerPoint 簡報是一門藝術，有時，最小的添加就能產生巨大的影響。其中一項功能是縮放框架，它允許您放大特定的幻燈片或圖像，從而創建動態的互動式簡報。在本教學中，我們將引導您完成使用 Aspose.Slides for Java 在 PowerPoint 中建立縮放框架的過程。
## 先決條件
在深入學習本教學之前，請確保您具備以下條件：
- 您的系統上安裝了 Java 開發工具包 (JDK)。
-  Java 函式庫的 Aspose.Slides。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/java/).
- 整合開發環境 (IDE)，例如 IntelliJ IDEA 或 Eclipse。
- Java 程式設計的基礎知識。
## 導入包
首先，您需要在 Java 專案中匯入必要的套件。這些導入將提供對本教學所需的 Aspose.Slides 功能的存取。
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## 第 1 步：設定簡報
首先，我們需要建立一個新的簡報並在其中添加幾張投影片。
```java
//輸出檔名
String resultPath = "ZoomFramePresentation.pptx";
//來源影像的路徑
String imagePath = "Your Document Directory/aspose-logo.jpg";
Presentation pres = new Presentation();
try {
    //將新投影片新增至簡報
    ISlide slide2 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
    ISlide slide3 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
```
## 第 2 步：自訂投影片背景
我們希望透過添加背景顏色來使我們的幻燈片在視覺上與眾不同。
### 設定第二張投影片的背景
```java
    //為第二張投影片建立背景
    slide2.getBackground().setType(BackgroundType.OwnBackground);
    slide2.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide2.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
    //為第二張投影片建立一個文字框
    IAutoShape autoshape = slide2.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Second Slide");
```
### 設定第三張投影片的背景
```java
    //為第三張投影片建立背景
    slide3.getBackground().setType(BackgroundType.OwnBackground);
    slide3.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide3.getBackground().getFillFormat().getSolidFillColor().setColor(Color.DARK_GRAY);
    //為第三張投影片建立一個文字框
    autoshape = slide3.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Third Slide");
```
## 第 3 步：新增縮放框
現在，讓我們將縮放框架新增至簡報中。我們將添加一個帶有幻燈片預覽的縮放框架和另一個帶有自訂圖像的縮放框架。
### 新增帶有幻燈片預覽的縮放框
```java
    //新增帶有幻燈片預覽的 ZoomFrame 對象
    IZoomFrame zoomFrame1 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(20, 20, 250, 200, slide2);
```
### 添加帶有自訂圖像的縮放框
```java
    //新增帶有自訂圖像的 ZoomFrame 對象
    byte[] imageBytes = Files.readAllBytes(Paths.get(imagePath));
    IPPImage image = pres.getImages().addImage(imageBytes);
    IZoomFrame zoomFrame2 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(200, 250, 250, 100, slide3, image);
```
## 第 4 步：自訂縮放框
為了使我們的縮放框架脫穎而出，我們將定制它們的外觀。
### 自訂第二個縮放框
```java
    //為zoomFrame2物件設定縮放框架格式
    zoomFrame2.getLineFormat().setWidth(5);
    zoomFrame2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    zoomFrame2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
    zoomFrame2.getLineFormat().setDashStyle(LineDashStyle.DashDot);
```
### 隱藏第一個縮放框的背景
```java
    //不顯示 ZoomFrame1 物件的背景
    zoomFrame1.setShowBackground(false);
```
## 第 5 步：儲存簡報
最後，我們將簡報儲存到指定的路徑。
```java
    //儲存簡報
    pres.save(resultPath, SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## 結論
使用 Aspose.Slides for Java 在 PowerPoint 中建立縮放框架可以顯著增強簡報的互動性和參與度。透過遵循本教學中概述的步驟，您可以輕鬆新增投影片預覽和自訂影像作為縮放框架，自訂它們以適應簡報的主題。快樂的演講！
## 常見問題解答
### 什麼是 Java 版 Aspose.Slides？
Aspose.Slides for Java 是一個功能強大的 API，用於以程式設計方式建立和操作 PowerPoint 簡報。
### 如何安裝 Aspose.Slides for Java？
您可以從以下位置下載 Aspose.Slides for Java：[網站](https://releases.aspose.com/slides/java/)並將其添加到您的專案的依賴項中。
### 我可以自訂縮放框的外觀嗎？
是的，Aspose.Slides 允許您自訂縮放框架的各種屬性，例如線條樣式、顏色和背景可見性。
### 是否可以將圖像新增至縮放框架？
絕對地！您可以透過讀取圖像檔案並將其新增至簡報中來將自訂圖像新增至縮放框架。
### 在哪裡可以找到更多範例和文件？
您可以在以下位置找到全面的文件和範例[Aspose.Slides for Java 文件頁面](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
