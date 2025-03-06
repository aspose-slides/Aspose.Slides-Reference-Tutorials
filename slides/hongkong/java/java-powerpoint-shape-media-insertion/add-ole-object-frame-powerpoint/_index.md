---
title: 在 PowerPoint 中新增 OLE 物件框架
linktitle: 在 PowerPoint 中新增 OLE 物件框架
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 將 OLE 物件框架無縫整合到 PowerPoint 簡報中。
weight: 13
url: /zh-hant/java/java-powerpoint-shape-media-insertion/add-ole-object-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 介紹
在 PowerPoint 簡報中新增 OLE（物件連結和嵌入）物件框架可顯著增強投影片的視覺吸引力和功能。借助 Aspose.Slides for Java，這個過程變得精簡且有效率。在本教程中，我們將引導您完成將 OLE 物件框架無縫整合到 PowerPoint 簡報中所需的步驟。
### 先決條件
在我們開始之前，請確保您具備以下先決條件：
1. Java 開發環境：確保您的系統上安裝了 Java 開發工具包 (JDK)。
2.  Aspose.Slides for Java：從網站下載並安裝 Aspose.Slides for Java[這裡](https://releases.aspose.com/slides/java/).
3. Java 程式設計的基本理解：熟悉 Java 程式設計概念和語法。
## 導入包
首先，您需要匯入必要的套件以利用 Aspose.Slides for Java 的功能。您可以這樣做：
```java
import com.aspose.slides.*;

import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
```
## 第 1 步：設定您的環境
確保您的專案配置正確，並且 Aspose.Slides 庫包含在您的類別路徑中。
## 第 2 步：初始化表示對象
建立一個Presentation物件來表示您正在使用的PowerPoint檔案：
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
//實例化表示 PPTX 的簡報類
Presentation pres = new Presentation();
```
## 第 3 步：存取投影片並載入對象
存取要新增 OLE 物件框架的幻燈片並載入物件檔案：
```java
ISlide sld = pres.getSlides().get_Item(0);
//載入檔案以進行串流傳輸
FileInputStream fs = new FileInputStream(dataDir + "book1.xlsx");
ByteArrayOutputStream mstream = new ByteArrayOutputStream();
byte[] buf = new byte[4096];
while (true) {
    int bytesRead = fs.read(buf, 0, buf.length);
    if (bytesRead <= 0)
        break;
    mstream.write(buf, 0, bytesRead);
}
```
## 第 4 步：建立嵌入資料對象
建立用於嵌入文件的資料對象：
```java
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.toByteArray(), "xlsx");
```
## 第 5 步：新增 OLE 物件框架
將 OLE 物件框架形狀新增至投影片：
```java
IOleObjectFrame oleObjectFrame = sld.getShapes().addOleObjectFrame(0, 0, (float)pres.getSlideSize().getSize().getWidth(),
        (float)pres.getSlideSize().getSize().getHeight(), dataInfo);
```
## 第 6 步：儲存簡報
將修改後的簡報儲存到磁碟：
```java
pres.save(outPath + "OleEmbed_out.pptx", SaveFormat.Pptx);
```

## 結論
恭喜！您已經成功學習如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中新增 OLE 物件框架。這項強大的功能可讓您嵌入各種類型的對象，增強投影片的互動性和視覺吸引力。

## 常見問題解答
### 我可以使用 Aspose.Slides for Java 嵌入 Excel 檔案以外的物件嗎？
是的，您可以嵌入各種類型的對象，包括 Word 文件、PDF 文件等。
### Aspose.Slides 是否與不同版本的 PowerPoint 相容？
Aspose.Slides 提供與各種 PowerPoint 版本的兼容性，確保無縫整合。
### 我可以自訂 OLE 物件框架的外觀嗎？
絕對地！ Aspose.Slides 提供了廣泛的選項來自訂 OLE 物件框架的外觀和行為。
### Aspose.Slides for Java 是否有試用版？
是的，您可以從以下位置下載免費試用版[這裡](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.Slides for Java 的支援？
您可以從Aspose.Slides論壇尋求支持和幫助[這裡](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
