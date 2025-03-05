---
title: 將 PPT 轉換為 PPTX 格式
linktitle: 將 PPT 轉換為 PPTX 格式
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for .NET 輕鬆將 PPT 轉換為 PPTX。具有無縫格式轉換程式碼範例的逐步指南。
type: docs
weight: 25
url: /zh-hant/net/presentation-manipulation/convert-ppt-to-pptx-format/
---

如果您曾經需要使用 .NET 將 PowerPoint 檔案從較舊的 PPT 格式轉換為較新的 PPTX 格式，那麼您來對地方了。在本逐步教學中，我們將引導您使用 Aspose.Slides for .NET API 完成整個過程。有了這個強大的庫，您可以輕鬆地處理此類轉換。讓我們開始吧！

## 先決條件

在我們深入研究程式碼之前，請確保您已進行以下設定：

- Visual Studio：確保已安裝 Visual Studio 並準備好進行 .NET 開發。
-  Aspose.Slides for .NET：下載並安裝 Aspose.Slides for .NET 函式庫[這裡](https://releases.aspose.com/slides/net/).

## 設定項目

1. 建立新專案：開啟 Visual Studio 並建立一個新的 C# 專案。

2. 新增對 Aspose.Slides 的參考：在解決方案資源管理器中右鍵單擊您的項目，選擇“管理 NuGet 套件”，然後搜尋“Aspose.Slides”。安裝軟體包。

3. 導入所需的命名空間：

```csharp
using Aspose.Slides;
```

## 將 PPT 轉換為 PPTX

現在我們已經設定了項目，讓我們編寫將 PPT 檔案轉換為 PPTX 的程式碼。

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

//實例化表示 PPT 檔案的Presentation 對象
Presentation pres = new Presentation(srcFileName);

//將簡報儲存為 PPTX 格式
pres.Save(outPath, SaveFormat.Pptx);
```

在此程式碼片段中：

- `dataDir`應替換為 PPT 檔案所在的目錄路徑。
- `outPath`應替換為要儲存轉換後的 PPTX 檔案的目錄。
- `srcFileName`是您輸入的 PPT 檔案的名稱。
- `destFileName`是輸出 PPTX 檔案所需的名稱。

## 結論

恭喜！您已使用 Aspose.Slides for .NET API 成功將 PowerPoint 簡報從 PPT 轉換為 PPTX 格式。這個強大的程式庫簡化了此類複雜的任務，讓您的 .NET 開發體驗更加順暢。

如果你還沒有，[下載 .NET 版 Aspose.Slides](https://releases.aspose.com/slides/net/)並進一步探索其能力。

如需更多教學和提示，請造訪我們的[文件](https://reference.aspose.com/slides/net/).

## 經常問的問題

### 1. 什麼是 Aspose.Slides for .NET？
Aspose.Slides for .NET 是一個 .NET 函式庫，可讓開發人員以程式設計方式建立、操作和轉換 PowerPoint 簡報。

### 2. 我可以使用 Aspose.Slides for .NET 將其他格式轉換為 PPTX 嗎？
是的，Aspose.Slides for .NET 支援各種格式，包括 PPT、PPTX、ODP 等。

### 3. Aspose.Slides for .NET可以免費使用嗎？
不，這是一個商業圖書館，但您可以探索[免費試用](https://releases.aspose.com/)來評價其特點。

### 4. Aspose.Slides for .NET還支援其他文件格式嗎？
是的，Aspose.Slides for .NET 也支援處理 Word 文件、Excel 電子表格和其他文件格式。

### 5. 我可以在哪裡獲得有關 Aspose.Slides for .NET 的支援或提出問題？
您可以在以下位置找到問題的答案並尋求支持[Aspose.Slides 論壇](https://forum.aspose.com/).

