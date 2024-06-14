---
title: 在 PowerPoint 中新增相對比例高度相框
linktitle: 在 PowerPoint 中新增相對比例高度相框
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中新增相對比例高度圖片框架，從而增強您的視覺內容。
type: docs
weight: 15
url: /zh-hant/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---
## 介紹
在本教學中，您將學習如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中新增具有相對比例高度的圖片框架。
## 先決條件
在開始之前，請確保您具備以下條件：
1. 您的系統上安裝了 Java 開發工具包 (JDK)。
2. 下載 Aspose.Slides for Java 程式庫並將其新增至您的 Java 專案。

## 導入包
首先，在您的 Java 專案中匯入必要的套件：
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 第 1 步：設定您的項目
首先，請確保您已為專案設定了目錄，並且 Java 環境已正確配置。
## 第 2 步：實例化表示對象
使用 Aspose.Slides 建立一個新的演示物件：
```java
Presentation presentation = new Presentation();
```
## 第三步：載入要新增的圖片
載入要新增到簡報中的圖像：
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## 第四步：為投影片新增相框
將圖片框新增至簡報的幻燈片：
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## 第 5 步：設定相對比例寬度和高度
設定相框的相對比例寬度和高度：
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## 第 6 步：儲存簡報
儲存新增了相框的簡報：
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## 結論
透過執行下列步驟，您可以使用 Aspose.Slides for Java 在 PowerPoint 簡報中輕鬆新增具有相對比例高度的圖片框架。嘗試不同的比例值以獲得所需的影像外觀。

## 常見問題解答
### 我可以使用此方法將多個圖片框新增至單張投影片嗎？
是的，您可以透過對每個圖像重複此過程來將多個圖片框新增至幻燈片。
### Aspose.Slides for Java 是否與所有版本的 PowerPoint 相容？
Aspose.Slides for Java與各種版本的PowerPoint相容，確保建立簡報的靈活性。
### 可以自訂相框的位置和大小嗎？
當然，您可以調整位置和大小參數`addPictureFrame`方法以滿足您的要求。
### Aspose.Slides for Java 是否支援 JPEG 以外的其他影像格式？
是的，Aspose.Slides for Java 支援各種圖片格式，包括 PNG、GIF、BMP 等。
### 是否有可供 Aspose.Slides 使用者使用的社群論壇或支援管道？
是的，您可以造訪 Aspose.Slides 論壇，以了解有關該程式庫的任何問題、討論或協助。