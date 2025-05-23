---
"description": "了解如何使用 Aspose.Slides 在 Java 中建立 SmartArt 子註解縮圖，輕鬆增強您的 PowerPoint 簡報。"
"linktitle": "建立 SmartArt 子註釋縮圖"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "建立 SmartArt 子註釋縮圖"
"url": "/zh-hant/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 建立 SmartArt 子註釋縮圖

## 介紹
在本教程中，我們將探討如何使用 Aspose.Slides 在 Java 中建立 SmartArt 子註解縮圖。 Aspose.Slides 是一個強大的 Java API，可讓開發人員以程式設計方式處理 PowerPoint 簡報，讓他們能夠輕鬆地建立、修改和操作投影片。
## 先決條件
在開始之前，請確保您具備以下條件：
1. 您的系統上安裝了 Java 開發工具包 (JDK)。
2. 已下載 Aspose.Slides for Java 程式庫並在您的專案中進行設定。您可以從 [這裡](https://releases。aspose.com/slides/java/).

## 導入包
確保在 Java 類別中導入必要的套件：
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 步驟 1：設定您的項目
確保您已設定 Java 專案並配置了 Aspose.Slides 庫。
## 第 2 步：建立簡報
實例化 `Presentation` 表示 PPTX 檔案的類別：
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## 步驟 3：新增 SmartArt
將 SmartArt 新增至簡報投影片：
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## 步驟 4：取得節點引用
使用索引取得節點的引用：
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## 步驟 5：取得縮圖
檢索 SmartArt 節點的縮圖：
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## 步驟 6：儲存縮圖
將縮圖儲存到檔案：
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
根據需要對簡報中的每個 SmartArt 節點重複這些步驟。

## 結論
在本教程中，我們學習如何使用 Aspose.Slides 在 Java 中建立 SmartArt 子註解縮圖。有了這些知識，您可以以程式設計方式增強您的 PowerPoint 演示文稿，輕鬆添加具有視覺吸引力的元素。
## 常見問題解答
### 我可以使用 Aspose.Slides 來操作現有的 PowerPoint 文件嗎？
是的，Aspose.Slides 允許您修改現有的 PowerPoint 文件，包括新增、刪除或編輯投影片及其內容。
### Aspose.Slides 是否支援將投影片匯出為不同的檔案格式？
絕對地！ Aspose.Slides 支援將投影片匯出為各種格式，包括 PDF、圖像和 HTML 等。
### Aspose.Slides 適合企業級 PowerPoint 自動化嗎？
是的，Aspose.Slides 旨在有效可靠地處理企業級 PowerPoint 自動化任務。
### 我可以使用 Aspose.Slides 以程式設計方式建立複雜的 SmartArt 圖表嗎？
當然！ Aspose.Slides 為創建和操作不同複雜程度的 SmartArt 圖表提供了全面的支援。
### Aspose.Slides 是否為開發人員提供技術支援？
是的，Aspose.Slides 透過其 [論壇](https://forum.aspose.com/c/slides/11) 和其他管道。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}