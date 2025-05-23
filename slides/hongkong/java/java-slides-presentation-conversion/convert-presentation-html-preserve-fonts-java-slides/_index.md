---
"description": "使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為 HTML，同時保留原始字體。"
"linktitle": "將簡報轉換為 HTML 並在 Java 幻燈片中保留原始字體"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "將簡報轉換為 HTML 並在 Java 幻燈片中保留原始字體"
"url": "/zh-hant/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 將簡報轉換為 HTML 並在 Java 幻燈片中保留原始字體


## Java 投影片中如何將簡報轉換為 HTML 並保留原始字體

在本教學中，我們將探討如何使用 Aspose.Slides for Java 將 PowerPoint 簡報 (PPTX) 轉換為 HTML，同時保留原始字體。這將確保生成的 HTML 與原始簡報的外觀非常相似。

## 步驟 1：設定項目
在深入研究程式碼之前，讓我們確保您已完成必要的設定：

1. 下載 Aspose.Slides for Java：如果您還沒有下載，請下載並將 Aspose.Slides for Java 程式庫包含在您的專案中。

2. 建立 Java 專案：在您最喜歡的 IDE 中設定 Java 項目，並確保您有一個可以放置 Aspose.Slides JAR 檔案的「lib」資料夾。

3. 導入所需的類別：在 Java 檔案的開頭導入必要的類別：

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 步驟 2：將簡報轉換為包含原始字體的 HTML

現在，讓我們將 PowerPoint 簡報轉換為 HTML，同時保留原始字體：

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";

// 載入簡報
Presentation pres = new Presentation("input.pptx");

try {
    // 排除 Calibri 和 Arial 等預設演示字體
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // 建立 HTML 選項並設定自訂 HTML 格式化程序
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // 將簡報儲存為 HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // 處置演示對象
    if (pres != null) pres.dispose();
}
```

在此程式碼片段中：

- 我們使用以下方式載入輸入 PowerPoint 簡報 `Presentation`。

- 我們定義一個字體清單（`fontNameExcludeList`) 我們希望將其排除在 HTML 嵌入之外。這對於排除 Calibri 和 Arial 等常見字體以減小檔案大小很有用。

- 我們建立一個實例 `EmbedAllFontsHtmlController` 並將字體排除列表傳遞給它。

- 我們創造 `HtmlOptions` 並使用設定自訂 HTML 格式化程序 `HtmlFormatter。createCustomFormatter(embedFontsController)`.

- 最後，我們使用指定的選項將簡報儲存為 HTML。

## 將簡報轉換為 HTML 並在 Java 幻燈片中保留原始字體的完整原始程式碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// 排除預設簡報字體
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

在本教學中，您學習如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為 HTML，同時保留原始字體。當您希望在網路上共享簡報時保持其視覺保真度時，這很有用。

## 常見問題解答

### 如何下載適用於 Java 的 Aspose.Slides？

您可以從 Aspose 網站下載適用於 Java 的 Aspose.Slides。訪問 [這裡](https://downloads.aspose.com/slides/java/) 取得最新版本。

### 我可以自訂排除字體的清單嗎？

是的，您可以自訂 `fontNameExcludeList` 數組根據您的要求包含或排除特定字體。

### 此方法適用於 PPT 等較舊的 PowerPoint 格式嗎？

此程式碼範例專為 PPTX 檔案設計。如果需要轉換較舊的PPT文件，則可能需要對程式碼進行調整。

### 我該如何進一步自訂 HTML 輸出？

您可以探索 `HtmlOptions` 類別來客製化 HTML 輸出的各個方面，例如幻燈片大小、圖像品質等等。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}