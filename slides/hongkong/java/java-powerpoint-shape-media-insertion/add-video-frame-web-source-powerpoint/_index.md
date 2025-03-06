---
title: 在 PowerPoint 中新增來自 Web 來源的視訊幀
linktitle: 在 PowerPoint 中新增來自 Web 來源的視訊幀
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 新增來自 Web 來源的影片畫面來增強 PowerPoint 簡報。
type: docs
weight: 18
url: /zh-hant/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---
## 介紹
在本教學中，我們將學習如何使用 Aspose.Slides for Java 將影片畫面從 Web 來源（例如 YouTube）新增至 PowerPoint 簡報中。透過遵循這些逐步說明，您將能夠透過合併引人入勝的多媒體元素來增強您的簡報。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
- Java 程式設計的基礎知識。
- 系統上安裝了 JDK（Java 開發工具包）。
- 下載 Aspose.Slides for Java 程式庫並將其新增至您的 Java 專案。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/java/).
- 用於存取網路來源（例如 YouTube）的有效網路連線。

## 導入包
首先，將必要的套件匯入到您的 Java 專案中：
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## 第 1 步：建立 PowerPoint 簡報對象
初始化一個Presentation對象，它代表一個PowerPoint簡報：
```java
Presentation pres = new Presentation();
```
## 第 2 步：新增視訊幀
現在，讓我們為簡報添加視訊幀。該幀將包含來自網路來源的影片。我們將使用 addVideoFrame 方法：
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID”）；
```
將“VIDEO_ID”替換為您要嵌入的 YouTube 影片的 ID。
## 第三步：設定影片播放模式
設定視訊影格的播放模式。在此範例中，我們將其設定為自動：
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## 第 4 步：載入縮圖
為了增強視覺吸引力，我們將載入影片的縮圖。此步驟涉及從網路來源取得縮圖：
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## 第 5 步：儲存簡報
最後，儲存修改後的簡報：
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
將“YOUR_DIRECTORY”替換為您要儲存簡報的目錄。

## 結論
恭喜！您已經成功學習如何使用 Aspose.Slides for Java 在 PowerPoint 中從 Web 來源新增視訊影格。結合影片等多媒體元素可以顯著增強簡報的影響力和參與度。
## 常見問題解答
### 我可以添加 YouTube 以外來源的影片嗎？
是的，您可以添加來自各種網絡源的視頻，只要它們提供可嵌入的鏈接即可。
### 我需要網路連線才能播放嵌入影片嗎？
是的，需要有效的網路連線才能從網路來源串流傳輸影片。
### 我可以自訂視訊畫面的外觀嗎？
絕對地！ Aspose.Slides 提供了廣泛的選項來自訂視訊框架的外觀和行為。
### Aspose.Slides 與所有版本的 PowerPoint 相容嗎？
Aspose.Slides支援多種PowerPoint版本，確保不同平台之間的相容性。
### 在哪裡可以找到有關 Aspose.Slides 的更多資源和支援？
您可以訪問[Aspose.Slides 論壇](https://forum.aspose.com/c/slides/11)尋求協助、文件和社群支援。