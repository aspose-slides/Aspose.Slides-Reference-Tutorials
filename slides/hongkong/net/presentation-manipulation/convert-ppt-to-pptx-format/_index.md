---
"description": "了解如何使用 Aspose.Slides for .NET 輕鬆地將 PPT 轉換為 PPTX。具有無縫格式轉換程式碼範例的逐步指南。"
"linktitle": "將PPT轉換為PPTX格式"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "將PPT轉換為PPTX格式"
"url": "/zh-hant/net/presentation-manipulation/convert-ppt-to-pptx-format/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 將PPT轉換為PPTX格式


如果您需要使用 .NET 將 PowerPoint 檔案從較舊的 PPT 格式轉換為較新的 PPTX 格式，那麼您來對地方了。在本逐步教學中，我們將引導您完成使用 Aspose.Slides for .NET API 的過程。有了這個強大的庫，您可以輕鬆處理此類轉換。讓我們開始吧！

## 先決條件

在深入研究程式碼之前，請確保您已進行以下設定：

- Visual Studio：確保您已安裝 Visual Studio 並準備好進行 .NET 開發。
- Aspose.Slides for .NET：從下列位置下載並安裝 Aspose.Slides for .NET 函式庫 [這裡](https://releases。aspose.com/slides/net/).

## 設定項目

1. 建立新專案：開啟 Visual Studio 並建立一個新的 C# 專案。

2. 新增對 Aspose.Slides 的參考：在解決方案資源管理器中右鍵單擊您的項目，選擇“管理 NuGet 套件”，然後搜尋“Aspose.Slides”。安裝該包。

3. 導入所需的命名空間：

```csharp
using Aspose.Slides;
```

## 將 PPT 轉換為 PPTX

現在我們已經設定好了項目，讓我們編寫程式碼將 PPT 檔案轉換為 PPTX。

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// 實例化代表 PPT 檔案的 Presentation 對象
Presentation pres = new Presentation(srcFileName);

// 將簡報儲存為 PPTX 格式
pres.Save(outPath, SaveFormat.Pptx);
```

在此程式碼片段中：

- `dataDir` 應替換為您的 PPT 檔案所在的目錄路徑。
- `outPath` 應替換為您要儲存轉換後的 PPTX 檔案的目錄。
- `srcFileName` 是您輸入的PPT檔案的名稱。
- `destFileName` 是輸出 PPTX 檔案的所需名稱。

## 結論

恭喜！您已成功使用 Aspose.Slides for .NET API 將 PowerPoint 簡報從 PPT 轉換為 PPTX 格式。這個強大的程式庫簡化了像這樣的複雜任務，讓您的.NET 開發體驗更加順暢。

如果你還沒有， [下載 Aspose.Slides for .NET](https://releases.aspose.com/slides/net/) 並進一步探索其能力。

如需更多教學和技巧，請造訪我們的 [文件](https://reference。aspose.com/slides/net/).

## 常見問題

### 1.什麼是 Aspose.Slides for .NET？
Aspose.Slides for .NET 是一個 .NET 函式庫，可讓開發人員以程式設計方式建立、操作和轉換 PowerPoint 簡報。

### 2. 我可以使用 Aspose.Slides for .NET 將其他格式轉換為 PPTX 嗎？
是的，Aspose.Slides for .NET 支援各種格式，包括 PPT、PPTX、ODP 等。

### 3. Aspose.Slides for .NET 可以免費使用嗎？
不，這是一個商業圖書館，但你可以探索 [免費試用](https://releases.aspose.com/) 來評估其特徵。

### 4. Aspose.Slides for .NET 也支援其他文件格式嗎？
是的，Aspose.Slides for .NET 也支援處理 Word 文件、Excel 電子表格和其他文件格式。

### 5. 在哪裡可以獲得 Aspose.Slides for .NET 的支援或詢問相關問題？
您可以在以下位置找到問題的答案並尋求支持 [Aspose.Slides 論壇](https://forum。aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}