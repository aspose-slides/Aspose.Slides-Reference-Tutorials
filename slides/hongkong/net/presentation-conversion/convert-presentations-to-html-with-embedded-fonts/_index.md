---
"description": "使用 Aspose.Slides for .NET 將 PowerPoint 簡報轉換為具有嵌入字體的 HTML。無縫保持原創性。"
"linktitle": "將簡報轉換為帶有嵌入字體的 HTML"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "將簡報轉換為帶有嵌入字體的 HTML"
"url": "/zh-hant/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 將簡報轉換為帶有嵌入字體的 HTML


在當今數位時代，線上共享簡報和文件已成為一種常見的做法。然而，經常出現的一個挑戰是確保在將簡報轉換為 HTML 時正確顯示字體。本逐步教學將引導您完成使用 Aspose.Slides for .NET 將簡報轉換為帶有嵌入字體的 HTML 的過程，確保您的文件看起來符合您的預期。

## Aspose.Slides for .NET簡介

在深入教學之前，讓我們先簡單介紹一下 Aspose.Slides for .NET。它是一個強大的程式庫，允許開發人員在 .NET 應用程式中處理 PowerPoint 簡報。使用 Aspose.Slides，您可以以程式設計方式建立、修改和轉換 PowerPoint 檔案。

## 先決條件

在開始之前，請確保您已滿足以下先決條件：

- Aspose.Slides for .NET：您應該在專案中安裝 Aspose.Slides 函式庫。您可以從下載 [這裡](https://releases。aspose.com/slides/net/).

## 步驟 1：設定您的項目

1. 在您首選的 .NET 開發環境中建立一個新專案或開啟一個現有專案。

2. 在您的專案中新增對 Aspose.Slides 庫的引用。

3. 在程式碼中匯入必要的命名空間：

   ```csharp
   using Aspose.Slides;
   ```

## 第 2 步：載入簡報

首先，您需要載入要轉換為 HTML 的簡報。代替 `"Your Document Directory"` 與簡報文件所在的實際目錄。

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // 您的程式碼在此處
}
```

## 步驟 3：排除預設簡報字體

在此步驟中，您可以指定要從嵌入中排除的任何預設簡報字體。這有助於優化生成的 HTML 檔案的大小。

```csharp
string[] fontNameExcludeList = { };
```

## 步驟 4：選擇 HTML 控制器

現在，您有兩個在 HTML 中嵌入字體的選項：

### 選項 1：嵌入所有字體

若要嵌入簡報中使用的所有字體，請使用 `EmbedAllFontsHtmlController`。

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### 選項 2：連結所有字體

若要連結到簡報中使用的所有字體，請使用 `LinkAllFontsHtmlController`。您應該指定字體在系統中所在的目錄。

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## 步驟 5：定義 HTML 選項

創建一個 `HtmlOptions` 物件並將 HTML 格式化程式設定為您在上一個步驟中選擇的格式化程式。

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // 使用 embedFontsController 嵌入所有字體
};
```

## 步驟 6：儲存為 HTML

最後，將簡報儲存為 HTML 檔案。您可以選擇 `SaveF或者mat.Html` or `SaveFormat.Html5` 取決於您的要求。

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## 結論

恭喜！您已成功使用 Aspose.Slides for .NET 將簡報轉換為帶有嵌入字體的 HTML。這可確保您的字體在線上分享簡報時能夠正確顯示。

現在，您可以輕鬆自信地分享格式精美的演示文稿，因為您知道觀眾將看到與您預期完全一致的內容。

欲了解更多資訊和詳細的 API 參考，請查看 [Aspose.Slides for .NET 文檔](https://reference。aspose.com/slides/net/).

## 常見問題解答

### 1. 我可以使用 Aspose.Slides for .NET 以批次模式將 PowerPoint 簡報轉換為 HTML 嗎？

是的，您可以使用 Aspose.Slides for .NET 將多個簡報批次轉換為 HTML，方法是循環遍歷簡報檔案並將轉換過程套用至每個簡報。

### 2. 有沒有辦法自訂 HTML 輸出的外觀？

當然！ Aspose.Slides for .NET 提供了各種選項來自訂 HTML 輸出的外觀和格式，例如調整顏色、字體和佈局。

### 3. 使用 Aspose.Slides for .NET 在 HTML 中嵌入字體有什麼限制嗎？

雖然 Aspose.Slides for .NET 提供了出色的字體嵌入功能，但請記住，嵌入字體時 HTML 檔案的大小可能會增加。確保優化字體選擇以適合網頁使用。

### 4. 我可以使用 Aspose.Slides for .NET 將 PowerPoint 簡報轉換為其他格式嗎？

是的，Aspose.Slides for .NET 支援多種輸出格式，包括 PDF、影像等。您可以輕鬆地將簡報轉換為您選擇的格式。

### 5. 在哪裡可以找到更多有關 Aspose.Slides for .NET 的資源和支援？

您可以存取豐富的資源，包括文檔， [Aspose.Slides for .NET API 參考](https://reference。aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}