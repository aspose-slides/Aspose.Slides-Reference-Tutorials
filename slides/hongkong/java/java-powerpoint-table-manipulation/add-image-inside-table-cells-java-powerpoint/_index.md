---
title: 在 Java PowerPoint 中的表格儲存格內新增圖像
linktitle: 在 Java PowerPoint 中的表格儲存格內新增圖像
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 透過此詳細的使用 Aspose.Slides for Java 的逐步指南，了解如何在 Java PowerPoint 簡報中的表格單元格內新增圖像。
type: docs
weight: 10
url: /zh-hant/java/java-powerpoint-table-manipulation/add-image-inside-table-cells-java-powerpoint/
---
## 介紹
如果您希望透過在表格單元格中嵌入圖像來增強 Java PowerPoint 演示文稿，那麼您來對地方了！今天，我們將深入研究使用 Aspose.Slides for Java 的詳細逐步指南。本教學將引導您完成整個過程，確保即使是新手也能遵循並取得令人驚嘆的結果。
## 先決條件
在開始之前，讓我們確保您擁有所需的一切：
1.  Java 開發工具包 (JDK)：確保您的電腦上安裝了 JDK。您可以從以下位置下載：[甲骨文網站](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java：從下列位置下載 Aspose.Slides 函式庫：[網站](https://releases.aspose.com/slides/java/).
3. 整合開發環境（IDE）：我們建議使用 IntelliJ IDEA 或 Eclipse 進行 Java 開發。
4. 圖像檔案：準備好要嵌入到 PowerPoint 表格單元格中的圖像檔案。
現在您已經具備了所有先決條件，讓我們繼續匯入必要的套件並編寫程式碼。
## 導入包
首先，將所需的套件匯入到您的 Java 專案中。這些套件將允許您利用 Aspose.Slides 和 Java 映像處理提供的功能。
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
讓我們將該範例分解為多個步驟，以便於理解。
## 第 1 步：設定簡報
首先設定簡報物件並存取第一張投影片。
```java
//定義文檔目錄的路徑
String dataDir = "Your Document Directory";
//實例化Presentation類別對象
Presentation presentation = new Presentation();
```
此程式碼片段初始化一個新的 PowerPoint 簡報並準備對其進行進一步修改。
## 第 2 步：存取第一張投影片
接下來，訪問簡報的第一張投影片。這張投影片將成為我們新增表格的畫布。
```java
try {
    //存取第一張投影片
    ISlide slide = presentation.getSlides().get_Item(0);
```
## 第 3 步：定義表格尺寸
定義表格的列寬和行高。此步驟對於確保表格單元格具有正確的尺寸至關重要。
```java
    //定義具有寬度的列和具有高度的行
    double[] columns = {150, 150, 150, 150};
    double[] rows = {100, 100, 100, 100, 90};
```
## 第 4 步：將表格新增至投影片
使用指定的尺寸將表格形狀新增至投影片。
```java
    //新增表格形狀以滑動
    ITable table = slide.getShapes().addTable(50, 50, columns, rows);
```
## 第5步：載入圖像
載入要嵌入到表格單元格中的圖像。確保圖像檔案在您指定的目錄中可用。
```java
    //建立 BufferedImage 物件來保存圖像文件
    BufferedImage image = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    //使用點陣圖物件建立 IPPImage 對象
    IPPImage imgx = presentation.getImages().addImage(image);
```
## 第 6 步：將圖像新增至表格單元格
現在，是時候將圖像新增至表格的第一個儲存格了。配置填滿格式並設定圖片屬性。
```java
    //將圖像新增至第一個表格單元格
    table.get_Item(0, 0).getCellFormat().getFillFormat().setFillType(FillType.Picture);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
## 步驟7：調整影像裁剪
如有必要，調整影像裁切以完美適合單元格。此步驟可確保您的影像看起來恰到好處。
```java
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropRight(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropLeft(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropTop(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropBottom(20);
```
## 第 8 步：儲存簡報
最後，將修改後的簡報儲存到您所需的目錄中。
```java
    //將 PPTX 儲存到磁碟
    presentation.save(dataDir + "Image_In_TableCell_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## 結論
你有它！透過執行下列步驟，您可以使用 Aspose.Slides 成功在 Java PowerPoint 簡報中的表格儲存格內新增圖像。本指南涵蓋了從設定環境到保存最終簡報的所有內容。我希望本教學可以幫助您創建更具視覺吸引力的簡報。
## 常見問題解答
### 什麼是 Java 版 Aspose.Slides？
Aspose.Slides for Java 是一個功能強大的 API，用於在 Java 應用程式中建立、修改和管理 PowerPoint 簡報。
### Aspose.Slides 是否有免費試用版？
是的，您可以獲得[免費試用](https://releases.aspose.com/)購買前試用 Aspose.Slides。
### 我可以在 Aspose.Slides 中使用任何圖像格式嗎？
Aspose.Slides 支援各種圖片格式，包括 JPEG、PNG、BMP 等。
### 在哪裡可以找到更詳細的文件？
您可以參考[文件](https://reference.aspose.com/slides/java/)以獲得更詳細的資訊和範例。
### 如何購買 Aspose.Slides for Java？
您可以從[阿斯普斯網站](https://purchase.aspose.com/buy).