---
"date": "2025-04-16"
"description": "了解如何使用 Aspose.Slides for .NET 將 Excel 電子表格嵌入和自訂為 PowerPoint 中的互動式 OLE 物件。使用動態內容增強您的簡報。"
"title": "使用 Aspose.Slides for .NET 在 PowerPoint 中嵌入 Excel&#58; OLE 物件框架完整指南"
"url": "/zh-hant/net/ole-objects-embedding/embed-excel-powerpoint-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for .NET 在 PowerPoint 中嵌入 Excel：OLE 物件框架完整指南

## 介紹

將 Excel 電子表格等複雜文件嵌入到 PowerPoint 簡報中可能相當具有挑戰性，尤其是當您想要保持其互動性時。本綜合指南將向您展示如何使用 Aspose.Slides for .NET 無縫嵌入和自訂 OLE（物件連結和嵌入）物件框架。透過掌握這些技巧，您將使用超越靜態影像的動態內容來增強您的簡報。

**您將學到什麼：**
- 如何使用 Aspose.Slides 將 Excel 檔案作為圖示嵌入到 PowerPoint 中。
- 使用自訂圖示影像替換預設圖示影像的技術。
- 設定 OLE 物件圖示標題的方法，以提高清晰度和顯示品質。
  

在深入研究程式碼之前，讓我們先概述一下您開始所需的內容。

## 先決條件

要繼續本教程，請確保您已具備：
- **.NET SDK** 已安裝（建議使用 5.x 或更高版本）。
- 熟悉 C# 程式設計基礎。
- 對 .NET 中檔案和記憶體流的操作有基本的了解。

## 設定 Aspose.Slides for .NET

### 安裝

您可以使用以下方法之一輕鬆地將 Aspose.Slides 添加到您的專案中：

**.NET CLI：**
```bash
dotnet add package Aspose.Slides
```

**套件管理器控制台：**
```powershell
Install-Package Aspose.Slides
```

**NuGet 套件管理器 UI：**
- 在您的 IDE 中開啟 NuGet 套件管理器。
- 搜尋“Aspose.Slides”並安裝最新版本。

### 許可證獲取

為了充分利用 Aspose.Slides，您可以獲得臨時許可證或購買一個。可以免費試用測試功能：

