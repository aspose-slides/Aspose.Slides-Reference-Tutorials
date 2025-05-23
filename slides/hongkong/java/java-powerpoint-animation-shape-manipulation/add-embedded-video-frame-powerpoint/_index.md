---
"description": "透過本逐步教學了解如何使用 Aspose.Slides for Java 在 PowerPoint 中嵌入影片影格。輕鬆增強您的簡報。"
"linktitle": "在 PowerPoint 中新增嵌入式視訊幀"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 PowerPoint 中新增嵌入式視訊幀"
"url": "/zh-hant/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 PowerPoint 中新增嵌入式視訊幀

## 介紹
在 PowerPoint 簡報中加入影片可以使其更具吸引力和資訊量。使用 Aspose.Slides for Java，您可以輕鬆地將影片直接嵌入到投影片中。在本教程中，我們將逐步引導您完成整個過程，確保您了解程式碼的每個部分及其功能。無論您是經驗豐富的開發人員還是剛起步，本指南都將幫助您使用嵌入式影片增強您的簡報。
## 先決條件
在深入研究程式碼之前，請確保已滿足以下先決條件：
1. Java 開發工具包 (JDK)：確保您的機器上安裝了 JDK。
2. Aspose.Slides for Java：下載並安裝 Aspose.Slides for Java 函式庫。
3. 整合開發環境（IDE）：使用 IntelliJ IDEA 或 Eclipse 等 IDE 獲得更好的開發體驗。
4. 影片檔案：有一個想要嵌入到 PowerPoint 簡報中的影片檔案。
## 導入包
首先，您需要匯入使用 Aspose.Slides 所需的套件。這些匯入將幫助您管理投影片、影片和簡報檔案。
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## 步驟 1：設定您的環境
在開始編碼之前，請確保您的環境已正確設定。這涉及創建必要的目錄和準備視訊檔案。
```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// 如果目錄尚不存在，則建立該目錄。
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## 步驟2：實例化表示類
建立一個實例 `Presentation` 班級。此類別代表您的 PowerPoint 文件。
```java
// 實例化代表 PPTX 的 Presentation 類
Presentation pres = new Presentation();
```
## 步驟 3：取得第一張投影片
存取簡報中將嵌入影片的第一張投影片。
```java
// 取得第一張投影片
ISlide sld = pres.getSlides().get_Item(0);
```
## 步驟 4：將影片新增至簡報
將影片檔案嵌入到簡報中。確保視訊路徑指定正確。
```java
// 在簡報中嵌入視頻
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## 步驟 5：將視訊幀新增至幻燈片
在幻燈片上建立視訊幀並設定其尺寸和位置。
```java
// 新增視訊幀
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## 步驟6：配置視訊幀屬性
將影片設定為影片畫面並配置其播放設置，如播放模式和音量。
```java
// 將影片設定為視訊幀
vf.setEmbeddedVideo(vid);
// 設定影片播放模式和音量
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## 步驟 7：儲存簡報
將嵌入影片的簡報儲存到指定的目錄。
```java
// 將 PPTX 檔案寫入磁碟
pres.save(resultPath, SaveFormat.Pptx);
```
## 步驟 8：清理資源
最後，處置表示物件以釋放資源。
```java
// 處置演示對象
if (pres != null) pres.dispose();
```
## 結論
使用 Aspose.Slides for Java 在 PowerPoint 簡報中嵌入影片是一個簡單的過程。透過遵循本指南中概述的步驟，您可以使用引人入勝的影片內容來增強您的簡報。請記住，熟能生巧，因此請嘗試嵌入不同的影片並調整其屬性，以查看哪種最適合您的需求。
## 常見問題解答
### 我可以在一張投影片中嵌入多個影片嗎？
是的，您可以透過新增多個影片畫面在一張投影片中嵌入多個影片。
### 我如何控制影片的播放？
您可以使用 `setPlayMode` 和 `setVolume` 方法 `IVideoFrame` 班級。
### Aspose.Slides 支援哪些影片格式？
Aspose.Slides 支援各種視訊格式，包括 MP4、AVI 和 WMV。
### 我需要許可證才能使用 Aspose.Slides 嗎？
是的，您需要有效的許可證才能使用 Aspose.Slides。您可以獲得臨時許可證以進行評估。
### 我可以自訂視訊畫面的大小和位置嗎？
是的，您可以在新增視訊畫面時透過設定適當的參數來自訂大小和位置。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}