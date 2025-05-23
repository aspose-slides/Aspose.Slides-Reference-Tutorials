---
"date": "2025-04-16"
"description": "了解如何使用 Aspose.Slides for .NET 自動建立和自訂 PowerPoint 表格，從而節省時間並確保格式一致。"
"title": "使用 Aspose.Slides for .NET 建立和自訂 PowerPoint 表格"
"url": "/zh-hant/net/tables/create-customize-powerpoint-tables-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for .NET 建立和自訂 PowerPoint 表格

## 介紹
在 PowerPoint 中建立視覺上吸引人的表格對於有效的資料呈現至關重要。使用 Aspose.Slides for .NET 自動執行此程序可節省時間並確保簡報的一致性。本教學將引導您以程式設計方式建立和自訂 PowerPoint 表格。

**您將學到什麼：**
- 使用 Aspose.Slides for .NET 設定您的環境。
- 以程式設計方式建立 PowerPoint 表格。
- 自訂表格單元格邊框的外觀。
- 將您的簡報儲存為 PPTX 格式。

讓我們先確保您擁有所需的一切，然後深入了解如何自動化您的 PowerPoint 任務。

## 先決條件
在開始之前，請確保您已：

- **庫和依賴項：** 您的專案中安裝了 Aspose.Slides for .NET。
- **環境設定：** 本教學假設使用 Visual Studio 或任何相容的 .NET 開發環境。
- **知識前提：** 對 C# 程式設計的基本了解是有益的，但不是強制性的。

## 設定 Aspose.Slides for .NET
若要將 Aspose.Slides for .NET 整合到您的專案中，請依照下列安裝步驟操作：

**.NET CLI：**
```bash
dotnet add package Aspose.Slides
```

**套件管理器：**
```powershell
Install-Package Aspose.Slides
```

**NuGet 套件管理器 UI：**
- 在您的 IDE 中開啟 NuGet 套件管理器。
- 搜尋“Aspose.Slides”並安裝最新版本。

### 許可證獲取
要充分利用 Aspose.Slides，請考慮以下選項：
1. **免費試用：** 初步探索其特點。
2. **臨時執照：** 獲取一個 [Aspose](https://purchase。aspose.com/temporary-license/).
3. **購買：** 如需完全存取權限，請購買訂閱。

### 基本初始化
安裝後，在您的專案中初始化 Aspose.Slides：
```csharp
using Aspose.Slides;
// 建立代表 PowerPoint 檔案的 Presentation 類別的實例。
Presentation presentation = new Presentation();
```

## 實施指南
讓我們將實施過程分解為建立和自訂表格的明確步驟。

### 在 PowerPoint 中建立表格
#### 概述
我們將首先在第一張投影片上建立具有指定尺寸的表格，重點是設定表格的結構和初始位置。

##### 步驟 1：存取投影片
```csharp
// 實例化代表 PPTX 檔案的演示類別。
using (Presentation pres = new Presentation()) {
    // 存取簡報的第一張投影片。
    ISlide sld = pres.Slides[0];
```

##### 第 2 步：定義表格維度
以點為單位定義具有特定寬度和高度的列和行。
```csharp
// 以點為單位定義列的寬度和行的高度。
double[] dblCols = { 70, 70, 70, 70 };
double[] dblRows = { 70, 70, 70, 70 };

// 在投影片的 (100, 50) 位置新增一個表格形狀。
ITable tbl = sld.Shapes.AddTable(100, 50, dblCols, dblRows);
```

### 自訂表格邊框
#### 概述
接下來，我們在新建立的表格中自訂每個儲存格的邊框。此步驟透過應用實心紅色邊框來增強視覺吸引力。

##### 步驟3：設定邊框樣式
遍歷每個單元格以設定所需的邊框格式。
```csharp
// 為表格中的每個儲存格設定邊框格式。
foreach (IRow row in tbl.Rows) {
    foreach (ICell cell in row) {
        // 使用純紅色自訂儲存格的頂部、底部、左側和右側邊框。
cell.CellFormat.BorderTop.FillFormat.FillType = FillType.Solid;
cell.CellFormat.BorderTop.FillFormat.SolidFillColor.Color = Color.Red;
cell.CellFormat.BorderTop.Width = 5;

cell.CellFormat.BorderBottom.FillFormat.FillType = FillType.Solid;
cell.CellFormat.BorderBottom.FillFormat.SolidFillColor.Color = Color.Red;
cell.CellFormat.BorderBottom.Width = 5;

cell.CellFormat.BorderLeft.FillFormat.FillType = FillType.Solid;
cell.CellFormat.BorderLeft.FillFormat.SolidFillColor.Color = Color.Red;
cell.CellFormat.BorderLeft.Width = 5;

cell.CellFormat.BorderRight.FillFormat.FillType = FillType.Solid;
cell.CellFormat.BorderRight.FillFormat.SolidFillColor.Color = Color.Red;
cell.CellFormat.BorderRight.Width = 5;
    }
}
```

### 儲存簡報
#### 概述
最後，將您的簡報儲存到磁碟上的檔案中。此步驟確保所有變更都已儲存。

##### 步驟 4：儲存您的工作
```csharp
// 使用指定的檔案名稱和格式儲存簡報。
pres.Save("StandardTables_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}