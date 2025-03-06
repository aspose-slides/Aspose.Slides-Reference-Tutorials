---
title: 使用 Java 在 SmartArt 中設定項目符號填滿格式
linktitle: 使用 Java 在 SmartArt 中設定項目符號填滿格式
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Java 和 Aspose.Slides 在 SmartArt 中設定項目符號填色格式。高效演示操作的逐步指南。
weight: 18
url: /zh-hant/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介紹
在 Java 程式設計領域，有效率地操作簡報是一項常見要求，尤其是在處理 SmartArt 元素時。 Aspose.Slides for Java 成為執行此類任務的強大工具，提供了一系列以程式設計方式處理簡報的功能。在本教程中，我們將逐步深入研究使用 Java 和 Aspose.Slides 在 SmartArt 中設定項目符號填滿格式的過程。
## 先決條件
在開始本教學之前，請確保您具備以下先決條件：
### Java 開發工具包 (JDK)
您的系統上需要安裝 JDK。您可以從[網站](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)並按照安裝說明進行操作。
### 用於 Java 的 Aspose.Slides
從下列位置下載並安裝 Aspose.Slides for Java[下載連結](https://releases.aspose.com/slides/java/)。請依照特定作業系統的文件中提供的安裝說明進行操作。

## 導入包
首先，將必要的套件匯入您的 Java 專案：
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#讓我們將提供的範例分解為多個步驟，以便清楚了解如何使用 Java 和 Aspose.Slides 在 SmartArt 中設定項目符號填滿格式。
## 第 1 步：建立表示對象
```java
Presentation presentation = new Presentation();
```
首先，建立Presentation 類別的新實例，它代表一個PowerPoint 簡報。
## 第 2 步：新增 SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
接下來，將 SmartArt 形狀新增至投影片。此程式碼行初始化具有指定尺寸和佈局的新 SmartArt 形狀。
## 第三步：訪問SmartArt節點
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
現在，造訪 SmartArt 形狀中的第一個節點（或任何所需的節點）以修改其屬性。
## 第四步：設定項目符號填滿格式
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
在這裡，我們檢查是否支援項目符號填充格式。如果是，我們載入一個圖像檔案並將其設定為 SmartArt 節點的項目符號填充。
## 第 5 步：儲存簡報
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
最後，將修改後的簡報儲存到指定位置。

## 結論
恭喜！您已經成功學習如何使用 Java 和 Aspose.Slides 在 SmartArt 中設定項目符號填滿格式。此功能為 Java 應用程式中動態且具有視覺吸引力的演示開啟了一個充滿可能性的世界。
## 常見問題解答
### 我可以使用 Aspose.Slides for Java 從頭開始建立簡報嗎？
絕對地！ Aspose.Slides 提供了全面的 API，用於完全透過程式碼建立、修改和操作簡報。
### Aspose.Slides 是否與不同版本的 PowerPoint 相容？
是的，Aspose.Slides 確保與各種版本的 Microsoft PowerPoint 相容，從而能夠無縫整合到您的工作流程中。
### 我可以自訂除項目符號填滿格式之外的 SmartArt 元素嗎？
事實上，Aspose.Slides 可讓您自訂 SmartArt 形狀的各個方面，包括佈局、樣式、內容等。
### Aspose.Slides for Java 是否有試用版？
是的，您可以透過免費試用來探索 Aspose.Slides 的功能。只需從[網站](https://releases.aspose.com/slides/java/)並開始探索。
### 在哪裡可以找到 Aspose.Slides for Java 的支援？
如有任何疑問或協助，您可以造訪 Aspose.Slides 論壇：[這個連結](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
