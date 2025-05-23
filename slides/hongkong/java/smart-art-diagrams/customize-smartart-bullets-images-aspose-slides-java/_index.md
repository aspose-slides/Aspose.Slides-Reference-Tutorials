---
"date": "2025-04-18"
"description": "了解如何使用 Aspose.Slides for Java 自訂帶有圖像的 SmartArt 專案符號來增強您的簡報。請按照本逐步指南操作，即可獲得專業外觀。"
"title": "如何使用 Aspose.Slides for Java 使用圖像自訂 SmartArt 項目符號 |逐步指南"
"url": "/zh-hant/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Java 自訂帶有圖像的 SmartArt 項目符號

## 介紹

創建具有視覺吸引力的簡報對於吸引觀眾的注意力和有效地傳達您的訊息至關重要。設計投影片時的常見挑戰是使用自訂影像增強 SmartArt 圖形中的項目符號。本教學將指導您使用 Aspose.Slides for Java 將圖片設定為 SmartArt 節點中的項目符號填滿格式，使您能夠專業地提升簡報的品質。

**您將學到什麼：**
- 設定並使用 Aspose.Slides for Java
- 使用 SmartArt 圖形中的圖像自訂項目符號
- 此客製化的實際應用
- 常見問題故障排除

在我們深入實施之前，請確保您已做好一切準備。

## 先決條件

要遵循本教程，請確保滿足以下先決條件：

1. **庫和依賴項**：您需要 Aspose.Slides for Java 函式庫版本 25.4 或更高版本。
2. **環境設定**：
   - 相容的 IDE，例如 IntelliJ IDEA 或 Eclipse
   - 您的電腦上安裝了 JDK 16
3. **知識前提**：熟悉Java程式設計和基本的PowerPoint簡報架構。

## 設定 Aspose.Slides for Java

首先，使用以下方法之一將 Aspose.Slides 庫包含在您的專案中：

### Maven

將此依賴項新增至您的 `pom.xml` 文件：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

將其包含在您的 `build.gradle`：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載

或者，直接從 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

**許可證取得步驟**：Aspose 提供免費試用許可證，非常適合測試其功能。您可以申請臨時許可證或購買許可證以消除評估限制。

若要初始化並設定您的環境，請建立一個實例 `Presentation` 類別如圖所示：

```java
Presentation presentation = new Presentation();
```

## 實施指南

本節將把流程分解為易於管理的步驟，解釋如何實現所需的功能。

### 添加帶有自訂項目符號填充的 SmartArt

#### 概述

我們首先在投影片中新增一個 SmartArt 形狀，然後使用影像填入自訂其項目符號。

#### 逐步說明

**1.初始化展示對象**

```java
Presentation presentation = new Presentation();
```

*目的*：初始化一個新的簡報實例，您將在其中新增 SmartArt 圖形。

**2. 新增 SmartArt 形狀**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*解釋*：此行在第一張投影片的位置 (x=10, y=10) 處新增一個新的 SmartArt 形狀，尺寸為 500x400 像素。這 `VerticalPictureList` 版面用於垂直對齊。

**3. 存取和自訂項目符號填充**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*目的*：檢查節點是否有 `BulletFillFormat` 財產。如果是的話，它會載入一個圖像並將其設定為項目符號的填充。
*參數*：
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`：影像檔案的路徑。
  - `PictureFillMode.Stretch`：確保影像完全填滿項目符號區域。

**4.儲存您的簡報**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}