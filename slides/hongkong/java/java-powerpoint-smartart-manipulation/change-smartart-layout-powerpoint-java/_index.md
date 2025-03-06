---
title: 使用 Java 變更 PowerPoint 中的 SmartArt 佈局
linktitle: 使用 Java 變更 PowerPoint 中的 SmartArt 佈局
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Java 和 Aspose.Slides for Java 操作 PowerPoint 簡報中的 SmartArt 版面配置。
weight: 19
url: /zh-hant/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 介紹
在本教學中，我們將探討如何使用 Java 操作 PowerPoint 簡報中的 SmartArt 版面。 SmartArt 是 PowerPoint 中的一項強大功能，可讓使用者為各種目的創建具有視覺吸引力的圖形，例如說明流程、層級結構、關係等。
## 先決條件
在我們深入學習本教學之前，請確保您具備以下條件：
1. Java 開發環境：確保您的系統上安裝了 Java 開發工具包 (JDK)。
2.  Aspose.Slides 函式庫：下載並安裝 Aspose.Slides for Java 函式庫[這裡](https://releases.aspose.com/slides/java/).
3. 對 Java 的基本了解：熟悉 Java 程式語言基礎知識將會有所幫助。
4. 整合開發環境 (IDE)：選擇您喜歡的 IDE，例如 Eclipse 或 IntelliJ IDEA。

## 導入包
首先，將必要的套件匯入您的 Java 專案：
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## 第 1 步：設定 Java 專案環境
確保您的 Java 專案在您選擇的 IDE 中正確設定。建立一個新的 Java 專案並將 Aspose.Slides 庫包含在專案的依賴項中。
## 第 2 步：建立新簡報
實例化一個新的Presentation物件來建立一個新的PowerPoint簡報。
```java
Presentation presentation = new Presentation();
```
## 第 3 步：新增 SmartArt 圖形
將 SmartArt 圖形新增至您的簡報。指定投影片上 SmartArt 圖形的位置和尺寸。
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## 第 4 步：更改 SmartArt 佈局
將 SmartArt 圖形的佈局變更為所需的佈局類型。
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## 第 5 步：儲存簡報
將修改後的簡報儲存到系統上的指定目錄。
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## 結論
使用 Aspose.Slides for Java，使用 Java 操作 PowerPoint 簡報中的 SmartArt 佈局是一個簡單的過程。透過遵循本教學課程，您可以輕鬆修改 SmartArt 圖形以滿足您的簡報需求。
## 常見問題解答
### 我可以使用 Aspose.Slides for Java 自訂 SmartArt 圖形的外觀嗎？
是的，您可以自訂 SmartArt 圖形的各個方面，例如顏色、樣式和效果。
### Aspose.Slides 是否與不同版本的 PowerPoint 相容？
Aspose.Slides支援在各種版本的PowerPoint中建立的PowerPoint簡報，確保跨不同平台的兼容性。
### Aspose.Slides 是否提供對其他程式語言的支援？
是的，Aspose.Slides 可用於多種程式語言，包括 .NET、Python 和 JavaScript。
### 我可以使用 Aspose.Slides 從頭開始建立 SmartArt 圖形嗎？
當然，您可以透過程式設計方式建立 SmartArt 圖形或修改現有圖形以滿足您的要求。
### 是否有社群論壇可供我尋求有關 Aspose.Slides 的協助？
是的，您可以造訪 Aspose.Slides 論壇[這裡](https://forum.aspose.com/c/slides/11)提出問題並與社區互動。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
