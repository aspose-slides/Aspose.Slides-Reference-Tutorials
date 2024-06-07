---
title: 在 Java 投影片中取得圖表影像
linktitle: 在 Java 投影片中取得圖表影像
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 取得 Java Slides 中的圖表影像。本逐步指南提供了原始碼和無縫整合的技巧。
type: docs
weight: 19
url: /zh-hant/java/data-manipulation/get-chart-image-java-slides/
---

## Java投影片中取得圖表影像簡介

Aspose.Slides for Java 是一個功能強大的函式庫，可讓您以程式設計方式處理 PowerPoint 簡報。使用此庫，您可以從簡報中建立、操作和提取各種元素，包括圖表。一個常見的要求是從幻燈片中獲取圖表圖像，我們將在本指南中示範如何做到這一點。

## 先決條件

在我們深入研究程式碼之前，請確保您具備以下先決條件：

- 您的系統上安裝了 Java 開發工具包 (JDK)。
-  Aspose.Slides for Java 程式庫已下載並在您的專案中設定。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/java/).

## 第 1 步：設定您的項目

首先在您首選的整合開發環境 (IDE) 中建立一個 Java 專案。確保您已將 Aspose.Slides for Java 程式庫新增至專案的依賴項。

## 第 2 步：初始化簡報

首先，您需要初始化 PowerPoint 簡報。在此範例中，我們假設您的文件目錄中有一個名為「test.pptx」的 PowerPoint 檔案。

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 第 3 步：新增圖表並取得圖像

接下來，您可以將圖表新增到投影片並取得其圖像。在此範例中，我們將添加聚集長條圖。

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

在此程式碼片段中，我們在簡報的第一張投影片上建立一個聚集長條圖，然後取得其縮圖。影像在指定目錄中儲存為“image.png”。

## 在 Java 投影片中取得圖表影像的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

使用 Aspose.Slides for Java 從 Java Slides 取得圖表圖像是一個簡單的過程。使用提供的程式碼，您可以輕鬆地將此功能整合到您的 Java 應用程式中，使您能夠有效地處理 PowerPoint 簡報。

## 常見問題解答

### 如何安裝 Aspose.Slides for Java？

安裝 Aspose.Slides for Java 很簡單。您可以從以下位置下載該程式庫[這裡](https://releases.aspose.com/slides/java/)並按照文件中提供的安裝說明進行操作。

### 我可以在獲取圖像之前自訂圖表嗎？

是的，您可以在獲取圖表圖像之前自訂圖表的外觀、資料和其他屬性。 Aspose.Slides for Java 為圖表自訂提供了廣泛的選項。

### Aspose.Slides for Java 還提供哪些其他功能？

Aspose.Slides for Java 提供了廣泛的用於 PowerPoint 簡報的功能，包括投影片建立、文字操作、形狀編輯等等。您可以瀏覽文件以獲取詳細資訊。

### Aspose.Slides for Java適合商業用途嗎？

是的，Aspose.Slides for Java 可以用於商業目的。它提供了適合個人開發者和企業的授權選項。

### 我可以以不同的格式儲存圖表圖像嗎？

當然！您可以透過在檔案中指定適當的檔案副檔名，以各種格式儲存圖表影像，例如 JPEG 或 GIF`ImageIO.write`方法。