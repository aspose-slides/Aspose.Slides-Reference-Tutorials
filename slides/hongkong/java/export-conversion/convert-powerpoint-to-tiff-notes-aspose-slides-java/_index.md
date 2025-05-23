---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為帶有註釋的高品質 TIFF 影像。請按照本逐步指南取得最佳轉換設定和故障排除提示。"
"title": "使用 Aspose.Slides for Java&#58; 將 PowerPoint 轉換為帶有註解的 TIFF綜合指南"
"url": "/zh-hant/java/export-conversion/convert-powerpoint-to-tiff-notes-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Java 中的 Aspose.Slides 將 PowerPoint 轉換為帶有註解的 TIFF

## 介紹

將 PowerPoint 簡報轉換為 TIFF 格式同時保留投影片註釋可能很有挑戰性。這個全面的教程將引導您使用 **Aspose.Slides for Java** 實現 .pptx 檔案到 TIFF 影像的高品質轉換，包括每張影像底部的所有重要註釋。

### 您將學到什麼：
- 在 Java 專案中設定 Aspose.Slides。
- 將 PowerPoint 簡報轉換為包含投影片註解的 TIFF 格式。
- 自訂轉換選項以獲得最佳結果。
- 解決轉換過程中的常見問題。

首先，請確保您已做好一切準備，以便有效地跟進。

## 先決條件

在深入學習本教學之前，請確保已準備好以下內容：

### 所需庫
- **Aspose.Slides for Java**：需要 25.4 或更高版本才能存取所有必要的功能。
  
### 環境設定
- Java 開發環境（例如 IntelliJ IDEA、Eclipse）。
- 確保您的系統安裝了相容的 JDK，最好是 16 版本。
### 知識前提
- 對 Java 程式設計有基本的了解。
- 熟悉使用 Maven 或 Gradle 管理外部程式庫。

## 設定 Aspose.Slides for Java

若要在專案中使用 Aspose.Slides，請將其新增為依賴項：

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### 直接下載
或者，從下載最新的 JAR 文件 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

#### 許可證取得步驟
要使用不受評估限制的 Aspose.Slides：
- **免費試用**：取得臨時許可證來測試所有功能。
- **臨時執照**：可在 [臨時執照頁面](https://purchase。aspose.com/temporary-license/).
- **購買**：對於完整的商業用途，請透過他們的 [購買頁面](https://purchase。aspose.com/buy).

取得許可證文件後，請在項目中進行設定：
```java
License license = new License();
license.setLicense("path/to/your/license/file.lic");
```

## 實施指南

滿足了先決條件後，讓我們開始實作轉換功能。

### 使用 Notes 將 PowerPoint 轉換為 TIFF

本節引導您將 PowerPoint 檔案轉換為 TIFF 影像，同時包含投影片註釋。

#### 概述
我們將載入簡報並配置選項以確保投影片註釋顯示在每個 TIFF 頁面的底部。輸出將保存為高品質的 TIFF 檔案。

#### 實施步驟
**1. 載入簡報**
創建一個 `Presentation` 您的 PPTX 檔案的物件：
```java
// 設定文檔目錄路徑
dir = "YOUR_DOCUMENT_DIRECTORY/";

// 實例化代表 PowerPoint 檔案的 Presentation 對象
Presentation pres = new Presentation(dir + "ConvertWithNote.pptx");
```
**2.配置TiffOptions**
創造 `TiffOptions` 指定轉換選項，包括投影片註釋顯示：
```java
// 建立 TiffOptions 進行自訂
TiffOptions opts = new TiffOptions();

// 存取和配置筆記佈局選項
INotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
opts.setSlidesLayoutOptions(notesOptions);
```
*解釋*： 這 `setNotesPosition` 方法確保幻燈片註釋位於每個 TIFF 影像的底部。

**3. 將簡報儲存為 TIFF**
最後，使用指定的選項儲存您的簡報：
```java
try {
    // 使用自訂選項將簡報儲存為 TIFF 格式
    pres.save(dir + "TestNotes_out.tiff\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}