---
title: 將簡報轉換為 HTML，同時保留 Java 投影片中的原始字體
linktitle: 將簡報轉換為 HTML，同時保留 Java 投影片中的原始字體
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為 HTML，同時保留原始字體。
type: docs
weight: 14
url: /zh-hant/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

## 將簡報轉換為 HTML 並保留 Java 投影片中的原始字體簡介

在本教學中，我們將探討如何使用 Aspose.Slides for Java 將 PowerPoint 簡報 (PPTX) 轉換為 HTML，同時保留原始字體。這將確保生成的 HTML 與原始簡報的外觀非常相似。

## 第 1 步：設定項目
在我們深入研究程式碼之前，讓我們確保您已完成必要的設定：

1. 下載 Aspose.Slides for Java：如果您還沒有下載 Aspose.Slides for Java 程式庫並將其包含在您的專案中。

2. 建立 Java 專案：在您最喜歡的 IDE 中設定 Java 項目，並確保您有一個可以放置 Aspose.Slides JAR 檔案的「lib」資料夾。

3. 導入所需的類別：在 Java 檔案的開頭導入必要的類別：

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 步驟 2： 使用原始字體將簡報轉換為 HTML

現在，讓我們將 PowerPoint 簡報轉換為 HTML，同時保留原始字體：

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";

//載入簡報
Presentation pres = new Presentation("input.pptx");

try {
    //排除預設演示字體，如 Calibri 和 Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    //建立 HTML 選項並設定自訂 HTML 格式化程序
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    //將簡報另存為 HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    //處理演示對象
    if (pres != null) pres.dispose();
}
```

在此程式碼片段中：

- 我們使用以下命令載入輸入的 PowerPoint 簡報`Presentation`.

- 我們定義一個字體清單（`fontNameExcludeList`）我們想要從 HTML 中的嵌入中排除。這對於排除 Calibri 和 Arial 等常見字體以減小檔案大小非常有用。

- 我們建立一個實例`EmbedAllFontsHtmlController`並將字體排除列表傳遞給它。

- 我們創造`HtmlOptions`並使用設定自訂 HTML 格式化程序`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- 最後，我們使用指定的選項將簡報儲存為 HTML。

## 將簡報轉換為 HTML 並保留 Java 投影片中的原始字體的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	//排除預設簡報字體
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為 HTML，同時保留原始字體。當您想要在網路上共享簡報時保持簡報的視覺保真度時，這非常有用。

## 常見問題解答

### 如何下載 Java 版 Aspose.Slides？

您可以從 Aspose 網站下載 Aspose.Slides for Java。訪問[這裡](https://downloads.aspose.com/slides/java/)取得最新版本。

### 我可以自訂排除字體清單嗎？

是的，您可以自訂`fontNameExcludeList`數組以根據您的要求包含或排除特定字體。

### 此方法適用於 PPT 等較舊的 PowerPoint 格式嗎？

此程式碼範例是為 PPTX 檔案設計的。如果您需要轉換較舊的 PPT 文件，您可能需要對程式碼進行調整。

### 如何進一步自訂 HTML 輸出？

您可以探索`HtmlOptions`類別來自訂 HTML 輸出的各個方面，例如幻燈片大小、圖像品質等。