---
title: Java 投影片中不使用 XPS 選項進行轉換
linktitle: Java 投影片中不使用 XPS 選項進行轉換
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為 XPS 格式。帶有原始程式碼的分步指南。
type: docs
weight: 33
url: /zh-hant/java/presentation-conversion/convert-without-xps-options-java-slides/
---

## 簡介 在 Aspose.Slides for Java 中將 PowerPoint 轉換為 XPS，無需使用 XPS 選項

在本教學中，我們將引導您完成使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為 XPS（XML 紙張規格）文件的過程，而無需指定任何 XPS 選項。我們將為您提供完成此任務的逐步說明和 Java 原始程式碼。

## 先決條件

在開始之前，請確保您具備以下先決條件：

1.  Aspose.Slides for Java：確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從[Aspose.Slides for Java 網站](https://downloads.aspose.com/slides/java).

2. Java 開發環境：您的電腦上應該安裝有 Java 開發環境。

## 第 1 步：匯入 Java 版 Aspose.Slides

在您的 Java 專案中，在 Java 檔案的開頭匯入 Java 類別所需的 Aspose.Slides：

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 第 2 步：載入 PowerPoint 簡報

現在，我們將載入您想要轉換為 XPS 的 PowerPoint 簡報。代替`"Your Document Directory"`與 PowerPoint 簡報文件的實際路徑：

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";

//實例化表示簡報文件的簡報對象
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
```

確保您更換`"Convert_XPS.pptx"`與您的 PowerPoint 文件的實際名稱。

## 步驟 3：另存為 XPS（不含 XPS 選項）

使用 Aspose.Slides for Java，您可以輕鬆地將加載的簡報另存為 XPS 文檔，而無需指定任何 XPS 選項。您可以這樣做：

```java
try {
    //將簡報儲存到 XPS 文檔
    pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
} finally {
    if (pres != null) pres.dispose();
}
```

此程式碼區塊將簡報儲存為 XPS 文檔，名稱為`"XPS_Output_Without_XPSOption_out.xps"`。您可以根據需要更改輸出檔名。

## Java 投影片中不帶 XPS 選項的轉換的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//實例化表示簡報文件的簡報對象
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
try
{
	//將簡報儲存到 XPS 文檔
	pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為 XPS 文檔，而無需指定任何 XPS 選項。您可以透過探索 Aspose.Slides for Java 提供的選項來進一步自訂轉換過程。如需更多高級功能和深入文檔，請訪問[Aspose.Slides for Java 文檔](https://docs.aspose.com/slides/java/).

## 常見問題解答

### 轉換時如何指定 XPS 選項？

若要在轉換 PowerPoint 簡報時指定 XPS 選項，您可以使用`XpsOptions`類別並設定各種屬性，例如圖像壓縮和字體嵌入。如果您對 XPS 轉換有特定要求，請參閱[Aspose.Slides for Java 文檔](https://docs.aspose.com/slides/java/)更多細節。

### 是否有其他選項可以儲存為其他格式？

是的，Aspose.Slides for Java 還提供 XPS 以外的各種輸出格式，例如 PDF、TIFF 和 HTML。您可以透過變更來指定所需的輸出格式`SaveFormat`調用時的參數`save`方法。請參閱文件以取得支援格式的完整清單。

### 轉換過程中出現異常如何處理？

您可以實現異常處理，以優雅地處理轉換過程中可能發生的任何錯誤。如代碼所示，一個`try`和`finally`即使發生異常，也可以使用區塊來確保正確的資源處理。