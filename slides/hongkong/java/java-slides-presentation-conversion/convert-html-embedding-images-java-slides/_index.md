---
title: 在 Java 幻燈片中轉換 HTML 嵌入圖像
linktitle: 在 Java 幻燈片中轉換 HTML 嵌入圖像
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 將 PowerPoint 轉換為具有嵌入圖像的 HTML。使用 Aspose.Slides for Java 的逐步指南。了解如何輕鬆地在 Java 中自動執行簡報轉換。
weight: 11
url: /zh-hant/java/presentation-conversion/convert-html-embedding-images-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 幻燈片中轉換 HTML 嵌入圖像


## 在 Java 投影片中轉換 HTML 嵌入圖片簡介

在本逐步指南中，我們將引導您完成將 PowerPoint 簡報轉換為 HTML 文檔，同時使用 Aspose.Slides for Java 嵌入圖像的過程。本教學假設您已經設定了開發環境並安裝了 Aspose.Slides for Java 函式庫。

## 要求

在我們開始之前，請確保您具備以下條件：

1.  Aspose.Slides for Java 程式庫已安裝。您可以從以下位置下載：[這裡](https://downloads.aspose.com/slides/java).

2. 若要轉換為 HTML 的 PowerPoint 簡報檔案（PPTX 格式）。

3. Java開發環境搭建完畢。

## 第 1 步：導入所需的庫

首先，您需要為 Java 專案匯入必要的程式庫和類別。

```java
import com.aspose.slides.Html5Options;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import java.io.File;
```

## 第 2 步：載入 PowerPoint 簡報

接下來，您將載入要轉換為 HTML 的 PowerPoint 簡報。確保更換`presentationName`與簡報文件的實際路徑。

```java
String presentationName = "path/to/your/presentation.pptx";
Presentation pres = new Presentation(presentationName);
```

## 步驟 3：配置 HTML 轉換選項

現在，您將配置 HTML 轉換選項。在此範例中，我們將在 HTML 文件中嵌入圖像並指定外部圖像的輸出目錄。

```java
Html5Options options = new Html5Options();
//強制不在 HTML5 文件中儲存圖片
options.setEmbedImages(true); //設定為 true 以嵌入圖像
//設定外部影像的路徑（如果需要）
options.setOutputPath("path/to/output/directory/");
```

## 第 4 步：建立輸出目錄

在儲存 HTML 文件之前，請建立輸出目錄（如果不存在）。

```java
File outputDirectory = new File(options.getOutputPath());
if (!outputDirectory.exists()) {
    outputDirectory.mkdirs();
}
```

## 步驟 5：將簡報儲存為 HTML

現在，使用指定的選項將簡報儲存為 HTML5 格式。

```java
pres.save(options.getOutputPath() + "output.html", SaveFormat.Html5, options);
```

## 第 6 步：清理資源

不要忘記處置演示對像以釋放任何分配的資源。

```java
if (pres != null) {
    pres.dispose();
}
```

## 在 Java 投影片中轉換 HTML 嵌入影像的完整原始碼

```java
//源演示的路徑
String presentationName = "Your Document Directory";
//HTML 文件的路徑
String outFilePath = "Your Output Directory" + "HTMLConvertion" + File.separator;
Presentation pres = new Presentation(presentationName);
try {
	Html5Options options = new Html5Options();
	//強制不在 HTML5 文件中儲存圖片
	options.setEmbedImages(false);
	//設定外部影像的路徑
	options.setOutputPath(outFilePath);
	//為輸出 HTML 文件建立目錄
	File f = new File(outFilePath);
	if (!f.exists())
		f.mkdir();
	//以 HTML5 格式儲存簡報。
	pres.save(outFilePath + "pres.html", SaveFormat.Html5, options);
} finally {
	if (pres != null) pres.dispose();
}
```

## 結論

在本綜合指南中，我們學習如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為 HTML 文件，同時嵌入圖片。透過遵循逐步說明，您可以將此功能無縫整合到您的 Java 應用程式中並增強您的文件轉換流程。

## 常見問題解答

### 如何更改輸出檔名？

您可以透過修改中的參數來更改輸出檔名`pres.save()`方法。

### 我可以自訂 HTML 模板嗎？

是的，您可以透過修改Aspose.Slides產生的HTML和CSS檔案來自訂HTML模板。您將在輸出目錄中找到它們。

### 如何處理轉換過程中的錯誤？

您可以將轉換程式碼包裝在 try-catch 區塊中，以處理轉換過程中可能發生的異常。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
