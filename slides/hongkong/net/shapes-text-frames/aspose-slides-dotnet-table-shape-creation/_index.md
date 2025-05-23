---
"date": "2025-04-16"
"description": "了解如何使用 Aspose.Slides for .NET 在 PowerPoint 簡報中建立動態表格和形狀。按照我們的逐步指南來增強視覺吸引力。"
"title": "使用 Aspose.Slides for .NET 在 PowerPoint 中建立表格和形狀&#58;逐步指南"
"url": "/zh-hant/net/shapes-text-frames/aspose-slides-dotnet-table-shape-creation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for .NET 在 PowerPoint 中建立表格和形狀：逐步指南

## 介紹

透過使用 C# 和 Aspose.Slides for .NET 建立動態表格或在文字周圍繪製形狀來增強您的 PowerPoint 簡報。本指南將引導您完成實現表格建立和形狀繪製功能的過程，使您的投影片更具資訊量和視覺吸引力。

在本教程中，我們將介紹：
- 在 PowerPoint 簡報中建立表格
- 將包含文字部分的段落新增到表格儲存格中
- 在形狀中嵌入文字框架
- 圍繞特定文字元素繪製矩形

在本指南結束時，您將能夠使用 Aspose.Slides for .NET 增強您的簡報投影片。讓我們先深入了解先決條件。

### 先決條件

要繼續本教程，請確保您已具備：
- **開發環境**：您的機器上安裝了 Visual Studio。
- **Aspose.Slides for .NET 函式庫**：我們將使用 22.x 或更高版本。
- **基本 C# 知識**：需要熟悉 C# 文法和概念。

## 設定 Aspose.Slides for .NET

在我們開始編碼之前，讓我們在您的專案中設定 Aspose.Slides 庫。有幾種安裝方法：

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**套件管理器控制台**
```powershell
Install-Package Aspose.Slides
```

**NuGet 套件管理器 UI**：搜尋「Aspose.Slides」並點選安裝按鈕。

### 許可證獲取

您可以從免費試用許可證開始探索所有功能。為了延長使用時間，您可以選擇臨時許可證或購買許可證 [Aspose 網站](https://purchase。aspose.com/buy).

安裝完成後，透過新增以下內容在專案中初始化 Aspose.Slides：

```csharp
using Aspose.Slides;
```

## 實施指南

### 在投影片上建立表格

**概述：**
當您需要清晰地呈現資料時，建立表格是基礎。使用 Aspose.Slides，您可以輕鬆定義表格尺寸和位置。

#### 步驟 1：初始化簡報
首先創建一個 `Presentation` 班級：

```csharp
Presentation pres = new Presentation();
```

#### 步驟 2：新增表
使用 `AddTable` 方法將表格新增至投影片中。指定行和列的位置和大小：

```csharp
ITable tbl = pres.Slides[0].Shapes.AddTable(50, 50, new double[] { 50, 70 }, new double[] { 50, 50, 50 });
```

**參數說明：**
- `50, 50`：左上角的 X 和 Y 座標。
- 數組指定列寬和行高。

#### 步驟 3：儲存簡報
最後，儲存您的簡報：

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY/CreateTable_Out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}