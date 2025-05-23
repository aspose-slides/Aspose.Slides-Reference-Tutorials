---
"description": "了解如何使用 Aspose.Slides for .NET 為您的 PowerPoint 簡報新增互動式評論和回應。加強參與和協作。"
"linktitle": "為投影片新增家長評論"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "使用 Aspose.Slides 將父註解新增至投影片"
"url": "/zh-hant/net/slide-comments-manipulation/add-parent-comments/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Slides 將父註解新增至投影片


您是否希望透過互動功能來增強您的 PowerPoint 簡報？ Aspose.Slides for .NET 讓您可以合併評論和回复，為您的觀眾創造動態且引人入勝的體驗。在本逐步教學中，我們將向您展示如何使用 Aspose.Slides for .NET 在投影片中新增父註解。讓我們深入探索這個令人興奮的功能。

## 先決條件

在開始之前，請確保您已滿足以下先決條件：

1. Aspose.Slides for .NET：請確定您已安裝 Aspose.Slides for .NET。你可以下載它 [這裡](https://releases。aspose.com/slides/net/).

2. Visual Studio：您需要 Visual Studio 來建立和執行您的 .NET 應用程式。

3. C# 基礎知識：本教學假設您對 C# 程式設計有基本的了解。

現在我們已經滿足了先決條件，讓我們繼續導入必要的命名空間。

## 導入命名空間

首先，您需要將相關的命名空間匯入到您的專案中。這些命名空間提供了使用 Aspose.Slides for .NET 所需的類別和方法。

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

有了先決條件和命名空間，讓我們將流程分解為多個步驟，以便在投影片中添加父註釋。

## 步驟 1：建立簡報

首先，您需要使用 Aspose.Slides for .NET 建立一個新的簡報。此簡報將成為您添加評論的畫布。

```csharp
// 輸出目錄的路徑。
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // 您添加評論的程式碼將放在這裡。
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

在上面的程式碼中，替換 `"Output Path"` 使用輸出演示所需的路徑。

## 第 2 步：新增評論作者

在新增評論之前，您需要定義這些評論的作者。在這個例子中，我們有兩位作者，“Author_1”和“Author_2”，每個作者都由一個實例表示 `ICommentAuthor`。

```csharp
// 新增評論
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// 新增對評論 1 的回复
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

在這一步驟中，我們建立兩位評論作者，並加入初始評論和對評論的回應。

## 步驟3：新增更多回复

若要建立評論的層次結構，您可以為現有評論新增更多回應。在這裡，我們新增對「comment1」的第二個回應。

```csharp
// 新增對評論 1 的回复
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

這會在您的簡報中建立對話流。

## 步驟 4：新增嵌套回复

評論也可以有嵌套回應。為了證明這一點，我們向「評論 1 的回复 2」添加回复，從而創建子回复。

```csharp
// 新增回復以回復
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

此步驟凸顯了 Aspose.Slides for .NET 在管理評論層次結構方面的多功能性。

## 第五步：更多評論和回复

您可以根據需要繼續添加更多評論和回應。在此範例中，我們新增了另外兩則評論並對其中一條進行了回應。

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

此步驟示範如何為您的簡報創建引人入勝且互動的內容。

## 步驟 6：顯示層次結構

為了直觀地顯示評論層次結構，您可以在控制台上顯示它。此步驟是可選的，但有助於調試和理解結構。

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## 步驟 7：刪除評論

在某些情況下，您可能需要刪除評論及其回應。下面的程式碼片段示範如何刪除「comment1」及其所有回應。

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

此步驟對於管理和更新您的簡報內容很有用。

透過這些步驟，您可以使用 Aspose.Slides for .NET 建立具有互動式評論和回應的簡報。無論您是想吸引觀眾還是與團隊成員合作，此功能都提供了廣泛的可能性。

## 結論

Aspose.Slides for .NET 提供了一套強大的工具來增強您的 PowerPoint 簡報。透過添加評論和回應的功能，您可以創建吸引觀眾的動態和互動內容。本逐步指南向您展示如何在投影片中新增父註解、建立層次結構，甚至在必要時刪除註解。透過遵循以下步驟並瀏覽 Aspose.Slides 文檔 [這裡](https://reference.aspose.com/slides/net/)，您可以將您的演示提升到一個新的水平。

## 常見問題解答

### 我可以在簡報中的特定投影片上新增評論嗎？
是的，您可以透過在建立註釋時指定目標投影片來為簡報中的任何投影片新增註解。

### 是否可以自訂簡報中評論的外觀？
Aspose.Slides for .NET 可讓您自訂註解的外觀，包括其文字、作者資訊和投影片上的位置。

### 我可以將評論和回應匯出到單獨的文件嗎？
是的，您可以將評論和回應匯出到單獨的簡報文件，如步驟 7 所示。

### Aspose.Slides for .NET 是否與最新版本的 PowerPoint 相容？
Aspose.Slides for .NET 設計用於與各種 PowerPoint 版本相容，確保與最新版本相容。

### Aspose.Slides for .NET 是否有可用的授權選項？
是的，您可以在 Aspose 網站上探索許可證選項，包括臨時許可證 [這裡](https://purchase.aspose.com/buy) 或嘗試免費試用 [這裡](https://releases。aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}