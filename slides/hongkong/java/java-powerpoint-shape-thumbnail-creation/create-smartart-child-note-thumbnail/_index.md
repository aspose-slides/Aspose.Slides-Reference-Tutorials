---
title: 建立 SmartArt 子筆記縮圖
linktitle: 建立 SmartArt 子筆記縮圖
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides 在 Java 中建立 SmartArt 子筆記縮圖，從而輕鬆增強您的 PowerPoint 簡報。
weight: 15
url: /zh-hant/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介紹
在本教程中，我們將探索如何使用 Aspose.Slides 在 Java 中建立 SmartArt 子筆記縮圖。 Aspose.Slides 是一個功能強大的 Java API，可讓開發人員以程式設計方式處理 PowerPoint 簡報，輕鬆建立、修改和操作投影片。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1. 您的系統上安裝了 Java 開發工具包 (JDK)。
2.  Aspose.Slides for Java 程式庫已下載並在您的專案中設定。您可以從以下位置下載該程式庫[這裡](https://releases.aspose.com/slides/java/).

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
## 第 1 步：設定您的項目
確保您已使用 Aspose.Slides 庫設定並配置了 Java 專案。
## 第 2 步：建立簡報
實例化`Presentation`表示 PPTX 檔案的類別：
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## 第 3 步：新增 SmartArt
將 SmartArt 新增至您的簡報幻燈片：
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## 步驟 4：取得節點引用
透過索引獲取節點的引用：
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## 第 5 步：取得縮圖
檢索 SmartArt 節點的縮圖：
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## 第 6 步：儲存縮圖
將縮圖儲存到文件中：
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
根據簡報中的需要，對每個 SmartArt 節點重複這些步驟。

## 結論
在本教程中，我們學習如何使用 Aspose.Slides 在 Java 中建立 SmartArt 子筆記縮圖。有了這些知識，您就可以透過程式設計方式增強 PowerPoint 演示文稿，輕鬆添加具有視覺吸引力的元素。
## 常見問題解答
### 我可以使用 Aspose.Slides 操作現有的 PowerPoint 檔案嗎？
是的，Aspose.Slides 允許您修改現有的 PowerPoint 文件，包括新增、刪除或編輯投影片及其內容。
### Aspose.Slides 是否支援將投影片匯出為不同的檔案格式？
絕對地！ Aspose.Slides 支援將投影片匯出為各種格式，包括 PDF、圖像和 HTML 等。
### Aspose.Slides 適合企業級 PowerPoint 自動化嗎？
是的，Aspose.Slides 旨在有效可靠地處理企業級 PowerPoint 自動化任務。
### 我可以使用 Aspose.Slides 以程式設計方式建立複雜的 SmartArt 圖表嗎？
當然！ Aspose.Slides 為建立和操作不同複雜度的 SmartArt 圖表提供全面支援。
### Aspose.Slides 是否為開發人員提供技術支援？
是的，Aspose.Slides 透過他們的技術為開發人員提供專門的技術支持[論壇](https://forum.aspose.com/c/slides/11)和其他管道。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
