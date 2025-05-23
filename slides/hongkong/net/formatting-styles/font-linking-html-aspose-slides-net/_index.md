---
"date": "2025-04-15"
"description": "了解如何透過直接嵌入字體，確保在使用 Aspose.Slides for .NET 將簡報轉換為 HTML 時字體渲染的一致性。"
"title": "如何使用 Aspose.Slides for .NET&#58; 在 HTML 中連結字體逐步指南"
"url": "/zh-hant/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for .NET 在 HTML 中連結字體

## 介紹

將簡報轉換為 HTML，同時保持跨平台一致的字體渲染可能具有挑戰性。 **Aspose.Slides for .NET** 提供無縫解決方案，可讓您透過嵌入的字體檔案直接在 HTML 輸出中連結簡報中使用的所有字體。

在本教程中，我們將探討如何使用 Aspose.Slides for .NET 實作字體連結並確保跨不同平台的設計一致性。 

**您將學到什麼：**
- 使用 Aspose.Slides for .NET 設定您的環境
- HTML 轉換中的連結字體
- 編寫用於字體嵌入的自訂控制器
- 實際應用和性能考慮

讓我們深入了解實現這一目標所需的步驟。

## 先決條件

在開始之前，請確保您具備以下條件：

### 所需的庫和依賴項
- **Aspose.Slides for .NET** 函式庫：我們實作的核心元件。

### 環境設定要求
- 安裝了 .NET Framework 或 .NET Core 的開發環境。

### 知識前提
- 對 C# 程式設計有基本的了解。
- 熟悉 HTML 和 CSS，特別是 `@font-face` 規則。

## 設定 Aspose.Slides for .NET

要在 .NET 專案中使用 Aspose.Slides，您需要安裝該程式庫。以下是幾種方法：

### 使用 .NET CLI
```bash
dotnet add package Aspose.Slides
```

### 使用套件管理器控制台
```powershell
Install-Package Aspose.Slides
```

### 透過 NuGet 套件管理器 UI
- 在 Visual Studio 中開啟您的專案。
- 導航至“NuGet 套件管理器”。
- 搜尋“Aspose.Slides”並安裝最新版本。

### 許可證取得步驟
您可以按照以下步驟取得免費試用許可證，以無限制地測試所有功能：
1. **免費試用**：下載臨時許可證 [這裡](https://releases。aspose.com/slides/net/).
2. **臨時執照**：申請延長訪問權限 [這裡](https://purchase。aspose.com/temporary-license/).
3. **購買**：如需完整功能，請購買許可證 [這裡](https://purchase。aspose.com/buy).

### 基本初始化和設定
```csharp
// 建立 License 類別的實例
easpose.slides.License license = new aspose.slides.License();

// 從檔案路徑應用許可證
license.SetLicense("Aspose.Slides.lic");
```

## 實施指南

現在，讓我們使用以下方法在 HTML 轉換中實現字體鏈接 **Aspose.Slides for .NET**。

### 功能概述：HTML 轉換中的連結字體
此功能透過嵌入字體檔案確保簡報中使用的所有字體直接連結到生成的 HTML 檔案中。此方法為維護不同瀏覽器和平台上的設計一致性提供了強大的解決方案。

#### 步驟 1：建立自訂控制器
建立自訂控制器類 `LinkAllFontsHtmlController` 繼承自 `EmbedAllFontsHtmlController`：
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // 設定字體檔案的儲存目錄
    }
}
```
#### 第二步：實作字體書寫方法
這 `WriteFont` 方法將字體資料寫入檔案並產生相應的 HTML 程式碼以供嵌入：
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // 確定要使用的字體名稱，如果可用則優先使用替代字體。
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // 為.woff 字型檔建立文件路徑。
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // 將字型資料寫入指定的檔案路徑。
    File.WriteAllBytes(path, fontData);

    // 使用@font-face 規則產生嵌入字體的 HTML 樣式區塊。
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}