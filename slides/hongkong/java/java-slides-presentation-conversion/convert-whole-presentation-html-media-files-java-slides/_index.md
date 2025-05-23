---
"description": "了解如何使用 Java Slides 將簡報轉換為帶有媒體檔案的 HTML。按照我們的逐步指南使用 Aspose.Slides for Java API。"
"linktitle": "使用 Java 幻燈片中的媒體檔案將整個簡報轉換為 HTML"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "使用 Java 幻燈片中的媒體檔案將整個簡報轉換為 HTML"
"url": "/zh-hant/java/presentation-conversion/convert-whole-presentation-html-media-files-java-slides/"
"weight": 30
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 幻燈片中的媒體檔案將整個簡報轉換為 HTML


## Java 投影片中如何使用媒體檔案將整個簡報轉換為 HTML

在當今數位時代，將簡報轉換為各種格式（包括 HTML）是一項常見的需求。 Java 開發人員經常發現自己面臨這項挑戰。幸運的是，借助 Aspose.Slides for Java API，可以有效率地完成這項任務。在本逐步指南中，我們將探討如何使用 Java Slides 將整個簡報轉換為 HTML，同時保留媒體檔案。

## 先決條件

在深入研究編碼方面之前，讓我們確保一切都已正確設定：

- Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
- Aspose.Slides for Java：您需要安裝 Aspose.Slides for Java API。你可以下載它 [這裡](https://releases。aspose.com/slides/java/).

## 步驟1：導入必要的套件

首先，您需要匯入必要的套件。這些包將提供我們的任務所需的類別和方法。

```java
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SlideImageFormat;
import com.aspose.slides.SVGOptions;
import com.aspose.slides.VideoPlayerHtmlController;
```

## 步驟2：指定文檔目錄

定義簡報文件所在的文件目錄的路徑。代替 `"Your Document Directory"` 與實際路徑。

```java
String dataDir = "Your Document Directory";
```

## 步驟 3：初始化簡報

載入您想要轉換為 HTML 的簡報。確保更換 `"presentationWith.pptx"` 使用您的簡報的檔案名稱。

```java
Presentation pres = new Presentation("presentationWith.pptx");
```

## 步驟 4：建立 HTML 控制器

我們將創建一個 `VideoPlayerHtmlController` 處理轉換過程。將 URL 替換為您想要的網址。

```java
VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
    "", htmlDocumentFileName, "http://www.example.com/”);
```

## 步驟 5：設定 HTML 和 SVG 選項

為轉換設定 HTML 和 SVG 選項。您可以在此處根據需要自訂格式。

```java
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);
htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
```

## 步驟 6：將簡報儲存為 HTML

現在，是時候將簡報儲存為 HTML 檔案（包括媒體檔案）了。

```java
pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
```

## Java 投影片中將整個簡報轉換為包含媒體檔案的 HTML 的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
String htmlDocumentFileName = "presentationWithVideo.html";
Presentation pres = new Presentation("presentationWith.pptx");
try
{
	VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
			"", htmlDocumentFileName, "http://www.example.com/”);
	HtmlOptions htmlOptions = new HtmlOptions(controller);
	SVGOptions svgOptions = new SVGOptions(controller);
	htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
	htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
	pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，我們介紹了使用 Java Slides 和 Aspose.Slides for Java API 將整個簡報轉換為包含媒體檔案的 HTML 的過程。透過遵循這些步驟，您可以有效地將簡報轉換為適合網路的格式，並保留所有必要的媒體元素。

## 常見問題解答

### 如何安裝 Aspose.Slides for Java？

若要安裝 Aspose.Slides for Java，請造訪下載頁面 [這裡](https://releases.aspose.com/slides/java/) 並按照提供的安裝說明進行操作。

### 我可以進一步自訂 HTML 輸出嗎？

是的，您可以根據您的要求自訂 HTML 輸出。這 `HtmlOptions` 類別提供了各種設定來控制轉換過程，包括格式和佈局選項。

### Aspose.Slides for Java 是否支援其他輸出格式？

是的，Aspose.Slides for Java 支援各種輸出格式，包括 PDF、PPTX 等。您可以在文件中探索這些選項。

### Aspose.Slides for Java 適合商業專案嗎？

是的，Aspose.Slides for Java 是一個強大且具有商業可行性的解決方案，用於處理 Java 應用程式中與簡報相關的任務。在企業級專案中有著廣泛的應用。

### 我如何存取轉換後的 HTML 簡報？

完成轉換後，您可以透過定位到 `htmlDocumentFileName` 多變的。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}