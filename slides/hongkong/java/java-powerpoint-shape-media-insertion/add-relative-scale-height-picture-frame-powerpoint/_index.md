---
"description": "了解如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中新增相對比例高度相框，以增強您的視覺內容。"
"linktitle": "在 PowerPoint 中新增相對比例高度相框"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 PowerPoint 中新增相對比例高度相框"
"url": "/zh-hant/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 PowerPoint 中新增相對比例高度相框

## 介紹
在本教學中，您將學習如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中新增具有相對比例高度的圖片框。
## 先決條件
在開始之前，請確保您已具備以下條件：
1. 您的系統上安裝了 Java 開發工具包 (JDK)。
2. Aspose.Slides for Java 程式庫已下載並新增到您的 Java 專案中。

## 導入包
首先，在 Java 專案中匯入必要的套件：
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 步驟 1：設定您的項目
首先，請確保您已為您的專案設定了目錄，並且您的 Java 環境已正確配置。
## 步驟2：實例化演示對象
使用 Aspose.Slides 建立一個新的演示物件：
```java
Presentation presentation = new Presentation();
```
## 步驟3：載入要新增的圖像
載入您想要新增到簡報的圖像：
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## 步驟 4：將圖片框新增至投影片
在簡報中的投影片中新增圖片框：
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## 步驟 5：設定相對比例寬度和高度
設定圖片框架的相對比例寬度和高度：
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## 步驟 6：儲存簡報
儲存新增了圖片框的簡報：
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## 結論
透過遵循這些步驟，您可以使用 Aspose.Slides for Java 在 PowerPoint 簡報中輕鬆新增具有相對比例高度的圖片框。嘗試不同的比例值來獲得影像所需的外觀。

## 常見問題解答
### 我可以使用此方法為單張投影片新增多個相框嗎？
是的，您可以透過對每張圖片重複此過程來為投影片新增多個相框。
### Aspose.Slides for Java 是否與所有版本的 PowerPoint 相容？
Aspose.Slides for Java 與各種版本的 PowerPoint 相容，確保建立簡報的靈活性。
### 我可以自訂相框的位置和大小嗎？
當然，你可以在 `addPictureFrame` 方法來滿足您的要求。
### Aspose.Slides for Java 除了 JPEG 之外還支援其他影像格式嗎？
是的，Aspose.Slides for Java 支援各種圖片格式，包括 PNG、GIF、BMP 等。
### 是否有可供 Aspose.Slides 使用者使用的社群論壇或支援管道？
是的，您可以造訪 Aspose.Slides 論壇，以了解有關該程式庫的任何問題、討論或協助。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}