---
"description": "了解如何使用 Aspose.Slides for .NET 在 PowerPoint 中建立群組形狀。按照我們的逐步指南製作具有視覺吸引力的簡報。"
"linktitle": "使用 Aspose.Slides 在簡報投影片中建立群組形狀"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "Aspose.Slides - 在.NET中建立群組形狀"
"url": "/zh-hant/net/image-and-video-manipulation-in-slides/creating-group-shapes/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - 在.NET中建立群組形狀

## 介紹
如果您希望增強簡報投影片的視覺吸引力並更有效地組織內容，那麼合併群組形狀是一個強大的解決方案。 Aspose.Slides for .NET 提供了在 PowerPoint 簡報中建立和操作群組形狀的無縫方法。在本教程中，我們將介紹使用 Aspose.Slides 建立群組形狀的過程，並將其分解為易於遵循的步驟。
## 先決條件
在深入學習本教學之前，請確保您具備以下條件：
- Aspose.Slides for .NET：確保您已安裝 Aspose.Slides 函式庫。您可以從 [網站](https://releases。aspose.com/slides/net/).
- 開發環境：使用與 .NET 相容的 IDE（例如 Visual Studio）設定工作環境。
- C# 基礎知識：熟悉 C# 程式語言的基礎。
## 導入命名空間
在您的 C# 專案中，首先匯入必要的命名空間：
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## 步驟 1：實例化表示類

建立一個實例 `Presentation` 類別並指定儲存文件的目錄：

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // 在此 using 區塊中繼續執行下列步驟
}
```

## 第 2 步：存取第一張投影片

從簡報中擷取第一張投影片：

```csharp
ISlide sld = pres.Slides[0];
```

## 步驟3：存取形狀集合

存取投影片上的形狀集合：

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## 步驟 4：新增群組形狀

在投影片中新增群組形狀：

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## 步驟5：在群組形狀內新增形狀

使用單一形狀填滿組形狀：

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## 步驟6：新增群組形狀框架

定義整個群組形狀的框架：

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## 步驟 7：儲存簡報

將修改後的簡報儲存到指定的目錄：

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

在您的 C# 應用程式中重複這些步驟，以使用 Aspose.Slides 在簡報投影片中成功建立群組形狀。

## 結論
在本教程中，我們探索了使用 Aspose.Slides for .NET 建立群組形狀的過程。透過遵循這些步驟，您可以增強 PowerPoint 簡報的視覺吸引力和組織性。
## 常見問題
### Aspose.Slides 是否與最新版本的 .NET 相容？
是的，Aspose.Slides 會定期更新以支援最新的 .NET 版本。檢查 [文件](https://reference.aspose.com/slides/net/) 了解相容性詳細資訊。
### 我可以在購買之前試用 Aspose.Slides 嗎？
絕對地！您可以下載免費試用版 [這裡](https://releases。aspose.com/).
### 在哪裡可以找到與 Aspose.Slides 相關的查詢支援？
請造訪 Aspose.Slides [論壇](https://forum.aspose.com/c/slides/11) 以獲得社區支持和討論。
### 如何獲得 Aspose.Slides 的臨時許可證？
您可以獲得臨時駕照 [這裡](https://purchase。aspose.com/temporary-license/).
### 我可以在哪裡購買 Aspose.Slides 的完整授權？
您可以從 [購買頁面](https://purchase。aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}