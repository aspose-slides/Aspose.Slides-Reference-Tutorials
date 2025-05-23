---
"description": "了解如何使用 Aspose.Slides for Java 在 Java 中建立縮放因子縮圖。易於遵循的指南，提供逐步說明。"
"linktitle": "建立縮放因子縮圖"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "建立縮放因子縮圖"
"url": "/zh-hant/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 建立縮放因子縮圖

## 介紹
在本教程中，我們將引導您完成使用 Aspose.Slides for Java 建立縮放因子縮圖的過程。請按照這些逐步說明來獲得您想要的結果。
## 先決條件
在開始之前，請確保您符合以下先決條件：
- 您的系統上安裝了 Java 開發工具包 (JDK)。
- 下載 Aspose.Slides for Java 程式庫並在您的 Java 專案中進行設定。
- 對 Java 程式語言有基本的了解。

## 導入包
首先，在 Java 程式碼中匯入使用 Aspose.Slides 所需的必要套件。 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

現在，讓我們將提供的範例分解為多個步驟：
## 步驟1：設定文檔目錄
定義 PowerPoint 簡報文件所在的文件目錄的路徑。
```java
String dataDir = "Your Document Directory";
```
代替 `"Your Document Directory"` 使用您的實際文件目錄的路徑。
## 步驟 2：實例化演示對象
建立 Presentation 類別的實例來表示 PowerPoint 簡報檔案。
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
確保更換 `"HelloWorld.pptx"` 使用您的 PowerPoint 簡報文件的名稱。
## 步驟3：建立全尺寸影像
從簡報中產生所需投影片的全尺寸影像。
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
此程式碼會擷取簡報第一張投影片上第一個形狀的縮圖。
## 步驟4：儲存影像
將產生的映像以 PNG 格式儲存到磁碟。
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
確保更換 `"Scaling Factor Thumbnail_out.png"` 使用所需的輸出檔名。

## 結論
總之，您已成功使用 Aspose.Slides for Java 建立了縮放因子縮圖。透過遵循提供的步驟，您可以輕鬆地將此功能整合到您的 Java 應用程式中。
## 常見問題解答
### 我可以將 Aspose.Slides for Java 與任何 Java IDE 一起使用嗎？
是的，Aspose.Slides for Java 可以與任何 Java 整合開發環境 (IDE) 一起使用，例如 Eclipse、IntelliJ IDEA 或 NetBeans。
### Aspose.Slides for Java 有免費試用版嗎？
是的，您可以造訪以下網址免費試用 Aspose.Slides for Java [網站](https://releases。aspose.com/).
### 在哪裡可以找到對 Aspose.Slides for Java 的支援？
您可以在 [Aspose.Slides論壇](https://forum。aspose.com/c/slides/11).
### 如何購買 Aspose.Slides for Java？
您可以從 [購買頁面](https://purchase。aspose.com/buy).
### 我是否需要臨時授權才能使用 Aspose.Slides for Java？
是的，你可以從 [臨時執照頁面](https://purchase。aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}