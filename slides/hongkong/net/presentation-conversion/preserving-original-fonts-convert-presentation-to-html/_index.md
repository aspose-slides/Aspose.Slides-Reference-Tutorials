---
title: 保留原始字體 - 將簡報轉換為 HTML
linktitle: 保留原始字體 - 將簡報轉換為 HTML
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for .NET 將簡報轉換為 HTML 時保留原始字體。輕鬆確保字體一致性和視覺衝擊。
weight: 14
url: /zh-hant/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 保留原始字體 - 將簡報轉換為 HTML


在這份綜合指南中，我們將引導您完成使用 Aspose.Slides for .NET 將簡報轉換為 HTML 時保留原始字體的過程。我們將為您提供必要的 C# 原始程式碼並詳細解釋每個步驟。學完本教學課程後，您將能夠確保轉換後的 HTML 文件中的字體與原始簡報保持一致。

## 一、簡介

將 PowerPoint 簡報轉換為 HTML 時，保留原始字體以確保內容的視覺一致性至關重要。 Aspose.Slides for .NET 為實現這一目標提供了強大的解決方案。在本教程中，我們將引導您在轉換過程中保留原始字體所需的步驟。

## 2. 前提條件

在我們開始之前，請確保您具備以下先決條件：

- Visual Studio 安裝在您的電腦上。
- Aspose.Slides for .NET 函式庫已新增至您的專案中。

## 3. 設定您的項目

首先，在 Visual Studio 中建立一個新專案並新增 Aspose.Slides for .NET 程式庫作為參考。

## 4. 載入簡報

使用以下程式碼載入您的 PowerPoint 簡報：

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    //你的程式碼在這裡
}
```

代替`"Your Document Directory"`以及簡報文件的路徑。

## 5. 排除預設字體

若要排除 Calibri 和 Arial 等預設字體，請使用以下程式碼：

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

您可以根據需要自訂此清單。

## 6. 嵌入所有字體

接下來，我們將在 HTML 文件中嵌入所有字體。這可確保保留原始字體。使用以下程式碼：

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7.另存為 HTML

現在，將簡報儲存為帶有嵌入字體的 HTML 文件：

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

代替`"output.html"`與您想要的輸出檔名。

## 八、結論

在本教學中，我們示範如何使用 Aspose.Slides for .NET 將 PowerPoint 簡報轉換為 HTML 時保留原始字體。透過執行這些步驟，您可以確保轉換後的 HTML 文件保持原始簡報的視覺完整性。

## 9. 常見問題解答

### Q1：我可以自訂排除字體清單嗎？

是的你可以。修改`fontNameExcludeList`數組根據您的要求包含或排除特定字體。

### Q2：如果我不想嵌入所有字體怎麼辦？

如果您只想嵌入特定字體，可以相應地修改程式碼。有關更多詳細信息，請參閱 Aspose.Slides for .NET 文件。

### Q3：使用 Aspose.Slides for .NET 有任何授權要求嗎？

是的，您可能需要有效的許可證才能在專案中使用 Aspose.Slides for .NET。請參閱 Aspose 網站以了解許可資訊。

### Q4：我可以使用 Aspose.Slides for .NET 將其他檔案格式轉換為 HTML 嗎？

Aspose.Slides for .NET 主要專注於 PowerPoint 簡報。要將其他文件格式轉換為 HTML，您可能需要探索為這些格式量身定制的其他 Aspose 產品。

### 問題 5：我可以在哪裡獲得更多資源和支援？

您可以在 Aspose 網站上找到更多文件、教學和支援。訪問[Aspose.Slides for .NET 文檔](https://reference.aspose.com/slides/net/)獲取詳細資訊。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
