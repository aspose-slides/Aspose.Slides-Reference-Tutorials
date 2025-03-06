---
title: 使用 Aspose.Slides 更改簡報中的 OLE 物件數據
linktitle: 使用 Aspose.Slides 更改簡報中的 OLE 物件數據
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 探索 Aspose.Slides for .NET 在輕鬆更改 OLE 物件資料方面的強大功能。透過動態內容增強您的簡報。
weight: 25
url: /zh-hant/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介紹
創建動態和互動式 PowerPoint 簡報是當今數位世界的常見要求。實現這一目標的一個強大工具是 Aspose.Slides for .NET，這是一個強大的程式庫，可讓開發人員以程式設計方式操作和增強 PowerPoint 簡報。在本教程中，我們將深入研究使用 Aspose.Slides 更改簡報投影片中的 OLE（物件連結和嵌入）物件資料的過程。
## 先決條件
在開始使用 Aspose.Slides for .NET 之前，請確保滿足以下先決條件：
1. 開發環境：設定安裝了.NET的開發環境。
2.  Aspose.Slides 函式庫：下載並安裝 Aspose.Slides for .NET 函式庫。你可以找到圖書館[這裡](https://releases.aspose.com/slides/net/).
3. 基本理解：熟悉 C# 程式設計和 PowerPoint 簡報的基本概念。
## 導入命名空間
在您的 C# 專案中，匯入必要的命名空間以使用 Aspose.Slides 功能：
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## 第 1 步：設定您的項目
首先建立一個新的 C# 專案並匯入 Aspose.Slides 庫。確保您的專案配置正確，並且具備所需的依賴項。
## 第 2 步：存取簡報和投影片
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## 第 3 步：找到 OLE 對象
遍歷投影片中的所有形狀以找到 OLE 物件框架：
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## 步驟4：讀取和修改工作簿數據
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        //讀取工作簿中的物件數據
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            //修改工作簿數據
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            //更改 Ole 框架物件數據
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## 第 5 步：儲存簡報
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## 結論
透過執行這些步驟，您可以使用 Aspose.Slides for .NET 無縫變更簡報投影片中的 OLE 物件資料。這為創建根據您的特定需求量身定制的動態和自訂簡報提供了無限可能。
## 經常問的問題
### 什麼是 Aspose.Slides for .NET？
Aspose.Slides for .NET 是一個功能強大的函式庫，使開發人員能夠以程式設計方式處理 PowerPoint 簡報，從而輕鬆進行操作和增強。
### 在哪裡可以找到 Aspose.Slides 文件？
可以找到 Aspose.Slides for .NET 的文檔[這裡](https://reference.aspose.com/slides/net/).
### 如何下載 .NET 版 Aspose.Slides？
您可以從發布頁面下載該程式庫[這裡](https://releases.aspose.com/slides/net/).
### Aspose.Slides 是否有免費試用版？
是的，您可以免費試用[這裡](https://releases.aspose.com/).
### 在哪裡可以獲得 Aspose.Slides for .NET 的支援？
如需支援和討論，請訪問[Aspose.Slides 論壇](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
