---
"description": "了解如何在 Aspose.Slides for .NET 中新增和刪除超連結。使用互動式連結輕鬆增強您的簡報。"
"linktitle": "Aspose.Slides 中的超連結操作"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "Aspose.Slides 中的超連結操作"
"url": "/zh-hant/net/hyperlink-manipulation/hyperlink-manipulation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides 中的超連結操作


超連結是簡報中必不可少的元素，因為它們提供了在幻燈片之間導航或存取外部資源的便捷方式。 Aspose.Slides for .NET 提供了強大的功能，可在簡報投影片中新增和刪除超連結。在本教程中，我們將指導您完成使用 Aspose.Slides for .NET 進行超連結操作的過程。我們將介紹如何向幻燈片添加超連結以及如何從幻燈片中刪除超連結。那麼，就讓我們開始吧！

## 先決條件

在開始之前，請確保您已滿足以下先決條件：

1. Aspose.Slides for .NET：您必須安裝並設定 Aspose.Slides for .NET 函式庫。您可以找到文檔 [這裡](https://reference.aspose.com/slides/net/) 並從下載 [此連結](https://releases。aspose.com/slides/net/).

2. 您的文件目錄：您需要一個目錄來儲存您的簡報文件。確保在程式碼中指定此目錄的路徑。

3. C# 基礎知識：本教學假設您對 C# 程式設計有基本的了解。

現在您已經滿足了先決條件，讓我們繼續使用 Aspose.Slides for .NET 進行超連結操作的逐步指南。

## 在幻燈片中添加超鏈接

### 步驟 1：初始化簡報

首先，您需要使用 Aspose.Slides 初始化簡報。您可以使用以下程式碼執行此操作：

```csharp
using (Presentation presentation = new Presentation())
{
    // 您的程式碼在這裡
}
```

### 步驟 2：新增文字框架

現在，讓我們為投影片新增一個文字方塊。此程式碼建立一個帶有文字的矩形：

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### 步驟3：新增超鏈接

接下來，您將向您創建的形狀中的文字添加超連結。您可以按照以下步驟操作：

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/”);
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### 步驟 4：儲存簡報

最後，使用新增的超連結儲存您的簡報：

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

恭喜！您已成功使用 Aspose.Slides for .NET 為投影片新增超連結。

## 從幻燈片中刪除超鏈接

### 步驟 1：初始化簡報

要從幻燈片中刪除超鏈接，您需要打開現有的簡報：

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### 第 2 步：刪除超鏈接

現在，使用以下程式碼從簡報中刪除所有超連結：

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### 步驟 3：儲存簡報

刪除超連結後，儲存簡報：

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

就是這樣！您已成功使用 Aspose.Slides for .NET 從投影片中刪除超連結。

總而言之，Aspose.Slides for .NET 提供了一種有效的方式來操作簡報中的超鏈接，讓您可以創建互動式且引人入勝的幻燈片。無論您想新增或刪除外部資源的超鏈接，Aspose.Slides 都能簡化流程並增強您的簡報建置能力。

感謝您參加有關 Aspose.Slides for .NET 中的超連結操作的教學課程。如果您有任何疑問或需要進一步的協助，請隨時探索 [Aspose.Slides 文檔](https://reference.aspose.com/slides/net/) 或聯絡 Aspose 社區 [支援論壇](https://forum。aspose.com/).

---

## 結論

在本教程中，我們學習如何使用 Aspose.Slides for .NET 操作簡報中的超連結。我們介紹了超連結的新增和刪除，使您能夠建立動態和互動的簡報。 Aspose.Slides 簡化了這個流程，讓您可以輕鬆地使用指向外部資源的超連結來增強幻燈片。

您對使用 Aspose.Slides 或示範設計的其他方面還有其他疑問嗎？請參閱下面的常見問題以獲得更多見解。

## 常見問題解答

### 使用 Aspose.Slides for .NET 的主要優點是什麼？
Aspose.Slides for .NET 提供了用於建立、操作和轉換簡報的多種功能。它提供了一套全面的工具，可用於為投影片添加內容、動畫和互動。

### 我可以在 Aspose.Slides 中為文字以外的物件新增超連結嗎？
是的，Aspose.Slides 允許您向各種物件添加超鏈接，包括形狀、圖像和文本，讓您可以靈活地建立互動式簡報。

### Aspose.Slides 是否相容於不同的 PowerPoint 檔案格式？
絕對地。 Aspose.Slides 支援各種 PowerPoint 格式，包括 PPT、PPTX、PPS 等。它確保與不同版本的 Microsoft PowerPoint 相容。

### 在哪裡可以找到有關 Aspose.Slides 的更多資源和支援？
如需詳細文件和社區支持，請訪問 [Aspose.Slides 文檔](https://reference.aspose.com/slides/net/) 和 [Aspose 支援論壇](https://forum。aspose.com/).

### 如何獲得 Aspose.Slides 的臨時許可證？
如果您需要 Aspose.Slides 的臨時許可證，您可以取得一個 [這裡](https://purchase。aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}