---
title: Java 投影片中的投影片放映媒體控件
linktitle: Java 投影片中的投影片放映媒體控件
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何透過 Aspose.Slides for Java 在 Java 投影片中啟用和使用媒體控制項。使用媒體控制增強您的簡報。
type: docs
weight: 11
url: /zh-hant/java/media-controls/slide-show-media-controls-in-java-slides/
---

## Java 投影片中投影片放映媒體控制簡介

在動態且引人入勝的演示領域，多媒體元素在吸引觀眾注意力方面發揮關鍵作用。 Java Slides 在 Aspose.Slides for Java 的幫助下，讓開發人員能夠創建無縫結合媒體控制的迷人幻燈片。無論您是設計培訓模組、銷售宣傳還是教育演示，在幻燈片放映期間控制媒體的能力都會改變遊戲規則。

## 先決條件

在深入研究程式碼之前，請確保滿足以下先決條件：

- 您的系統上安裝了 Java 開發工具包 (JDK)。
-  Java 函式庫的 Aspose.Slides。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/java/).
- 您選擇的整合開發環境 (IDE)，例如 IntelliJ IDEA 或 Eclipse。

## 第 1 步：設定您的開發環境

在我們深入研究程式碼之前，請確保您已正確設定開發環境。按著這些次序：

- 在您的系統上安裝 JDK。
- 從提供的連結下載 Aspose.Slides for Java。
- 設定您首選的 IDE。

## 第 2 步：建立新簡報

讓我們從建立一個新簡報開始。以下是在 Java Slides 中執行此操作的方法：

```java
// PPTX 文件的路徑
String outFilePath = RunExamples.getOutPath() + "SlideShowMediaControl.pptx";
Presentation pres = new Presentation();
```

在此程式碼片段中，我們建立一個新的簡報物件並指定保存簡報的路徑。

## 第 3 步：啟用媒體控制

若要在投影片模式下啟用媒體控制顯示，請使用下列程式碼：

```java
pres.getSlideShowSettings().setShowMediaControls(true);
```

這行程式碼指示 Java Slides 在投影片放映期間顯示媒體控制項。

## 第 4 步：將媒體新增至幻燈片

現在，讓我們為幻燈片添加媒體。您可以使用 Java Slides 的豐富功能將音訊或視訊檔案新增至幻燈片。

自訂媒體播放
您可以進一步自訂媒體播放，例如設定開始和結束時間、音量等，為觀眾打造量身訂製的多媒體體驗。

## 第 5 步：儲存簡報

新增媒體並自訂其播放後，請使用以下程式碼將簡報儲存為 PPTX 格式：

```java
pres.save(outFilePath, SaveFormat.Pptx);
```

此程式碼在啟用媒體控制的情況下儲存您的簡報。

## Java 投影片中投影片放映媒體控制項的完整原始碼

```java
// PPTX 文件的路徑
String outFilePath = RunExamples.getOutPath() + "SlideShowMediaControl.pptx";
Presentation pres = new Presentation();
try {
	//啟用投影片模式下的媒體控制顯示。
	pres.getSlideShowSettings().setShowMediaControls(true);
	//以 PPTX 格式儲存簡報。
	pres.save(outFilePath, SaveFormat.Pptx);
} finally {
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，我們探討如何使用 Aspose.Slides for Java 在 Java Slides 中啟用和利用媒體控制項。透過執行以下步驟，您可以使用互動式多媒體元素建立引人入勝的演示文稿，以吸引觀眾。

## 常見問題解答

### 如何將多個媒體檔案新增到一張投影片中？

若要將多個媒體檔案新增至單張投影片中，您可以使用`addMediaFrame`幻燈片上的方法並指定每個幀的媒體檔案。然後，您可以單獨自訂每個影格的播放設定。

### 我可以控制簡報中的音訊音量嗎？

是的，您可以透過設定來控制簡報中的音訊音量`Volume`音頻幀的屬性。您可以將音量調整至您想要的水平。

### 幻燈片播放期間可以連續循環播放影片嗎？

是的，您可以設定`Looping`視訊幀的屬性`true`使影片在幻燈片放映期間連續循環播放。

### 如何在幻燈片出現時自動播放影片？

若要讓影片在投影片出現時自動播放，您可以設定`PlayMode`視訊幀的屬性`Auto`.

### 有沒有辦法在 Java Slides 中為影片添加字幕？

是的，您可以透過為包含影片的投影片新增文字框架或形狀，為 Java 投影片中的影片新增字幕或說明文字。然後，您可以使用計時設定將文字與影片播放同步。