- **免費試用：** [點此下載](https://releases.aspose.com/slides/net/)
- **臨時執照：** [在此請求](https://purchase.aspose.com/temporary-license/)
- **購買許可證：** [立即購買](https://purchase.aspose.com/buy)

獲得許可證後，將其應用到您的代碼中以解鎖所有功能。

### 基本初始化

若要開始使用 Aspose.Slides，請如下初始化函式庫：

```csharp
// 如果可用，請申請臨時或購買的許可證
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("path_to_your_license.lic");
```

## 實施指南

讓我們將每個功能分解為易於管理的步驟。

### 新增和配置 OLE 物件框架

本節示範如何將 Excel 文件作為圖示嵌入 PowerPoint 投影片中。

#### 概述
嵌入 OLE 物件可讓您將複雜文件（如電子表格或其他文件）直接插入到簡報中，同時保持其功能。

#### 實施步驟

**1.準備原始文件**
確保您已準備好 Excel 文件 `YOUR_DOCUMENT_DIRECTORY/ExcelObject。xlsx`.

**2. 讀取並嵌入文件**

```csharp
using Aspose.Slides;
using System.IO;

string oleSourceFile = "YOUR_DOCUMENT_DIRECTORY/ExcelObject.xlsx";
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");

using (Presentation pres = new Presentation()) {
    ISlide slide = pres.Slides[0];
    IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
    
    // 將 OLE 物件設定為顯示為圖示
    oof.IsObjectIcon = true;
}
```
- **參數：** `AddOleObjectFrame` 取得框架的位置和大小（x、y、寬度、高度）以及資料資訊。
- **目的：** 環境 `IsObjectIcon` 到 `true` 確保僅顯示圖標，節省空間並保持內容可存取。

### 為 OLE 物件框架新增和配置替換圖片

接下來，我們將用自訂圖像取代預設的 Excel 圖示。

#### 概述
自訂圖示可使您的簡報更具視覺吸引力並符合品牌指導方針。

#### 實施步驟

**1.準備圖示文件**
確保您有一個圖像文件 `YOUR_DOCUMENT_DIRECTORY/Image。png`.

**2. 嵌入並替換預設圖標**

```csharp
using Aspose.Slides;
using System.IO;

string oleIconFile = "YOUR_DOCUMENT_DIRECTORY/Image.png";
byte[] imgBuf = File.ReadAllBytes(oleIconFile);

using (Presentation pres = new Presentation()) {
    using (MemoryStream ms = new MemoryStream(imgBuf)) {
        IPPImage image = pres.Images.AddImage(System.Drawing.Image.FromStream(ms));
        ISlide slide = pres.Slides[0];
        IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, new OleEmbeddedDataInfo(imgBuf, "png"));
        
        // 用自訂圖像取代 OLE 物件的圖標
        oof.SubstitutePictureFormat.Picture.Image = image;
    }
}
```
- **參數：** `AddImage` 方法將圖像新增至演示圖像集合。
- **目的：** 這種替代增強了視覺吸引力，並提供了更好的視覺效果。

### 設定 OLE 物件圖示的標題

添加標題可以闡明幻燈片中每個圖示所代表的含義。

#### 概述
處理多個圖示時，標題至關重要，確保清晰度，而不會使投影片充斥著文字。

#### 實施步驟

**1. 重複使用影像準備步驟**

```csharp
using Aspose.Slides;
using System.IO;

string oleIconFile = "YOUR_DOCUMENT_DIRECTORY/Image.png";
byte[] imgBuf = File.ReadAllBytes(oleIconFile);

using (Presentation pres = new Presentation()) {
    using (MemoryStream ms = new MemoryStream(imgBuf)) {
        IPPImage image = pres.Images.AddImage(System.Drawing.Image.FromStream(ms));
        ISlide slide = pres.Slides[0];
        IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, new OleEmbeddedDataInfo(imgBuf, "png"));
        
        // 設定 OLE 圖示的標題文本
        oof.SubstitutePictureTitle = "Caption example";
    }
}
```
- **目的：** 這 `SubstitutePictureTitle` 屬性可讓您直接在圖示上提供描述性標題。

## 實際應用

合併 OLE 物件框架可以使各種場景受益：

1. **商業報告：** 將互動式 Excel 圖表嵌入 PowerPoint 簡報中，以實現動態資料視覺化。
2. **培訓材料：** 使用 Word 文件作為投影片中的可編輯資源，讓學員在課程期間與內容互動。
3. **行銷簡報：** 直接在投影片中展示 Photoshop 或 AutoCAD 等軟體的設計草稿，讓利害關係人更清楚了解進度。

## 性能考慮

為了確保您的應用程式順利運行：

- **優化記憶體使用：** 使用 `using` 聲明及時處置物品。
- **高效率的文件處理：** 如果可能的話，以較小的區塊載入檔案以減少記憶體佔用。
- **遵循最佳實務：** 定期查看 Aspose.Slides 文件以取得有關效能增強的更新。

## 結論

透過學習本教程，您將學習如何使用 Aspose.Slides for .NET 新增和自訂 OLE 物件框架。這些技術可以透過在幻燈片中直接嵌入豐富的互動式內容來顯著增強您的簡報。繼續探索 Aspose.Slides 的其他功能，以進一步提高您的簡報技巧。

**後續步驟：**
- 嘗試使用不同的文件類型作為 OLE 物件。
- 探索其他 Aspose.Slides 功能，如幻燈片過渡和動畫。

## 常見問題部分

1. **我可以使用 Aspose.Slides 嵌入 PDF 檔案嗎？**
   - 是的，請按照嵌入 Excel 或 Word 文件的類似步驟操作。
2. **如何處理包含許多 OLE 物件的大型簡報？**
   - 優化程式碼以進行記憶體管理，並在必要時考慮拆分演示。
3. **OLE 物件嵌入支援哪些文件格式？**
   - Aspose.Slides 支援多種文件格式，包括 Excel、Word、PDF 等。
4. **是否可以直接在 PowerPoint 中編輯嵌入的文件？**
   - 雖然您可以與嵌入的文檔進行交互，但編輯需要打開原始文件格式。
5. **我可以在沒有授權的情況下使用 Aspose.Slides for .NET 嗎？**
   - 您可以嘗試一下，但有限制；取得許可證可消除浮水印並解鎖全部功能。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}